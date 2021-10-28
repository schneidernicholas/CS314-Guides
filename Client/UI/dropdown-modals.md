# Dropdown Modals

In this example, we will be adding a new button to the Itinerary actions dropdown that will toggle open a new modal when pressed. Once in the modal, the user is able to use the "X" or "Close" button to then close that modal.

## 1. Creating a Dropdown Modal Hook
First, to store the state of our dropdown, that is, whether or not the dropdown is currently toggled open or not, we must use a hook. Remember that in React, we can't just pass a variable around for this, we must use a hook.

Luckily, our base code has provided a useful hook called `useToggle`. We will utilize this hook for our dropdowns.
Create the hook in the file where the information is relevant to all of the components. In this case, it will likely be where the component is created.

**`components/Trip/Itinerary.js`**
```js
import { useToggle } from '../../../hooks/useToggle';

...

export function Itinerary(props) {
   const [loadModal, toggleLoadModal] = useToggle(false);
   ...
}
```

Notice how in the `useToggle()` hook call, we specify `false`, this is the default state. By default, we don't want the modal showing, so we set this to `false`. A value of `true` would make the modal show on the screen.

## 2. Using the hook: passing it to the new component
Now, we can get and pass along the current state of the modal with the hook variable `loadModal` and change that using `toggleLoadModal`.
Let's create a new modal component as `components/Trip/LoadModal.js` to store the load modal.

**`components/Trip/LoadModal.js`**
```js
export function LoadModal(props) {
    // We will be adding the modal content here soon! See step 3.
}
```

Now, let's construct this component where we made the hook and pass the toggle hook we made to it, don't forget to add the import:
**`components/Trip/Itinerary.js`**
```js
import { LoadModal } from './LoadModal';

export function Itinerary(props) {
   ...
   <LoadModal toggled={loadModal} toggle={toggleLoadModal} />
}
```

Now, we have passed the props on to the LoadModal, which can now access them via `props.toggled` to see if it is toggled and `props.toggle()` to toggle itself (such as from an exit button).

## 3. Creating the ReactStrap Modal
Let's take a look at the ReactStrap documentation for a Modal: https://reactstrap.github.io/components/modals/
We can use the documentation's example to make a base/skeleton modal in our component:

**`components/Trip/LoadModal.js`**
```js
export function LoadModal(props) {
    return (
        <Modal isOpen={propsmodal} toggle={props.toggled}>
            <ModalHeader toggle={props.toggled}>Modal title</ModalHeader>
            <ModalBody>
                This is an example modal.
            </ModalBody>
            <ModalFooter>
                <Button color="secondary" onClick={props.toggle}>Close</Button>
            </ModalFooter>
        </Modal>
    );
}
```

## 4. Creating the Toggle (Action) Button
Now, we need a button to be able to open the modal itself. You will notice at this point it still is not on the screen, which is intended, it must be toggled to show. Now, at this stage in our setup, any component that is passed the `toggleLoadModal` function will be able to toggle the modal.

Let's pass that now to `actions.js`, where we will add our button to toggle this modal:

**`components/Trip/Itinerary.js`**
```js

export default function Itinerary(props) {
    ...
    <Header 
        ...
        loadModal={loadModal} 
        toggleLoadModal={toggleLoadModal}
    />
}

function Header(props) {
    ...
    <ItineraryActionsDropdown 
        ...
        loadModal={props.loadModal} 
        toggleLoadModal={props.toggleLoadModal} 
    />
    ...
}
```

Let's create a button in the Itinerary actions dropdown. To do so, we need to edit `actions.js` to add a `<DropdownItem>`. Keep in mind that any button could be used, but in this case we are adding to a dropdown, so we need to use the correct React type. The main part of this is the `onClick` field, which specifies what it does when clicked.

**`components/Trip/actions.js`**
```js
import { FiUpload } from 'react-icons/fi';

export function ItineraryActionsDropdown(props) {
    return (
        <ActionsDropdown {...props}>
            ...
            <DropdownItem onClick={() => props.toggleLoadModal()} data-testid='load-button' title="Load trip">
                <FiUpload />
            </DropdownItem>
            ...
        </ActionsDropdown>
    );
}
```

Note that we made use of an icon for our button, `<FiUpload />`. See the guide on [using-icons.md](using-icons.md) for more information on how to import and use icons.
