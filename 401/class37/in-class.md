# In Class Notes: NextJS Application

* `npx create-next-app@latest <name-of-project> --javascript --eslint`
* Use all defaults (enter, enter, enter)
* Install Tailwinds CSS
  * `npm install -D tailwindcss postcss autoprefixer`
  * `npx tailwindcss init -p`
  * NOTE: Make sure to install in the project directory
* In `tailwinds.config.js`
  
  ```js
  /** @type {import('tailwindcss').Config} */
  module.exports = {
    content: ["./src/**/*.{html,js}"],
    theme: {
      extend: {},
    },
    plugins: [],
  }
  ```

* In `styles/globals.css`

  ```js
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
  ```

* In `pages/index.js`
  * Remove everything other than `Head`
  * Create a proof of life

    ```jsx
    <h1 className='text-3xl font-bold underline'>Hello World</h1>
    ```

* `npm run dev` to start the server
  * Check that proof of life works
* Add in additional required HTML elements
  * `header`
  * `main`
  * `footer`
  * NOTE: Just make one big app to start, then turn them into components later once we know how the final app will look
* To create links to new pages
  
  ```jsx
  import Link from 'next/link`

  <Link href='linktopage'>Link Display Name</Link>
  ```
