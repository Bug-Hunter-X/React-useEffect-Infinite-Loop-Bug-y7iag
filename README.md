# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook that leads to an infinite rendering loop.  The bug occurs when a state variable used within the `useEffect` is not included in the dependency array.  This causes the effect to run continuously, resulting in a performance issue and potentially a crash.

## Bug Description
The provided `MyComponent` uses `useState` to track a count. The `useEffect` hook logs the count to the console. However, it is missing the `count` variable from the dependency array. This makes the effect trigger on every render causing an infinite loop because `setCount` inside the click handler triggers a re-render and therefore triggers the `useEffect` again.