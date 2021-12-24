Redux

- npx xreate-react-app react-redux
- npm install redux react-redux
- npm install redux-logger
- npm install --save redux-devtools-extension
- npm install redux-thunk

* initialState 
* Store
	* contain the state
	* createStore method
	* createStore accepts a reducer as a parameter
	* Provider used to provide store to the react application in App.js
	* Provider will take the store as a prop
	* Accepts only one reducer
	* Middlewares
	* applyMiddleware function passed in as a parameter to the createStore function
	* takes in parameters to be exuted
	* logger middleware - to view actions and state in console
	* react-redux middleware
		- redux dev tool extension
		- composeWithDevTools function
		- accepts applyMiddleware as an argument withother middlewares
	* redux thunk middleware - allows action creaters to react a function instead of an action
* Reducer
	* update state
	* Accepts state and action as parameters
	* Contain a switch statements based on action type
	* Each case returns a state changed or unchanged
	* combineReducers function takes in maps reducers to variables
	* Async functions
		- state: loading state, data, error message
		- actions: fetch date request, success and error
* Action 
	* define state change
	* A function that returns an object
	* Has a type - define action type
	* Can contain a payload passed in when dispatching an action to the reducer
	* can fetch data and trigger other actions based on the return data returned using fetch or axios.
* Dispatch
	* handle action changes
* Constants 
	* for easy typing
	
///////// access store without hooks /////////
* mapStateToProps
	* takes in the redux state as a parameter
	* returns an object of props with the data
	* if there are many reducers should specify state reducer variable key in the combineReducers
	* Can also take in component props that have been passed in already, ownProps
	* ownProps allows to use booleans to check if prop exists.
* mapDispatchToProps
	* takes redux dispatch method as a paraeter and returns an object with functions to trigger a dispatch
	* Also accepts ownProps to determine dispatch
* connect
	* to connect mapDispatchToProps and mapStateToProps with the current react component
	* file can the access the state and the dispatch method through props
	
///////// access store with hooks /////////
* useSelector
	* takes in a selector function as a parameter
	* selector function takes in the redux state as a parameter
	* selector returns a value that can be stored in a const
	* if there are many reducers should specify state reducer variable key in the combineReducers
* useDispatch
	* returns a ref to a dispatch function that can be stored in a const and used to dispatch actions
