# React: Memory Leak in useEffect with setInterval

This repository demonstrates a common React bug: a memory leak caused by the improper use of `setInterval` within the `useEffect` hook.  The initial code lacks a cleanup function to stop the interval when the component unmounts, leading to a memory leak.

The solution demonstrates the correct implementation, including a cleanup function to ensure that the interval is cleared when the component is no longer needed.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the component's behavior.
5. Examine the `bug.js` file for the faulty code, and the `bugSolution.js` file for the corrected version.

## Bug Explanation

The bug is caused by the `setInterval` function inside the `useEffect` hook without a cleanup function. When the component unmounts, the interval continues running in the background, leading to a memory leak.

## Solution

The solution adds a cleanup function that uses `clearInterval` to stop the interval when the component unmounts. This prevents the memory leak and ensures proper resource management.