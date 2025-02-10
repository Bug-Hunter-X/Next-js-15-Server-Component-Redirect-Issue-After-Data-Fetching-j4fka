# Next.js 15 Server Component Redirect Issue

This repository demonstrates a subtle bug in Next.js 15's `app` directory when using server components and redirects.  The problem occurs when a server component fetches data and subsequently attempts a redirect based on that data.  The redirect is often ignored, resulting in unexpected behavior.

## Bug Description
A server component fetches data.  Based on the data, it should redirect to a different page. However, the redirect is not executed and the original component renders with the fetched data, despite the redirect call.

## Steps to Reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run `npm run dev`.
4. Observe the unexpected behavior.

## Solution
The solution involves careful handling of redirects within the server component's asynchronous operations.  This may require refactoring the data fetching to explicitly return a `redirect` object which next.js will handle properly.