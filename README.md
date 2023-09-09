# astro-playground

📚 Learning and exploring Astro: a static site generator but with dynamism.

> **The web framework that scales with you**
> 
> Astro builds fast content sites, powerful web applications, dynamic server APIs, and everything in-between.
> 
> -- <cite>https://astro.build</cite>


## Overview

I'm eager to continue learning web fundamentals (HTML, CSS, and JavaScript) but I'm also keen to have some amount of
automated tooling to help me build and maintain a website, especially when it comes to things like generating links,
a table of contents, and other lightly dynamic. Astro is a popular static site generator, and it looks promising for
me to learn.

**NOTE**: This project was developed on macOS for my own personal use. Your mileage may vary.


## Instructions

Follow these instructions to generate the site:

1. Pre-requisite: Node.js
    * I used version 18.12.1
2. Install dependencies:
    * ```shell
      npm install
      ```
3. Generate the site:
    * ```shell
      npm run build
      ```
4. Serve the site
    * ```shell
      python3 -m http.server --directory dist/
      ```
    * Why bother with Python? It's partly to make the point that we used Astro to generate a *static site* which is just
      a bunch of static files that can be served by any web server: Python, Node.js, Apache HTTP Server, etc. Python is
      conveniently installed on macOS and conveniently has a built-in directory-serving web server. Let's use it.
5. Explore the site
    * Open the browser to <http://localhost:8000>


## Observations

I generated this project using this awesome official Astro template:

```shell
npm create astro@latest
```

Next I want to try using the template options:

```shell
npm create astro@latest -- --template basics
```

Astro project source code is expressed as `.astro` files (called *components*). Can I use `.html`? Most templating
engines also do this like Mustache (`.mustache`) and ERB (`.rhtml`) but some have a lighter touch like Thymeleaf
(`.html`) or Django (`.html`). Here is a snippet from the Astro docs which indicates that Astro is a "Astro over HTML"
and not a "HTML with Astro" type of tool:

> Astro supports importing and using `.html` files as components or placing these files within the `src/pages/`
> subdirectory as pages. You may want to use HTML components if you’re reusing code from an existing site built
> without a framework, or if you want to ensure that your component has no dynamic features.

I found that when I run `npm run build` (which runs `astro build`) it generates an `env.d.ts` file everytime even
though I'm not using TypeScript. I agree that TypeScript type definitions files and JSDoc can be super useful even in
a JavaScript-only project, but I'm stumped about what this file is doing for me at this moment. 


## Wish List

General clean-ups, TODOs and things I wish to implement for this project:

* [x] DONE Scaffold the project.
* [ ] Do something dynamic. Can I do a table of contents, like I hoped? Also, I know Astro will build markdown files but
  I'm interested in expressing my site content in straight HTML but adorning it with some dynamic stuff like maybe `<tip>`
  or `<warning>` custom elements (or something with the same effect). What does the development experience of "authoring
  for dynamic content" look like in Astro? How much vendor-specific API do I need to attach my source code to? I know
  there are Astro components.


## Reference

* [Astro on GitHub: `withastro/astro`](https://github.com/withastro/astro)
