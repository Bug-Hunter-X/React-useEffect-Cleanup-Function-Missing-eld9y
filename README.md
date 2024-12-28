# React useEffect Cleanup Function Missing

This repository demonstrates a common error in React's `useEffect` hook: forgetting to include a cleanup function to prevent memory leaks.  The `bug.js` file contains the erroneous code, while `bugSolution.js` provides the corrected version.

## Problem

The `useEffect` hook in `bug.js` fetches data from an API when the component mounts. However, it omits a return statement containing a cleanup function.  This means that when the component unmounts, the fetch request remains active, potentially causing memory leaks, especially with repeated component mounts/unmounts.

## Solution

The `bugSolution.js` file shows the corrected code.  A cleanup function is added using a return statement within the `useEffect` callback. This function cancels or cleans up any resources (in this case, an in-flight fetch request) before the component is unmounted, preventing resource leaks.