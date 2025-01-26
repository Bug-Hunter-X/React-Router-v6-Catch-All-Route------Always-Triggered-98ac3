# React Router v6 Catch-All Route Bug

This repository demonstrates a common, yet subtle bug in React Router v6 related to catch-all routes (`/*`).  The issue is that the catch-all route is always triggered, overriding other, more specific routes.

## Bug Description

The provided `App.js` demonstrates this issue.  Despite having a route for `/` and `/about`, the `NotFound` component (associated with `/*`) is always rendered. This happens because the order of routes matters, and a catch-all route should generally be the last route defined.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe that navigating to `/` or `/about` always shows the `Not Found` page.

## Solution

The solution is to place the catch-all route (`/*`) as the last route in the `Routes` component, so it only matches if no other route matches first.

See `bugSolution.js` for the corrected code.
