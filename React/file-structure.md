# React File Structure
The React project features a file structure that categorizes various needs and utilities in certain ways. This guide will go over what each of these are and where certain things should go.

`client/`  
- `schemas`  
- `src`  
    - `components`  
    - `hooks`  
    - `static`  
    - `utils`  
- `test`  
  
## `schemas`
This folder contains JSON schemas used for validation. These schemas almost always can be found in the [product repo](https://github.com/CSU-CS-314-Fall-2021/product). For example, if you are looking to validate a find response, you would add https://github.com/CSU-CS-314-Fall-2021/product/blob/main/protocol/find/FindResponse.json to the schemas folder.

## `src/components`
This houses all of the UI (user-interface) components. These include things like the page layout structure and styling, buttons, text, and so forth. Components should do very little data processing and code in these files should largely be related to UI elements and making them function. All functionalities that these UI elements perform should be calls from the component to a hook or util file that does the actual processing.

## `src/hooks`
All React hooks can be found here. Hooks are a way of passing data along to many components and allowing it to be updated by any of those components, propagating to any other components with that hook variable. We can define the behavior of this hook in its hook file, which is located in this directory. Create any new hooks here if needed.

## `src/static`
This is for static assets, which includes things like images and stylesheets (`scss`). It's unlikely that you will need to edit any of the stylesheets unless you know SCSS and are an advanced web programmer. You may need to add an image, which you can do by adding that image file into the corresponding directory in the `static/images` directory.

## `src/utils`
This is for utility functions/classes and is where a lot of the data processing happens. For example, `restfulAPI.js` handles making REST API calls and any portion of the client can import and use those functionalities. Offload functionalities like these to a util file, calling it from the component, and receiving back what is neccessary for the UI (e.g. a success or error message).

## `test`
This is where all of the test cases can be found. Follow the directory structure to create a Component.test.js file for each component we need to test.
Make note of `test/sharedMocks.js`, where you can use and add new mock cases, such as for a sample JSON TripFile. These can then be imported to any number of test cases to be used.

## Examples

Some examples of things we're looking to add and how that might correspond to the project file structure.

> **Example #1:** Looking to add a new button that queries an API for some result to mark on the map.  

In this case, we can break this down into some categories to help us see what files to create:
- UI
    - Button
- Functionality
    - API request, process result, send back to UI to handle
- Test
    - A test case for each of these things.  

Now that we understand how we want to break down our code, let's cater it to the project's file structure. By category, this is how our list would correspond to the correct file directory:  
`UI` goes in `src/components`  
`Functionality` goes in `src/utils`  
`Test` goes in `test`  

So, we would end up with a new or edited component in `src/components` that has a `<Button>`, which `onClick` calls a function from a file in `src/utils` you either added to or created for this purpose to have something processed, then handles the result of that. Additionally, before making a pull request, we would make test cases to get branch coverage for any components or new functionalities we added in any files. We would make these in the `test` directory corresponding to the file structure and file names, except instead of `.js` the file is named `.test.js`.

What determines if you create a new component or add to an existing one depends on what you are adding. If it is a simple button you are adding to a menu, then it likely does not need it's own component. However, if it's a search bar with a results area, it may need multiple components added. The same goes for whether or not you add to an existing util or create a new one. If the functionality you are adding pertains to places for example, add to the existing `utils/places.js` file. On the other hand, if it's something not currently covered by any util file category, you may need to create a new one, such as one for saving or uploading files.
