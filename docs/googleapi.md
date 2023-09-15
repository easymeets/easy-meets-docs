# Google-APi

## Overview

The `google-api` directory contains functions for fetching data from the Google Places API. The functions are defined in `googleapi.js`, and they can be imported into other files using the following import statement:

```javascript
import { getNearbyPlaces } from '../google-api/google-api';
```

## Functions

1. `getNearbyPlaces(location, radius, type)`: This function fetches places near a specific location within a certain radius. The type of places to fetch can be specified (e.g., restaurant, cafe, etc.). It returns an array of places.

Example usage:
```javascript
async function fetchNearbyPlaces() {
  try {
    const places = await getNearbyPlaces('37.4226711,-122.0849872', 1000, 'restaurant');
    console.log(places);
  } catch (error) {
    console.error(error);
  }
}

fetchNearbyPlaces();
```

2. `getGooglePhotoUrl(photoReference, maxWidth)`: This function generates a URL for a Google Places photo. The `photoReference` is a unique identifier for the photo, and `maxWidth` specifies the maximum width of the photo.

Example usage:
```javascript
const photoUrl = getGooglePhotoUrl('CmRaAAAA...', 400);
console.log(photoUrl);  // Outputs the URL of the photo
```

3. `getDetails(placeId)`: This function fetches detailed information about a place specified by its `placeId`. It returns an object containing the place's details.

Example usage:
```javascript
async function fetchPlaceDetails() {
  try {
    const details = await getDetails('ChIJN1t_tDeuEmsRUsoyG83frY4');
    console.log(details);
  } catch (error) {
    console.error(error);
  }
}

fetchPlaceDetails();
```

4. `getGeocode(address)`: This function converts an address into geographic coordinates (latitude and longitude). It returns an array of results, each containing the geographic coordinates and other information about a location.

Example usage:
```javascript
async function fetchGeocode() {
  try {
    const results = await getGeocode('1600 Amphitheatre Parkway, Mountain View, CA');
    console.log(results);
  } catch (error) {
    console.error(error);
  }
}

fetchGeocode();
```

5. `getPlaceFromText(input)`: This function fetches places that match a text query. It returns an array of places.

Example usage:
```javascript
async function fetchPlacesFromText() {
  try {
    const places = await getPlaceFromText('coffee in Sydney');
    console.log(places);
  } catch (error) {
    console.error(error);
  }
}

fetchPlacesFromText();
```

6. `parseCardData(location, radius, type)`: This function fetches nearby places and formats the data for display in a card. It returns an array of objects, each representing a card.

Example usage:
```javascript
async function fetchCardData() {
  try {
    const cards = await parseCardData('37.4226711,-122.0849872', 1000, 'restaurant');
    console.log(cards);
  } catch (error) {
    console.error(error);
  }
}

fetchCardData();
```

7. `parseCardDataTextSearch(input)`: This function fetches places that match a text query and formats the data for display in a card. It returns an array of objects, each representing a card.

Example usage:
```javascript
async function fetchCardDataFromText() {
  try {
    const cards = await parseCardDataTextSearch('coffee in Sydney');
    console.log(cards);
  } catch (error) {
    console.error(error);
  }
}

fetchCardDataFromText();
```