# React Memory Leak with setInterval in useEffect Hook
This repository demonstrates a common error in React applications: memory leaks caused by improper use of `setInterval` within the `useEffect` hook.

The `bug.js` file contains a component that uses `setInterval` to update a counter every second. However, the returned cleanup function from `setInterval` (using `clearInterval`) is missing, leading to a memory leak.

The `bugSolution.js` file shows the corrected version that uses the return value of `setInterval` to clear the interval when the component unmounts, thus preventing the memory leak.

## How to Reproduce
1. Clone the repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe that the counter continues to increment even after unmounting the component (this might require inspecting developer tools to confirm the effect).
