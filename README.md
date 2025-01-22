# React useEffect setInterval memory leak

This repository demonstrates a common error when using `setInterval` within a React `useEffect` hook and provides a solution to prevent memory leaks. In React 18 and 19, this remains a frequent issue if not handled correctly.

## Bug

The `bug.js` file showcases an incorrect implementation of `setInterval` within `useEffect`.  The missing cleanup function leads to the interval continuing to run even after the component unmounts, resulting in a memory leak.

## Solution

The `bugSolution.js` file demonstrates the correct way to use `setInterval` within `useEffect`.  A cleanup function is returned to clear the interval when the component unmounts or when the dependency array changes, thus preventing memory leaks.

## How to reproduce the bug:

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the console for any errors or warnings (none will appear from the incorrect code). The memory leak would occur in memory rather than being detectable in the console immediately. Using a memory profiler would be necessary for clear demonstration of the leak.
5. Switch to the solution to see it fixed.
