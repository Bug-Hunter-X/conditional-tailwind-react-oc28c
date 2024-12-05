# Tailwind CSS Classes Not Applied in Conditionally Rendered Components

This repository demonstrates a common issue when using Tailwind CSS with server-side rendering (SSR) frameworks.  The problem arises when applying Tailwind classes to elements conditionally rendered based on server-side data.  The solution involves ensuring the elements are rendered on the client-side, even if their initial visibility depends on server-side conditions.

## Problem

When using frameworks like Next.js or Nuxt.js with server-side rendering (SSR), if you have a component that conditionally renders an element based on data only available on the server, applying Tailwind classes to that element may not work as expected. This is because the client-side JavaScript responsible for applying the Tailwind classes might not run before the element is mounted, leading to the classes not being applied.

## Solution

To resolve this issue, ensure that the elements are rendered on the client-side.  Even if the initial state of the element is hidden due to a server-side condition, it needs to exist in the DOM for Tailwind to apply the classes.

This often involves using a combination of client-side rendering and state management to control the visibility.