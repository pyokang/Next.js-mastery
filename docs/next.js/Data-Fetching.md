https://nextjs.org/docs/app/building-your-application/data-fetching/fetching-caching-and-revalidating

Two potential problems we need to think about

1. The data requests are unintenionally blocking each other, creating a request waterfall.
2. By default, Next.js prerenders routes to improve performance, this is called Static Rendering. So if your data changes, it won't be reflected in your dashboard.

# 1

For example,

await getSomeData()
await getAnotherData()
...

Each line blocks another from running. This is not desired unless subsequent lines depend on the result from the previous one.
We can use `Promise.all(...)` or `Promise.allSettled(...)`, however one slow async function can effect the rest of the responses.
