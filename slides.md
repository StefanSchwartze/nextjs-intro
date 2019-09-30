*A talk about* 
## **Next.js**
Stefan Schwartze<br/><br/>
---

## What is Next.js?
----

#### A JavaScript framework for
### Server-rendered React Apps
----

### Recap:
## Why render on the server?
----

* Earlier FCP (and possibly FMP)
<!-- .element: class="fragment" -->
* Best SEO
<!-- .element: class="fragment" -->
* Progressive Enhancement
<!-- .element: class="fragment" -->
---
 
## Things to consider
----

* Rendering
<!-- .element: class="fragment" -->
* Routing
<!-- .element: class="fragment" -->
* Data-fetching
<!-- .element: class="fragment" -->  
* Re-hydration
<!-- .element: class="fragment" -->
* Code chunking
<!-- .element: class="fragment" -->
---

## Next.js for the Resuce
----

### File-based routing

One file per page (`pages/index.js`)
```js
function Home() {
  return <div>Welcome to Next.js!</div>
}

export default Home
```
----

### Static file-serving

```js
function MyImage() {
  return <img src="/static/my-image.png" alt="my image" />
}
export default MyImage
```
----

### Simple data fetching

* Async `getInitialProps` for retrieving data

```jsx
import fetch from 'isomorphic-unfetch'

function Page({ stars }) {
  return <div>Next stars: {stars}</div>
}

Page.getInitialProps = async ({ req }) => {
  const res = await fetch('https://api.github.com/repos/zeit/next.js')
  const json = await res.json()
  return { stars: json.stargazers_count }
}

export default Page
```
----

### Automatic code-splitting

* One chunk per page
<!-- .element: class="fragment" -->
----

### Automatic pre-fetching

* Viewport-based
<!-- .element: class="fragment" -->
* Network-based
<!-- .element: class="fragment" -->
----

## How to use in production?
----

Pages can be built as:
* **σ** Server-rendered
* **⚡** Static HTML
* **λ** Functions
---

![Output](https://nextjs.org/static/blog/next-9/build-types.png)
---

## Pro-Tip: Use it with Redux!
----
* Complete state in client on pageload
<!-- .element: class="fragment" -->
* No re-rendering required
<!-- .element: class="fragment" -->
* Drawback: Increasing file size
<!-- .element: class="fragment" -->
---

## Experiences from Linus.de
----

* Uncomplicated setup
<!-- .element: class="fragment" -->
* Data-fetching is simple
<!-- .element: class="fragment" -->
* Not every page needs SSR
<!-- .element: class="fragment" -->
* Common way to do things
<!-- .element: class="fragment" -->
* Perfect in combination with Redux
<!-- .element: class="fragment" -->
---


## Sources

* [Next.js](https://nextjs.org)
* [Google Indexes and Ranks JavaScript Pages in Two Waves Days Apart](http://www.thesempost.com/google-indexes-ranks-javascript-pages-two-waves-days-apart/)