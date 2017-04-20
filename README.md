# React Tutorial

We're going to be building a simple solitaire [memory card game](https://en.wikipedia.org/wiki/Concentration_\(game\)).

## Setup
1. Run `npm install`
2. Run `npm start`. This will start a file watcher that will update the application whenever it detects file changes.
3. Go to <http://localhost:8080/webpack-dev-server/#> to see the running application.

## Notes
* This tutorial will require you to do your own research to figure out implementation details for many of these steps.
* This tutorial uses ES6 syntax. Be aware that as you look up examples and code snippets, lots of them will be using ES5 and will have slight differences.
* React is built to be very modular. As you add to existing components, extract subcomponents to encapsulate discrete concepts.

## 1. React Components
* Display a title and a grid of cards.
* When a card is clicked, display an image for the front of the card instead. (See React `setState`)
    * Note that unlike in HTML, you cannot pass the filepath string directly into the `src` attribute of an `img` tag.
    * Don't worry yet about flipping cards back over again.
* Display pairs of images on the fronts of the cards, and randomize these.

## 2. Redux
* Define an action to track how many turns (card flips) a user has taken. Keep this in its own file.
* Build a reducer function that will increment a turn count when your action is triggered. Keep this in its own file as well.
* Use redux `createStore` to capture and expose the turn count application state.
* Use redux `dispatch` to trigger your action from your component.
* Use react-redux `connect` and `Provider` to subscribe your component to changes in the turn count, and display the count in the application.
    * For now, your `connect` function should take a `mapStateToprops` parameter.
* Add the `mapDispatchToProps` parameter to the `connect` function to replace the direct `dispatch` in your component.
* Explore redux-thunk's action pattern to extract the action dispatch further.
* Add an action and reducer to store the list of cards, and subscribe to this card list from any components that need information about the cards.
* Use your redux application state to track which cards are flipped up, rather than keeping this state local to your card component.
* Continue adding to your actions and reducers to flesh out the game functionality (e.g. flip cards back over once two have been turned up unless they match).

## 3. Unit Testing (mocha)
* Run `npm test` to run the unit tests.
* Add unit tests for your reducers. These are pure functions, so you should be able to send actions and assert on the function output.
    * Invoke a reducer with two arguments (initial state, action) to get the new state
* Use [Enzyme](https://github.com/airbnb/enzyme) to add mocha unit tests for your components.
    * What behavior do you expect when the component is clicked?
    * What behavior do you expect from your component when an action is triggered?