# React setInterval Memory Leak
This repository demonstrates a common mistake when using `setInterval` within a React component's `useEffect` hook.  Forgetting to return a cleanup function from `useEffect` results in a memory leak, as the interval continues even after the component is unmounted.

## Bug
The `bug.js` file contains a React component that increments a counter every second using `setInterval`. However, it lacks a cleanup function to clear the interval when the component unmounts. This causes the interval to persist, leading to wasted resources and potential performance issues.

## Solution
The `bugSolution.js` file demonstrates the correct way to use `setInterval` within `useEffect`. It returns a cleanup function that uses `clearInterval` to stop the interval when the component is unmounted, preventing memory leaks.