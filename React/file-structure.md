# React File Structure
The React project features a file structure that categorizes various needs and utilities in certain ways. This guide will go over what each of these are and where certain things should go.

`client/`

    `schemas`
    
    `src`
    
        `components`
        
        `hooks`
        
        `static`
        
        `utils`
        
    `test`
  
## `schemas`
This folder contains JSON schemas used for validation. These schemas almost always can be found in the [product repo](https://github.com/CSU-CS-314-Fall-2021/product). For example, if you are looking to validate a find response, you would add https://github.com/CSU-CS-314-Fall-2021/product/blob/main/protocol/find/FindResponse.json to the schemas folder.

## `src/components`
This houses all of the UI (user-interface) components. These include things like the page layout structure and styling, buttons, text, and so forth. Components should do very little data processing and code in these files should largely be related to UI elements and making them function. All functionalities that these UI elements perform should be calls from the component to a hook or util file that does the actual processing.

## `src/hooks`
All React hooks can be found here. Hooks are a way of passing data along to many components and allowing it to be updated by any of those components, propagating to any other components with that hook variable. We can define the behavior of this hook in its hook file, which is located in this directory. Create any new hooks here if needed.

## `src/static`
This is for static assets, which includes things like images and stylesheets (`scss`).

## `src/utils`
This is for utility functions/classes and is where a lot of the data processing happens. For example, `restfulAPI.js` handles making REST API calls and any portion of the client can import and use those functionalities. Offload functionalities like these to a util file, calling it from the component, and receiving back what is neccessary for the UI (e.g. a success or error message).

## `test`
This is where all of the test cases can be found.
