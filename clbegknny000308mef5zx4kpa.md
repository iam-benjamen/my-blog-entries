# What is Per-Page Layouts in Next.js?

## Introduction.

**Next.js** is a React framework that has enjoyed popularity for its features that make building web apps very fast and scalable. One of such feature is the layout component which can be used to persist components across multiple pages. For example, having a navbar or footer across many pages of a website. In this article, we take a look at per-page layouts and how to implement them.

## Understanding Layouts in Next.js

A very important style of the React library is breaking the user interface into reusable components. This philosophy makes building scalable and produced neat code. Next.js also builds on the style and introduces Layouts to share certain components across several pages. Let's see an example:

Start a new Next.js project. `npx create-next-app per-page-tutorial`

Create a folder named components.js to store our components.

The pages directory contains files that are automatically linked to a page route on our site. For example, the index.js file is linked to the "/" directory while about.js will be linked to "/about" on our website. A basic file structure of a Next.js project should look like this:

![Screenshotfrom20221122122931.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1670464546411/N4Vfh6gIu.png align="left")

We create a navbar.js file in your components directory and create a very simple navbar component to illustrate the concept of layouts.

```javascript
//components/navBar.js

export default function NavBar = () => {
	return (
    	<div>
        	<a href="/">
             	Home
            <a/>
            <a href="/about">
            	About
            </a>
        </div>
    )
}
```

To share the navbar component across, we create a layout.js file in the components folder and write the following code.

```javascript
//components/layout.js

import Navbar from './navbar'

export default function Layout({ children }) {
  return (
    <>
      <Navbar />
      <main>{children}</main>
    </>
  )
}
```

Next is to wrap our entire project with the Layout component, so that all our components can access the properties in the layout. Edit the app.js file found in the pages directory:

```javascript
// pages/_app.js

import Layout from '../components/layout'

export default function MyApp({ Component, pageProps }) {
  return (
    <Layout>
      <Component {...pageProps} />
    </Layout>
  )
}
```

This way, the layout component containing our navbar is displayed on all pages of our project. Great, right? What if we had multiple layouts?

## What is Per-Page Layouts?

Real-world applications can easily get complex and we may have a need for more than a single layout shared across the entire project. Thankfully, Next.js takes care of such situations.

Per-page Layouts is a feature in Next.js that enables us to build apps with multiple layouts easily. Next.js ships a property called `getLayout`, which allows us to define the layout on a per-page basis. Hence called `per-page layout`.

This helps to define the layout structure on each page instead of having just one layout showing up on all pages of our Next.js application. Let's see per-page layout in action. Ready?

### Per-Page Layouts in action

There are two procedures for using per-page layouts.

1.  First is to define our layout structure in the pages that need them. For example, our index page.
    

```javascript
// pages/index.js

import Layout from '../components/layout'

export default function Page() {
  return (
    <div>
    	<p>Home Page</p>
    </div>
  )
}

Page.getLayout = function getLayout(page) {
  return (
    <Layout>
     	{page}
    </Layout>
  )
}
```

2.  We then tell our \_app.js file to use the layouts in the individual pages if they are specified.
    

```javascript
// pages/_app.js

export default function MyApp({ Component, pageProps }) {
  // Use the layout defined at the page level, if available
  const getLayout = Component.getLayout || ((page) => page)

  return getLayout(<Component {...pageProps} />)
}
```

Simple, right? This gives us freedom in case of more complex or multiple layouts, we can even have nested layouts in our components.

```javascript
// pages/index.js

import Layout from '../components/layout'
import SomeLayout from '../components/some-layout'

export default function Page() {
  return (
    <div>
    	<p>
            Page with nested layout
        </p>
    </div>
  )
}

Page.getLayout = function getLayout(page) {
  return (
    <Layout>
      <SomeLayout>{page}</SomeLayout>
    </Layout>
  )
}
```

Here, we import another layout called `SomeLayout` and nest it in our predefined `Layout`. Depending on the need of out application, Next.js provides a robust and scalable means of building user interfaces.

## Conclusion

Next.js offers so much in terms of developing scalable web applications. In this article, we have discussed `per-page layouts`. I hope you have gained a robust understanding of the concept. If you made it this far, your comments and suggestions are welcome. Cheers!