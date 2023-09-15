# Components 

## LocationCard

The `LocationCard` component is a React Native component that displays information about a location in a card format. The data for the card is currently hardcoded as `fakeData`, but the comment indicates that this will eventually be replaced with real data from the Google API.

Here's a breakdown of what the component does:

- The `Card.Cover` component displays an image from the `photo` property of `fakeData`.
- The `Card.Title` component displays the `name` and `formatted_address` of the location. It also includes an avatar icon on the left and a heart icon button on the right.
- The `Card.Content` component contains several `Chip` components that display various pieces of information about the location:
  - The first `Chip` displays the `rating` of the location.
  - The second `Chip` indicates whether the location is currently open.
  - The third `Chip` displays the `formatted_phone_number` of the location.
  - The fourth `Chip` displays the `website` of the location.
  - The fifth `Chip` displays the `types` of the location.
- The commented out `View` component was intended to display the `price_level` of the location as a series of dollar sign icons.

The `styles` object contains several styles that are applied to the components in the card. For example, `styles.cover_size` is applied to the `Card.Cover` component to set its height, and `styles.title_font` is applied to the `Card.Title` component to set the font size and weight of the title

## SwipingCards

The `SwipingCards` component is a React Native component that displays a stack of cards (using the `Swiper` component from `react-native-deck-swiper`) which can be swiped left or right. Each card is represented by the `LocationCard` component.

Here's a breakdown of what the component does:

- It initializes a state variable `cards` with a list of fake data. This state will hold the data for each card.

- It defines two functions `showLikedToast` and `showSkippedToast` that display a toast message when a card is swiped right (liked) or left (skipped), respectively.

- It defines two functions `onSwipedLeft` and `onSwipedRight` that are called when a card is swiped left or right, respectively. These functions call the appropriate toast function and log the type of swipe.

- In the return statement, it renders a `Swiper` component with the following props:
  - `cards`: the data for each card.
  - `renderCard`: a function that takes a card's data and returns a `LocationCard` component.
  - `onSwipedLeft` and `onSwipedRight`: functions to be called when a card is swiped left or right.
  - `onSwipedAll`: a function to be called when all cards have been swiped.
  - `cardIndex`: the index of the card to be displayed first.
  - `backgroundColor`: the background color of the swiper.
  - `stackSize`: the number of cards to be displayed in the stack.

- It also defines a `styles` object that contains styles for the container and the cards.

In summary, this component displays a stack of cards that can be swiped left or right, and it shows a toast message depending on the direction of the swipe.

## SearchBarStatic

The `SearchComponent` maintains two pieces of state: `searchQuery` and `results`. `searchQuery` is the current text in the search bar, and `results` is an array of search results.

The `onChangeSearch` function is called whenever the text in the search bar changes. It updates `searchQuery` with the new text. If the new text is an empty string, it clears the search results. Otherwise, it filters the `places` array to include only places that contain the new text, takes the first 5 results, and sets `results` to these new results.

The `SearchComponent` renders a `Searchbar` and a list of search results. The `Searchbar`'s `onChangeText` prop is set to `onChangeSearch`, so `onChangeSearch` is called whenever the text in the search bar changes. The `value` prop is set to `searchQuery`, so the text in the search bar reflects the current search query.

The search results are rendered as `List.Item` components. Each `List.Item` displays a search result and logs the result to the console when pressed.