
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

You can now use the `getCurrentUser` function in your components in the same way as the other functions:

```javascript title="YourComponent.js"
import React, { useContext, useEffect } from 'react';
import SupabaseContext from './SupabaseContext';

function YourComponent() {
  const { getCurrentUser } = useContext(SupabaseContext);

  useEffect(() => {
    const fetchUser = async () => {
      const user = await getCurrentUser();
      console.log(user);
    };

    fetchUser();
  }, []);

  return <div>Your component</div>;
}

export default YourComponent;
```

In this example, `YourComponent` calls the `getCurrentUser` function when it mounts and logs the current user to the console.

## Supabase Functions

How can i find out more about Supabase functions?

!!! info
    Please use version 2.0.0 of the Supabase client. Version 1.0.0 is deprecated and we are not using it.

- [Supabase Auth](https://supabase.io/docs/reference/javascript/auth-signup)
- [Supabase Database](https://supabase.com/docs/reference/javascript/select)
- [Supabase Storage](https://supabase.com/docs/reference/javascript/storage-createbucket)
- [Supabase Realtime](https://supabase.com/docs/reference/javascript/subscribe)

