# VueJS Amsterdam Conference - Day 2

## Creating VueCLI plugins - Guillaume
- @vue/cli
  - Creating projects 
  - Adding plugins
- @vue/cli-service
  - Webpack config etc.

A plugin needs
- `package.json`
- `index.js` - service
- `generator.js` - generator
- `prompts.js` - install prompts
- `ui.js` (optional) - UI interactions

## Static Site Generation - Alex Kyriakidis and Rolf Haug
- Vue School has lessons about how to test Vue apps
- Googlebot uses Chrome 41 and defers the indexing of JS-based websites, so JS rich websites will have poor SEO
- You can use Nuxt.js for Server Side Rendering, but we can go full static
- Using Static Generated Sites helps increase the SEO performance and they can be served globally on CDN
- It also helps the social media services to create the rich cards easier
- To create static files in Nuxt a function that would generate static pages for every page

## Webpack - Sean Lark
- An overview on the Plugin architecture of webpack
- Webpack 5 will come with many improvements
- Resources to learn about webpack:
  - https://webpack.academy/
  - https://github.com/TheLarkInn/artsy-webpack-tour - Annotations on webpack source code
  - https://github.com/TheLarkInn/everything-is-a-plugin

## Make your Vue apps lighter by being lazy with Webpack - Eduardo San Martin Morote
- You can make Vue Apps lighter with lazy loading
- Dynamic import function
  - `const Calendar = () => import('@/components/Calendar.vue')`
- Use it anywhere except the areas that are needed initially and in the viewport
  - Modals or below fold components are good use cases
- Safe lazy load recipee
  - Local component registration
  - Local routes
- Prefetch/preload modules (they only work lazy loaded chunks)
- Vue UI has an analyzer plugin for Webpack (use `-a` for it)
- Dynamic lazy components
  ```js
  <component :is="dynamicComponent" />
  render(h) { return h(this.dynamicComponent) }

  // inside of a component method
  this.dynamicComponent = () => import('./UserCard.vue')
  ```
- [Async components docs](https://vuejs.org/v2/guide/components-dynamic-async.html)

## Writing components with Vue CLI - Thorsten Luebborg
- An overview on configurations and best practices for writing components
- It's an anti pattern to name your exported components with a hardcoded string as it could clash with the user's components, instead do:
  ```js
  Vue.component(options.HelloWorldName || 'Hello World', HelloWorld)
  ```
- Check for the environment running your plugin on your `/src/index.js` file
  ```js
  import Vue from 'vue'

  ...

  if (typeof window !== undefined
    && window.Vue
    && window.Vue === Vue){
      install(window.Vue)
  }
  ```
- Recommendations
  - Always export all components individually
  - Offer a way to install as a plugin
  - Keep the plugin customizable
  - Auto install in non-modules environments
- Repository with several comments and ticks and tricks https://github.com/chrisvfritz/hello-vue-components

## Nuxt - Greg Pollack
- [Nuxt folder structure](https://nuxtjs.org/guide/directory-structure/) might give an idea for Golem-Vue apps
- It creates the router automatically as the `.vue` files in the the *pages* folder
- Nuxt 2.4 prefetches the page assets that are linked to the page which are in the viewport
- It supports SPA and Universal apps

## Jest tests for Vue - Roman Kuba
- It started with **revue** and it's revolved into **vue-test-utils**
- [marak/faker.js](https://github.com/marak/Faker.js/) - Fake data generator
- Create a factory function (a builder) to create wrappers
- Acceptance tests
- [snapshot-diff](https://github.com/jest-community/snapshot-diff) and [jest-serializer-vue](https://github.com/eddyerburgh/jest-serializer-vue) packages that helps with snapshots
- [codeship/jest-acceptence](https://github.com/codeship/jest-acceptance) for acceptence tests

## Empowering vue js with TypeScript, Inversify and Vuex -  Quique Fdez Guerra
- Inversify helps decrease decoupling 
- Don't have logic in the view, you can create a Service to hold that logic
- Decorators for people without much knowledge of Vue to make it easier
- Tips
  - Make small components
  - Sometimes splitted components
  - Use linting always
  - Use conventions for names
  - Do Tests
  - Be continuosly changing your code and be ready to change everything

## Vuex patterns - Filipa Lacerda
- Do not use a property directly from the store, use a computed property instead 
- Use actions that dispatch actions to commit mutations, instead of committing them directly (see [here](../photos/actions-dispatching-actions.jpg)). That makes debugging easier and more concise code

## Accessibility with Vue on SPAs - Callum Macrae 
- Make the link to have the whole context, as screen readers may jump over links and would have no context.
  - A screen reader reading:
    ```html
    <a href="">link</a>
    ```
    ```html
    <a href="">see the Hello World component</a>
    ```
- Links and hidden content may be read from screen readers, especially when using max height to hide content. So be add `aria` tags if using this markup
- Avoid using on blur on events so that screen readers can interact on autocompleted forms. Removing the suggestions on blur of the form is a terrible experience for screen reader users. Make sure that pressing enter does not break so that sr can interact with that form.
- Notify the screen reader something has appeared (aria live), on notifications for instance
- Screen readers usually have a hard time with SPAs
- Automated tools to analyze accessibilty are a good first step, but they are far from fixing many issues


## Visualizations using svg, canvas and WebGL - Chris Fritz 
- https://greensock.com/gsap for animations on state transition 
- SVG is slow compared to Canvas
- Hide elements that should not be rendered rather than frequently adding/removing them 
- Cache derived values with computed properties 
- Clean up infinite loops so they don't become memory leaks
- Use requestAnimationFrame instead of an infinite recursive 
- With Canvas you want to clear the canvas rather than changing a property, so you reduce the amount of operations
- WebGL, avoid writing by hand. But an advantage is that it has 3D
