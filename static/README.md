# React, NextJS and Now: course 2

(2.5hrs)

This course is aimed at experienced developers who have complete [course-1](https://course-1.willemliu.now.sh). This course will build upon the product created in course-1. The goal is to learn how to configure `now` and use its power to handle custom routing.
After this course you will know how to:

-   Configure `now.json` with custom routes.
-   Depart from `next` and use `now dev` for local development.
-   Fetch data from an external endpoint.
-   Make use of Server-side rendering

# Recap

<details>
<summary>course-1</summary>

In course-1 we've learned the following:

-   How to initialize an NPM project using the `npm init` command.
-   How to bootstrap all the dependencies needed for a NextJS application: `npm i -S typescript next react react-dom @types/react @types/react-dom @types/node`
-   All pages go into the `pages` folder by convention. And any other code should go elsewhere.
-   Run installed node-modules from the command-line using the `npx <module>` command.
-   Inside an NPM Script the `npx` part can be omitted.
-   You can run a NextJS app simply running `npx next` from command-line.
-   Deploy to Now cloud provider by simply calling `now` from the command-line.

</details>

# Acceptance criteria

1. Should handle `/<section>/<id>` routes
1. Should render the `section` and `id` values given as URL Query parameters on the page
1. Fetch data from a JSON endpoint
1. Render a value from fetched JSON to your page.
1. Render the value server-side.

# Steps

<details>
<summary>Sprint 3</summary>

1. Create a `now.json`
    - Tip: `now.json`: https://zeit.co/docs/v2/advanced/configuration/
1. Create a custom route to your `index.tsx`. Navigating to `/this_is_the_section/123` should land you on `index?section=this_is_the_section&id=123`.
    - Tip: Configuring routes in `now.json`: https://zeit.co/docs/v2/advanced/routes/
    - Bonus: Parameter id should only match numbers
    - Run `now dev` to see your custom route in action
1. Render the `section` and `id` URL parameters on your page
    - Tip: Use implement `getInitialProps`
    - Tip: URL Query parameter: https://nextjs.org/docs#fetching-data-and-component-lifecycle

</details>

<details>
<summary>Sprint 4</summary>

1. Create a new component named `Data.tsx` in the `components` folder
1. Include `<Data/>` in your `index.tsx` page
1. Implement the following inside your `<Data/>` component
1. Fetch JSON data from `https://xz4on0khc6.execute-api.eu-west-1.amazonaws.com/dev` and store it as component state
    - Tip: Install `fetch-everywhere` module: https://github.com/lucasfeliciano/fetch-everywhere
    - Put `import 'fetch-everywhere';` at the top of your `index.tsx`
    - Tip: Fetch API: https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch
1. Render a value found in the fetched JSON data in your `Data` component
1. Make sure your component isn't in an endless render-loop
1. Clicking anywhere on the `<Data/>` component should result in a color change
    - Tip: toggle between 2 colors by setting it as component-state which is then used in your styled-jsx

</details>

<details>
<summary>Sprint 5</summary>

1. Create a new page named `DataPage.tsx`
1. Remove `<Data/>` component from `index.tsx` and include it in `DataPage.tsx` instead. (may require `now dev` restart)
1. Use `getInitialProps` to fetch your data and return the data so you can use it as `props` on your page
1. Fetch JSON data from `https://xz4on0khc6.execute-api.eu-west-1.amazonaws.com/dev` and store it as component state
1. Render a value found in the fetched JSON data on the page
1. Clicking anywhere on the page should result in a color change of the rendered value
    - Tip: make it distinguishable from `<Data/>`
    - Tip: toggle between 2 colors by setting it as component-state which is then used in your styled-jsx
1. Include your `<Data/>` component from Sprint 2 and place it at the bottom of the page
1. Do you notice a difference in rendering of the page data vs component data?

</details>

# What's next

<details>
<summary>`next` steps?</summary>

1. Single-Page App
1. Make use of [Prettier](https://prettier.io/)
1. Deploy for staging and production
1. Use environment secrets

</details>

# Resources

-   now.json: https://zeit.co/docs/v2/advanced/configuration/
-   Configuring routes in `now.json`: https://zeit.co/docs/v2/advanced/routes/
-   URL Query parameter: https://nextjs.org/docs#fetching-data-and-component-lifecycle
-   Fetch API: https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch
