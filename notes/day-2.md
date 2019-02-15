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
- Nuxt.js - something to look at
- This helps to increase the SEO results
- Since these will be static files they can be served on CDN
- It also helps the social media services to create the rich cards easier
- `yarn serve`
- To create static files in Nuxt a function that would generate static pages for every page

## Make your Vue apps lighter by being lazy with Webpack - Eduardo San Martin Morote
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

## Nuxt - Greg Pollack
- [Nuxt folder structure](https://nuxtjs.org/guide/directory-structure/) might give an idea for Golem-Vue apps
- It creates the router automatically as the `.vue` files in the the *pages* folder
- Nuxt 2.4 prefetches the page assets that are linked to the page which are in the viewport
- It supports SPA and Universal apps

## Jest tests for Vue - Roman Kuba
- it started with **revue** and it's revolved into **vue-test-utils**
- [marak/faker.js](https://github.com/marak/Faker.js/) - Fake data generator
- Create a factory function (a builder) to create wrappers
- Acceptence tests
- [snapshot-diff](https://github.com/jest-community/snapshot-diff) and [jest-serializer-vue](https://github.com/eddyerburgh/jest-serializer-vue) packages that helps with snapshots
- [codeship/jest-acceptence](https://github.com/codeship/jest-acceptance) for acceptence tests