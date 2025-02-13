# React 19 useEffect Shallow Comparison Bug

This repository demonstrates a subtle bug related to shallow comparisons within the `useEffect` hook in React 19.  When comparing objects within the `useEffect` dependency array, React's shallow comparison might not work as expected, leading to unexpected re-renders or infinite loops.

## Bug Description
The issue occurs when you directly compare objects within the `useEffect` hook's dependency array. Since React performs a shallow comparison, changes within the object won't trigger a re-render unless a new object reference is used.

## Solution
The solution involves ensuring that the object you are comparing is deeply compared or that you create a new object reference when the state changes. You can achieve this through techniques like using JSON.stringify to compare strings or updating the object with a new reference on state change.