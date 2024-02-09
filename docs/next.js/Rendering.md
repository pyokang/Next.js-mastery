# CSR

Client refers to our device

# SSR

Sends the required outcome after computation

Before Next.js v13, only the route pages could be rendered Server side.
Lead to problems such as

- Prop drilling
- Duplication of API calls

[Read](https://vercel.com/blog/nextjs-app-router-data-fetching)

App directory - brought Component level SSR

1. client components - rendered on browser
2. server components - rendered on server

By choosing to render components on server side, we can save browser from doing extra work to show the components.
We get initial html code which is immediately displayable.
Reduces the bundle size of JS - "Initial load time gets faster"

1. Smaller JS bundle size
2. Enhanced SEO - improves search engine visibility and indexing
3. Faster initial page load - better UX and browsing experience
4. Efficient utilization of server resources - Reduces the overhead / latency

# When to decide what to render where?

Depends on what the component does.
Ask "Does it need user interactivity"

### Requires user interaction

"Client component"

1. clicking buttons
2. Entering information in input fields
3. Triggering events
4. Using react hooks

### Doesn't require user interaction

[Server component](https://vercel.com/blog/understanding-react-server-components)

1. Fethcing data from a server
2. Displaying static content
3. Performing server side computations

[Table](https://nextjs.org/docs/app/building-your-application/rendering/composition-patterns)

All components are automatically considered server components by default, unless specified otherwise

"use client"

Server components are guaranteed to be only rendered on the server

Client components are primarily rendered on the client side. Next.JS also prerenders them on the server to ensure smooth UX and improved SEO

static rendereing - pre-renders necessary contents from the server before it sends it to client.

When we use "use client" in a file, all the other modules imported into that file, including child server components, are treated as part of the client module

> DO NOT INCLUDE SERVER COMPONENTS INSIDE THE CLIENT COMPONENTS

> SSR focuses on initial page load, sending pre-rendered HTML to the client that must then be hydrated with downloaded JavaScript before it behaves as a typical React app. SSR also only happens one time: when directly navigating to a page.

Different ways things are displayed(strategies)
the specific times they run (runtime/build time)
and the specific places where they work (environment)

# Rendering

Process of generating or creating the user interface from the code we write.
React 18 and Next.js 13 introduced different strategies to render an application
2 environments to render our code - Client and Server

For B2B, CSR is suitable
Interactive features without dedicating too much to SEO optimization

## Static Rendering

data fetching and rendering happens on the server at build time (when you deploy) or during revalidation. The result can be distributed and cached in CDN

Some benefits of Static Rendering are:

1. Faster Websites - Prerendered content can be cached. This ensures that users around the world can access your website's content more quickly and reliably.
2. Reduced Server Load - Because the content is cached, your server does not have to dynamically generate content for each user request.
3. SEO - Prerendered content is easier for search engine crawlers to index, as the content is already available when the page loads. This can lead to improved search engine rankings.

## Dynamic Rendering

content is rendered on the server for each user at request time (when the user visits the page).

Some benefits of Dynamic Rendering are:

1. Real-Time Data - Dynamic rendering allows your application to display real-time or frequently updated data. This is ideal for applications where data changes often.
2. User-Specific Content - It's easier to serve user-specific content, such as personalized dashboards or user profiles, through dynamic rendering, as the data is updated based on user interaction.
3. Request Time Information - Dynamic rendering allows you to access information that can only be known at request time, such as cookies or the URL's search params.
