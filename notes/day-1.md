# Vue Amsterdam Conference - Day 1

## State of Vue - Evan You
- [Vue - Apollo](https://vue-apollo.netlify.com/) for server-side rendering with GraphQL
- 3.0 - All of the slots will be implicitly be scoped-slots
- The new slot syntax comes with huge performance improvements (see component update cycle [RFC](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0001-new-slot-syntax.md))

### In future
#### ES2015+ & Core
- Change detections with Proxies
- ES Modules top level API for tree-shaking 
- Maps, Sets, [WeakMaps](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap) help simplify internal implementations
#### ES2015+ & Vuex
- async/await
- Simplify concepts by merging mutations and actions
- Class-based store API for better type integration
#### TypeScript
- Someone from VS Code helping the Vue team to create better editor environment for VueJS
- They started to TS internal works
- They wanted to support TS in general
### RFCS
- Follow [@vuejs/rfcs](https://github.com/vuejs/rfcs) to see what's going to land next

## Hot Vue Topic - Guillaume Chau
- SSR Revolution - v2.6

### Before 2.6
[life cycle before 2.6](../photos/before-2.6.jpg)

### With 2.6
- From component it will be possible to call API as async operations
-- This will allow us to componentize apps with their individual actions
- State is injected after the page is rendered

create component instance - prefetch data - render - continue with every componenets ([life cycle with 2.6](../photos/with-2.6.jpg))

## Case Study: L'Oreal - Tim Benninks
- L'Oreal made a goal to reduce the 3000+ websites that they have to 800. 
-- Every website that is newly created is need to have the same technology stack
-- Every tech team has the same KPIs (for scalibility, security, maintainability etc.)
- L'Oreal has 60 markets that need localizations which are product first approaches
- Some KPIs that they have
  - A11y AA, no-js version, SEO, mobile first, progressively enhanced, async/lazy, fast.
- "Choose whatever package you want as long as you meet your KPIs"

## The Great Minibar Challange - Jen Looper 
- Nativescript Vue to build native mobile apps that can bu used in ios and android

## Modern Web Apps Performance - Filip Rakowski
- Basically off screen components can be downloaded dynamically ([lazy loading modal](../photos/lazy-loading-modal.jpg))
- [bundlephobia](https://bundlephobia.com/) - show the packages performances and alternatives
- [Webpack Bundle Analyzer](https://www.npmjs.com/package/webpack-bundle-analyzer) to create visual dependency map
- [import cost](https://github.com/wix/import-cost) to see the file size that will be added when you import a package

## GraphQL + Apollo + Vue - Sara Vieira
- Apollo-queries wrap the components and the template needs to be wrapped with the result data with a slot-scope

## Designing components in Vue - Damian Dulisz
- prop-based solution
  - low flexibility
  - a lot of conditions in the templates
  - hard to maintain
- slot-based solution is the best solution in most cases

## Design Patterns for Vue - Jacob Schatz
- [vuecommander.com](https://vuecommander.com/) for the command pattern
- Vue builder pattern example [see](https://codesandbox.io/s/rmmprvonnm)

