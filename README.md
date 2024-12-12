# React setInterval Memory Leak

This repository demonstrates a common error in React applications: using `setInterval` within a `useEffect` hook without providing a cleanup function. This leads to memory leaks and potential performance issues.

## Bug

The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it fails to provide a cleanup function in the `useEffect` hook. This means that even after the component unmounts, the `setInterval` continues to run, consuming resources and potentially causing memory leaks.

## Solution

The `bugSolution.js` file demonstrates the correct way to use `setInterval` within `useEffect`.  A cleanup function is returned, which uses `clearInterval` to stop the interval when the component is unmounted.