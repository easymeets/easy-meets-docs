# Project Overview


## File Structure

The file structure for the project is as follows for our react native app:

``` bash
easy-meets
├── .expo-shared
├── .github
├── .vscode
├── assets
├── lib
├── components
├── screens
├── styles
├── tests
├── App.js
├── app.json
├── babel.config.js
├── jest.config.js
├── package.json
├── .gitignore
├── README.md

```

## Naming Conventions and Style

We use the following naming conventions and style to make it easier for developers to read and understand the code.

### Naming Conventions

#### Components
   Components have the following naming convention:
    - **Functional Components**: `ComponentName.js`
    - **Class Components**: `ClassName.js`
    
!!! tip
    Functional components are preferred over class components.
    Please use functional components unless you have a good reason to use a class component.


#### Files
   Files have the following naming convention based on their type:
    - **Components**: `ComponentName.js`
    - **Classes**: `ClassName.js`
    - **Functions**: `functionName.js`
    - **Variables**: `variableName.js`
    - **Styles**: `styleName.js`
    - **Tests**: `testName.js`
    
!!! tip
    Components and Classes do not have camel case, while Functions, Variables, Styles, and Tests do.
    Please follow this convention when creating new files.

### Style

   Easy meets uses the React Native Paper library for styling.
    The documentation for this library can be found [here](https://callstack.github.io/react-native-paper/).

!!! tip
    Please use the React Native Paper library for styling components.
    
!!! danger
    Do not use inline styling or other libraries. This will make it harder for other developers to read your code.


### Links

- [React Native Paper](https://callstack.github.io/react-native-paper/)
- [Figma](https://www.figma.com/file/k9AhUzLgY0px7BrlQIveL8/Easy-Meets?type=design&node-id=0%3A1&mode=design&t=5865oJhuzAITqhWr-1).
