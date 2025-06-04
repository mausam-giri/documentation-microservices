# Tech Stack
- Docusaurus
- React Query
- React Table
- Tailwind css
- Redux (if required)

** Use latest version of each tool **
## Style Guide
- Create theme for the whole website in the tailwind config and use tailwind directives
- Don't use component library
- Create required component only
- Structure the page

** Important **
- Implement browser side caching
- Create two different routes
  -  Admin (protected under guard) can only be accessed on /admin, it will require login page, invite to join page where user puts in email-address and code to join, and forgot password page.
    - Admin will show the documentation for the specific usage made only for role based user
    - Inside admin pages will be guarded based on the user roles (everything will be fetched from server)   
  -  Public routes for the public documentation
