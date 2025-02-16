# React Native useEffect Async Function Cleanup Issue

This repository demonstrates a common issue in React Native: using the `useEffect` hook with an async function without proper cleanup.  This can lead to memory leaks and unexpected behavior.

The `bug.js` file contains the problematic code.  The `bugSolution.js` file shows the corrected code with proper cleanup.

The problem stems from the lack of a returned promise from the async function within `useEffect`, making it impossible to reliably clean up resources (like network requests) when the component unmounts.

The solution uses a promise returned by the async function to handle cancellation, improving memory management and application stability.  A cleanup function ensures resources are released as needed. 