# Context

Hooks by default are client side.
Eliminates SSR.

share data "globally" - user authenticate, theme preference etc...

1. Client component

createContext
useContext

2. Third party

Client component called Providers, wrap the third party providers. "use client"

3. Server component

How to create it in a server component?
Add "use client".
