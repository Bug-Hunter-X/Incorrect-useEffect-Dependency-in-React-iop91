# Incorrect useEffect Dependency in React
This example demonstrates a common mistake in using the React `useEffect` hook. The dependency array is missing a crucial element causing an infinite loop. The component re-renders infinitely after first render because of useEffect's condition.

## Bug
The bug lies in the `useEffect` hook. The condition `count > 0` is always true after the first render since `count` is updated, triggering a re-render, and then `useEffect` runs again and again causing an infinite loop.

## Solution
The solution involves carefully reviewing the dependency array for the useEffect hook. Ensure that only the necessary values are included. In this case, including only `count` as a dependency is correct because the effect should only run whenever the `count` value changes.