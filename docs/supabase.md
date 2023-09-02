
## Supabase Overview

The `SupabaseProvider` component in /lib/context is a context provider for the Supabase client, authentication, and database functions. It uses the React Context API to provide these functionalities to all components inside of the application.

The way `SupbaseProvider` works, is that it creates a context object that contains the Supabase client and authentication functions. It then wraps the application in a `SupabaseContext.Provider` component, which provides the context object to all components in the application. This allows all components to access the Supabase client and authentication functions using the `useContext` hook.


```javascript linenums="7" title="App.js"
export default function App() {
  return (
    <SupabaseProvider>
      <PaperProvider>
        <GlobalNav></GlobalNav>
      </PaperProvider>
    </SupabaseProvider>
  );
}

```

## Example Usage

An an example, lets say we had a component called `YourComponent`, it can now access the Supabase client and authentication functions using our custom hook in '/lib/hooks/useSupabase.js'.

```javascript title="YourComponent.js"
import React, { useContext } from 'react';
import useSupabase from './lib/hooks/useSupabase'; // This route is not correct, but you get the idea

function YourComponent() {
  const { isLoggedIn, login, register, forgotPassword, logout } = useSupabase();

  // You can now use isLoggedIn, login, register, forgotPassword, and logout in your component

  return <div>Your component</div>;
}

export default YourComponent;
```

## Adding new functions to SupabaseProvider

To add a new function to `SupabaseProvider`, you need to define it in the `SupabaseProvider` component and add it to the value of the `SupabaseContext.Provider` component. Here's an example of how you can add a function that gets the current user:

```javascript title="SupabaseProvider.js"
// In SupabaseProvider.js

// Define the getCurrentUser function
const getCurrentUser = async () => {
  const { data: { user } } = await supabase.auth.getUser()
  return user;
};

// Add getCurrentUser to the value of the SupabaseContext.Provider component
return (
  <SupabaseContext.Provider
    value={{ isLoggedIn, login, register, forgotPassword, logout, getCurrentUser }}
  >
    {isNavigationReady ? props.children : null}
  </SupabaseContext.Provider>
);
```

In SubabaseContext.js, you need to add the `getCurrentUser` function to the `SupabaseContext` object:

```javascript title="SupabaseContext.js" linenums="1"
// In SupabaseContext.js

import { createContext } from 'react';

const SupabaseContext = createContext({
  isLoggedIn: false,
  login: async () => {},
  register: async () => {},
  forgotPassword: async () => {},
  logout: async () => {},
  getCurrentUser: async () => {}, // Add getCurrentUser to the SupabaseContext object
});

export default SupabaseContext;
```


You can now use the `getCurrentUser` function in your components in the same way as the other functions
using the `use Supabase` hook:

```javascript title="YourComponent.js"
import React, { useContext } from 'react';
import useSupabase from './lib/hooks/useSupabase'; // This route is not correct, but you get the idea

function YourComponent() {
  const { getCurrentUser } = useSupabase();

  // You can now use getCurrentUser in your component

  getCurrentUser().then((user) => console.log(user));

  return <div>Your component</div>;
}
```

In this example, `YourComponent` calls the `getCurrentUser` function when it mounts and logs the current user to the console.

!!! question
    Why is using a hook better than using the context object directly?

    !!! answer
        Using a hook is better because it allows you to use the function in a functional component. If you use the context object directly, you can only use the function in a class component. Also, using a hook is easier to read and understand. It is also easier to test. useSupabase has clearer semantics than useContext(SupabaseContext). (useSupabase is a custom hook that uses the useContext hook under the hood)

## Supabase Functions

!!! question
    How can i find out more about Supabase functions?
    !!! answer
        You can find out more about Supabase functions by reading the documentation. Here are some links to the documentation:
    - [Supabase Auth](https://supabase.io/docs/reference/javascript/auth-signup)
    - [Supabase Database](https://supabase.com/docs/reference/javascript/select)
    - [Supabase Storage](https://supabase.com/docs/reference/javascript/storage-createbucket)
    - [Supabase Realtime](https://supabase.com/docs/reference/javascript/subscribe)

!!! info
    Please use version 2.0.0 of the Supabase client. Version 1.0.0 is deprecated and we are not using it.


