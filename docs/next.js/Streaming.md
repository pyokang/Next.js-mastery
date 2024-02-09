Streaming is a data transfer technique that allows you to break down a route into smaller “chunks” and progressively stream them from the server to the client as they become ready.

With streaming, data fetching and rendering for each chunk is also initiated in parallel, solving the waterfall problem.

Streaming works well with React's component model, as each component can be considered a chunk.

Two ways of implementing streaming:

1. At the page level, with the loading.tsx file.

   - loading.tsx is a special Next.js file built on top of Suspense, it allows you to create loading UI to show as a replacement while page content loads.
   - Since <Sidebar> is static, it's shown immediately. The user can interact with <Sidebar> while the dynamic content is loading.
   - The user doesn't have to wait for the page to finish loading before navigating away (this is called interruptable navigation).

2. For specific components, with <Suspense>.

## Suspense

Suspense allows you to defer rendering parts of your application until some condition is met (e.g. data is loaded). You can wrap your dynamic components in Suspense. Then, pass it a fallback component to show while the dynamic component loads.
