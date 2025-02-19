# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook:  an infinite loop caused by a missing dependency. 

## Bug Description

The `useEffect` hook is used to perform side effects after a component renders.  However, if a variable used inside the `useEffect` function is not included in the dependency array, it will cause the effect to re-run on every render, creating a potential infinite loop. 

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`. 
4. Observe the console for continuous logging and potentially a browser crash (due to excessive re-renders).

## Solution

The solution involves adding the variable that's being modified inside the `useEffect` to the dependency array. In this case it's the `count` variable.  By including `count` in the dependency array, the effect only runs when the value of `count` changes.