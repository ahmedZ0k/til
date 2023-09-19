
# useReducer React.js

useReducer is hook to mange states:

const [state, dispatch] = useReducer(reducer, initializeState);

okay let’s breakdown this hook

1- initalizeState: is an object that contain all states we want to manage by the Reducer hook

```jsx
const initalizeState = {
age: "",
name: "",
isClicked: false,
counter: 1,
}
```

2- state : it’s an object that contain all the states in the **initalizeState** and we can destruct the states like that

```jsx
const [ { name, age, isClicked, counter }, dispatch] = useReducer(reducer, initializeState);
```

3- dispatch: is a function that get the order to the reducer function to mange/update the certain state, let’s imagine that we have button and we want to update the state **isClicked** when we click on the button and we want to update the counter by add 5 on each Click

```jsx
<button onClick={ () ⇒ { dispatch( { type: “clicked”, payload:5 } ) } }>click here</button> 
```

4-reducer: it’s a function where we manage the states

```jsx
function reducer( state, action ){
switch ( action.type) {
case “clicked”:
	return { …state, isClicked: true, counter: state.counter + action.payload }
default:
	throw new Error (”Unknown Action”)
}
}
```

-states values after click on the button

```jsx
name = ""
age = ""
isClicked = true
counter = 6
```

here because we want to just update the isClicked state we return other stats without change by

…state
