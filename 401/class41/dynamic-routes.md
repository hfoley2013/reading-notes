# Dynamic Routes

## Reading

* [Next.js - Dynamic Routes](https://nextjs.org/learn/basics/dynamic-routes)

## Notes

### Summary

Dynamic routes in Next.js allow you to define routes with a dynamic URL structure, which can be determined at runtime, based on the incoming request. Dynamic routes make it possible to create pages with URL patterns that contain variables or dynamic segments.

You should use dynamic routes when you need to display content that is specific to a particular item or set of items, and that content is best accessed by a unique URL.

By "content that is specific to a particular item or set of items," I mean information or data that belongs to a unique item or group of items. For example, if you have a list of blog posts on a website, each post would have its own specific content, such as a title, body, and author.

By "best accessed by a unique URL," I mean that it is easier for users to access and identify a specific item if it has its own URL. For example, having a URL for each blog post, such as "/posts/{post-id}" makes it easy for users to access and share a specific post.

For example, you might want to create a blog website where each blog post has its own URL, such as `/posts/{post-id}`. The `post-id` part of the URL would be a dynamic segment, and it would determine which blog post to display.

So, in general, **you should use dynamic routes when you want to provide users with a way to access specific items on your website through unique URLs**. This makes it easier for users to find and share the content they're looking for, and provides a better user experience overall.

![Dynamic Routes](https://nextjs.org/static/images/learn/dynamic-routes/page-path-external-data.png)
![Summary](https://nextjs.org/static/images/learn/dynamic-routes/how-to-dynamic-routes.png)

### Syntax

* To create a dynamic route, add brackets to a page (`[param]`) to create a dynamic route (a.k.a. url slugs, pretty urls, and others)
  * EX: `/post/[post-id].js`
* Any route like `/post/1`, /`post/abc`, etc. will be matched by `/post/[pid].js`
  * The matched path parameter will be sent as a query parameter to the page, and it will be merged with the other query parameters
* Need `getStaticProps` and `getStaticPaths`
  * `getStaticProps`
    * Allows you to fetch data for a specific page and make it available as a prop to the component that represents that page
  * `getStaticPaths`
    * 
* Client-side navigations to dynamic routes are handled with `next/link`
  * You have to import on each file: `import Link from 'next/link'`

### getStaticProps

`getStaticProps` is a Next.js function that allows you to fetch data for a specific page and make it available as a prop to the component that represents that page. This function is used to create static pages in Next.js, which are **pre-rendered** at build time and can be **served directly from a CDN**, providing **fast loading times** for the user.

The `getStaticProps` function is **called on the server at build time** and is used to **fetch data for the page**. The **data is then passed as a prop to the component** that represents the page. The function takes a single argument, which is an object that contains information about the current request. This object can be used to access the URL parameters and other information about the request.

```jsx
// pages/posts/[id].js

export default function Post({ post }) { // {post} is the data returned as props
  return <h1>{post.title}</h1>;
}

export async function getStaticProps({ params }) {
  // get the post data from the database or API based on the id from the URL
  const post = await getPost(params.id);

  // return the post data as a prop
  return { props: { post } };
}
```

### getStaticPaths

`getStaticPaths` is a Next.js function that is used to **generate the set of static paths for a dynamic route**. It is called during the build process to **generate the necessary HTML files for the dynamic routes**, and its return value determines the set of paths that will be pre-rendered as static pages.

Example:

```jsx
export async function getStaticPaths() {
  const posts = await getPosts();
  const paths = posts.map((post) => ({
    params: { id: post.id.toString() },
  }));

  return { paths, fallback: false };
}
```

In this example, `getStaticPaths` is used to fetch a list of blog posts and generate the set of static paths for each post. The function returns an object with two properties:

* `paths`: an array of objects, each of which represents a single dynamic route and contains the `params` that will be passed to the component for that route
* `fallback`: a boolean value that determines whether or not to fall back to client-side rendering for non-existing paths.

The `paths` array is used to generate the static HTML files for each dynamic route, so that each blog post is accessible at a unique URL. The fallback value of false indicates that there is no fallback to client-side rendering, which means that if a user tries to access a path that doesn't exist, they will receive a 404 error.

In summary, `getStaticPaths` is used to generate the set of static paths for a dynamic route and to determine the set of paths that will be pre-rendered as static pages.

### Link

`Link` accepts the following props:

* `href` - The path or URL to navigate to. This is the only required prop. It can also be an object, see example here
* `as` - Optional decorator for the path that will be shown in the browser URL bar. Before Next.js 9.5.3 this was used for dynamic routes, check our previous docs to see how it worked. Note: when this path differs from the one provided in href the previous href/as behavior is used as shown in the previous docs.
* `legacyBehavior` - Changes behavior so that child must be `<a>`. Defaults to false.
* `passHref` - Forces Link to send the href property to its child. Defaults to false
* `prefetch` - Prefetch the page in the background. Defaults to true. Any `<Link />` that is in the viewport (initially or through scroll) will be preloaded. Prefetch can be disabled by passing prefetch={false}. When prefetch is set to false, prefetching will still occur on hover. Pages using Static Generation will preload JSON files with the data for faster page transitions. Prefetching is only enabled in production.
* `replace` - Replace the current history state instead of adding a new url into the stack. Defaults to false
* `scroll` - Scroll to the top of the page after a navigation. Defaults to true
* `shallow` - Update the path of the current page without rerunning getStaticProps, `getServerSideProps` or `getInitialProps`. Defaults to `false`
* `locale` - The active locale is automatically prepended. locale allows for providing a different locale. When false href has to include the locale as the default behavior is disabled.
