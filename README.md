# React useEffect Hook Missing Cleanup Function

This repository demonstrates a common, yet subtle, error in React applications: forgetting to include a cleanup function within the `useEffect` hook. This can lead to memory leaks and unexpected behavior, especially when dealing with subscriptions, timers, or other resources that need to be released when the component unmounts.

## The Problem

The provided `bug.js` file showcases a `useEffect` hook that logs a message when the component mounts. However, it lacks a return statement, which is crucial for defining a cleanup function.  Without this cleanup function, the effect's side effects (in this case, a simple log, but could be anything more resource-intensive) will persist even after the component is unmounted from the DOM.

## The Solution

The `bugSolution.js` file provides the corrected version, including a cleanup function within the `useEffect` hook. This function ensures that any necessary cleanup, such as canceling subscriptions or clearing timers, is performed when the component unmounts, preventing potential issues.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository's directory.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe the console logs and behavior with both `bug.js` and `bugSolution.js` to understand the difference.