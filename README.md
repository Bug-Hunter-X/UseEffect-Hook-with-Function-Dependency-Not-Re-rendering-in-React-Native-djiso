# React Native useEffect Hook Issue

This repository demonstrates a common, yet subtle, issue when using the `useEffect` hook in React Native. Specifically, the issue occurs when a function is included in the dependency array of `useEffect`, and that function uses values from state variables. 

The problem is that React doesn't detect changes to the *contents* of the function, only to the function reference itself. If the function closes over state, updates to that state don't trigger a re-render because the function reference remains the same.

The `bug.js` file shows the problematic code.  The `bugSolution.js` file demonstrates the correct approach.