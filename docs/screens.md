# Screens

## Overview

The `screens` directory contains the React Native screens for the application. Each screen is a React component that is rendered by the `NavigationContainer` component in `App.js`. The screens are organized into subdirectories based on the navigation stack they belong to. For example, the `ExploreScreen` component is located in `screens/ExploreScreen.js`.

## ExploreScreen

The `ExploreScreen` component in this React Native application provides a user interface for exploring locations. It has three main states: "location", "search", and "settings". In the "location" state, users can view a map with a draggable marker, input an address to update the marker's location, and search for places within a specified radius from the marker. The search results are displayed as swipeable cards. In the "search" state, users can enter a search query to find places, and the results are also displayed as swipeable cards. In the "settings" state, users can adjust the type of places to search for. The component uses several hooks to manage state, including the current page state, the search query, the marker's location, the search radius, and the search type. It also uses the `getGeocode` function to convert an address to geographic coordinates, and the `parseCardData` and `parseCardDataTextSearch` functions to fetch places data from the Google Places API.