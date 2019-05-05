# React

## Function-Based Component
```
import React from 'react';

const app = props => {
	return <div>It is a app component!</div>;
};
```
Benefits: Simple, can access to props system

## Class-Based Component
```
import React from 'react';

class app extends React.Component {
	render () {
		return <div>It is a app component</div>;
	};
};
```
Benefits: Props system, State system, React Life cycle method

## React State
---
### Rule of React State
* Only usable with Class-based component
* Updating State will causes the React App rendered
* State must be initialized when the class is created
* You must use `setState` to update the State

### 2 Ways to initialize a State
1. ES6 Class syntax
```
constructor (props) {
	super(props);
	this.state = { something: null };
}
```
2. ES7 constructor syntax
```
state = { something: null };
```

## React Component Life Cycle Method
---
1. <b>constructor</b> --> try to do data loading in componentDidMount
2. <b>render</b> --> best practice is to aviod doing anything besides return JSX
3. <b>componentDidMount</b>  --> when content visible on screen, good for data loading
4. <b>componentDidUpdate</b> --> when render method is called, good for data loading when state change
5. <b>componentWillMount</b> --> wait until the content become invisible, good for clean up non-react stuff

## Communicating Child to Parent
---
Using Callback function
```
// Parent component
class App extends React.component {
	onSearchSubmit(term){
		// Do some API request
	};

	render() {
		return <SearchBar onSubmit={ this.onSearchSubmit }>;
	};
};

// Child component
class SearchBar extends React.component {
	state = { term: '' };

	onFromSubmit = e => {
		e.preventDefault();
	};

	render() {
		return (
			<form onSubmit={this.onFormSubmit}>
				<input 
					type='text' 
					value={this.state.term} 
					onChange={e => this.setState({ term: e.target.value })
				/>
			</from>
		)
	}

}
```

## React-related packages
---
* <b>react</b>
* <b>create-react-app</b> -> Initize react project
* <b>redux</b> -> For centralized management of the state 
* <b>react-redux</b> -> Integration layer between react and redux
* <b>redux-thunk</b> -> Redux middleware for handling async request in redux action creators

# Redux
	Redux Life Cycle
		1. Action Creater
			a. Synchronous action creator
				- Must return plain JS object (No async/await, No promise)
				- Cannot handle async request such as api call
				
			b. Async action creator (Using react-thunk)
				- Either return JS object or a function
				- Can return a async function to handle async request
				- The action creator receive the dispatch function and getState function
				- Can perform certain actions then call dispatch manually
			
		2. Action
			- Must have a type property
			- Optionally have a payload property (The data)
			
		3. Dispatch
		4. Reducer
			Rules of Reducer
				a. Reducer must return any values besides 'undefined'
				b. Must use the previous state and action creator to calculate a new state (Not APIs)
					(state v1, action) => return state v2
				c. Must not mutate the input state. Since react app will not re-rendered if same address of state is return.
				
				Correct way to mutate a state
					Array state
						Removing		`state.filter(element => element !=='to_remove')`
						Adding			`.[..state, 'to_add']`
						Replacing		`state.map(el => el === 'old' ? 'new' : el)`
						
					JS Object state
						Removing		`
		5. State



