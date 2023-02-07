# In Class Notes: NextJS Application

* `npx create-next-app@latest <name-of-project> --javascript --eslint`
* Use all defaults (enter, enter, enter)
* Install Tailwinds CSS
  * `npm install -D tailwindcss postcss autoprefixer`
  * `npx tailwindcss init -p`
  * NOTE: Make sure to install in the project directory
* In `tailwinds.config.js`
  
  ```jsx
  /** @type {import('tailwindcss').Config} */
  module.exports = {
    content: [
      "./app/**/*.{js,ts,jsx,tsx}",
      "./pages/**/*.{js,ts,jsx,tsx}",
      "./components/**/*.{js,ts,jsx,tsx}",
  
      // Or if using `src` directory:
      "./src/**/*.{js,ts,jsx,tsx}",
    ],
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

* To create the new page
  * In `pages`, create a new `js` file: `pageName.js`
    * EX: `careers.js`
  * Inside the new `js` file, write your functional components and links to other pages

  ```jsx
  import Link from 'next/link`;

  export default function Careers() {
    return(
      <div>
        <h1>Careers Page Coming Soon</h2>
        <Link href="/">Home</Link>
      </div>
    );
  };
  ```

  * Add `className` styling with TailwindCSS as you go
    * Can create **high order components** to create classes of components with defined styling
      * Read: [Reusable React Components in Tailwind](https://www.smashingmagazine.com/2020/05/reusable-react-components-tailwind/)
