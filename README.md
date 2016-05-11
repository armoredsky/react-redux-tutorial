#React Tutorial

We're going to be building a simple children's memory card game.

##Setup
1. Run `npm install`
2. Run `npm start`. This will start a file watcher that will update the application whenever it detects file changes.
3. Go to <http://localhost:8080/webpack-dev-server/#> to see the running application.

##1. React Components
* Display a title and a grid of cards.
* When a card is clicked, display an image for the front of the card instead. (See React `setState`)
    * Don't worry yet about flipping cards back over again.
* Display pairs of images on the fronts of the cards, and randomize these.

##2. Redux
* Use redux-act `createAction` to define an action to track how many turns (clicks) a user has taken. Keep this in its own file.
* Use redux-act `createReducer` to build a reducer function that will increment a turn count when your action is triggered. Keep this in its own file as well.
* Use redux `createStore` to capture and expose the turn count application state.
* Use react-redux `connect` to subscribe your component to changes in the turn count, and display the count in the application.
* Add an action and reducer to store the list of cards, and subscribe to this card list from any components that need it.
* Continue adding actions and reducers to flesh out the game functionality (e.g. flip cards back over once two have been turned up unless they match).

##3. Unit Testing (mocha)
* Run `npm test` to run the unit tests.
* Add unit tests for your reducers. These are pure functions, so you should be able to dispatch actions and assert on the function output.
* Extract your pure React components from the react-redux containers. Containers should just handle the react-redux `connect` (including mapping state).
* Use the [React Test Utilities](https://facebook.github.io/react/docs/test-utils.html) to add mocha unit tests for your components.
    * What behavior do you expect when the component is clicked?
    * What behavior do you expect from your component when an action is triggered?
