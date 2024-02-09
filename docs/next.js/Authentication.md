# Authentication

Two main packages

1. Next-Auth
2. Clerk

Authentication - You are who you say you are
Authorisation - What are you authroised to use

`auth.config.ts`
`middleware.ts`
Middleware runs before any requests.

The advantage of employing Middleware for this task is that the protected routes will not even start rendering until the Middleware verifies the authentication, enhancing both the security and performance of your application.
