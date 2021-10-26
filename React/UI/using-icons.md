# Using Icons
Icons are a powerful way to convey meaning to a user in a quick way in the user interface. We do not need to create our own icons, the base code comes with [react-icons](https://react-icons.github.io/react-icons/), which includes several libraries of icons we can easily import and use.

Note that some icons are not available from the search listing.

## 1. Selecting an Icon
First, we must select an icon that fits what we are trying to convey to the user. This can be done by using the [search on the react-icons documentation](https://react-icons.github.io/react-icons/search). Once you've found a fitting icon, copy the name of it. We will use this later in our import.

## 2. Import the Icon for use
In the desired file, add an import to the top following this format:
```js
import { <PackName><IconName> } from 'react-icons/<PackName>';
```

For example, if the icon we have is `BsFillCloudRainFill`, `<PackName>` woudl be `Bs` and `<IconName>` would be `FillCloudrainFill`. Therefore, the import would be:
```js
import { BsFillCloudRainFill } from 'react-icons/bs';
```

## 3. Use the Icon after Importing
Now that the icon has been imported for use, it can actually be created. These icons can be created like any other React component, using their name as the component name.

For example, if I want to make a `BsFillCloudRainFill` icon:
```js
<BsFillCloudRainFill />
```

## 4. Increasing the Size or Other Options
Other options can be provided to the icon component, allowing it to be customized to the UI area it's in.

### `size` prop
You can utilize the `size` prop to specify a particular size. For example:
```js
<BsFillCloudRainFill size={32} />
```

### `color` prop
You can change the color of the icon itself using this prop, for example:
```js
<BsFillCloudRainFill color={"blue"} />
```

## 4. Using inside Buttons, other Components
These icon components can very easily be used in other components. For example, the icon component can be placed inside of a button to make the button have that icon:
```js
<Button>
    <BsFillCloudRainFill /> Stormy Weather
</Button>
```
This will create a button with the rain cloud icon and the text next to it, "Stormy Weather." You can choose to add text next to the icon like this, or you can just have the icon alone.
