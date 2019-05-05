# React

### Popular package
* react
* create-react-app  Initize react project
* redux             For centralize the state management
* react-redux       Integration layer between react and redux
* redux-thunk       Redux middleware for handling async request in redux action creators




Redux
	

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



