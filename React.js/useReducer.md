# useReducer React.js

useReducer is hook to mange states:

const [state, dispatch] = useReducer(reducer, initializeState);

okay let’s breakdown this hook

1- initalizeState: is an object that contain all states we want to manage by the Reducer hook

```jsx
const initalizeState = {
age: "",
name: "",
isClicked: false
}
```

2- state : it’s an object that contain all the states in the **initalizeState** and we can destruct the states like that

```jsx
const [ { name, age ,isClicked}, dispatch] = useReducer(reducer, initializeState);
```

3- dispatch: is a function that get the order to the reducer function to mange/update the certain state, let’s imagine that we have button and we want to update the state **isClicked** when we click on the button

```jsx
<button onClick={ () ⇒ { dispatch( { type: “clicked” } ) } }>click here</button> 
```

4-reducer: it’s a function where we manage the states

```jsx
function reducer( state, action ){
switch ( action.type) {
case “clicked”:
	return { …state, isClicked: true }
default:
	throw new Error (”Unknown Action”)
}
}
```

here because we want to just update the isClicked state we return other stats without change by

…state
