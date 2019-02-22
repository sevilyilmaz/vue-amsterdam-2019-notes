# Vue Amsterdam Conference - Day 1

## State of Vue - Evan You
- [Vue - Apollo](https://vue-apollo.netlify.com/) for server-side rendering with GraphQL
- 3.0 - All of the slots will be implicitly be scoped-slots
- The new slot syntax comes with huge performance improvements (see component update cycle [RFC](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0001-new-slot-syntax.md))

### In future
#### ES2015+ & Core
- Change detections with Proxies
- ES Modules top level API for tree-shaking 
- Introduce Maps, Sets, [WeakMaps](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap) to help simplify internal implementations
#### ES2015+ & Vuex
- async/await
- Simplify concepts by merging mutations and actions
- Class-based store API for better type integration
#### TypeScript
- Someone from VS Code is helping the Vue team to create better editor environment for VueJS
- They started to use TS on internal works
- They wanted to support TS in general
### RFCs
- Follow [@vuejs/rfcs](https://github.com/vuejs/rfcs) to see what's going to land next

## Hot Vue Topic - Guillaume Chau
- SSR Revolution - v2.6

### Before 2.6
[life cycle before 2.6](../photos/before-2.6.jpg)

### With 2.6
- From component it will be possible to call API as async operations
  - This will allow us to componentize apps with their individual actions
- State is injected after the page is rendered

create component instance - prefetch data - render - continue with every componenets ([life cycle with 2.6](../photos/with-2.6.jpg))

## Case Study: L'Oreal - Tim Benninks (from Valtech)
- L'Oreal made a goal to reduce the 3000+ websites that they have to 800. 
  - Every website that is newly created needs to have the same technology stack
  - Every tech team has the same KPIs (for scalability, security, maintainability etc.)
- L'Oreal has 60 markets that need localizations which are product first approaches
- Some KPIs that they have
  - A11y AA, no-js version, SEO, mobile first, progressively enhanced, async/lazy, fast.
- They had the following from L'Oreal: "Choose whatever package you want as long as you meet your KPIs"
- VueJS was chosen for its simplicity, with an additional advantage of Full-Stack devs and first timers could start contribute faster on the project

## The Great Minibar Challange - Jen Looper 
- She demonstrated how to use NativeScript Vue to build native mobile apps that can be used in iOS and Android
- The main feature of the app shown consisted on an image scanner to read the label and would suggest a cocktail recipe using Machine Learning
- Some resources mentioned for ML
  - [TensorFlow For Poets](https://codelabs.developers.google.com/codelabs/tensorflow-for-poets/index.html?index=..%2F..index#0) - Image classifier tutorial
  - [Kaggle](https://www.kaggle.com/) A source of open datasets that can be used on ML projects

## Modern Web Apps Performance - Filip Rakowski
- Rules for performance
  - Split your code per route
  - **Load off screen components lazily** ([lazy loading modal](../photos/lazy-loading-modal.jpg)), so the first load is as fast as possible
  - Load non-critical libraries lazily
  - Avoid bundling all 3rd party libs into one file. It's an anti pattern
- Resources mentioned on the talk:
  - [bundlephobia](https://bundlephobia.com/) - show the packages performances and alternatives
  - [Webpack Bundle Analyzer](https://www.npmjs.com/package/webpack-bundle-analyzer) to create visual dependency map
  - [import cost](https://github.com/wix/import-cost) to see the file size that will be added when you import a package
  - [Code coverage](https://developers.google.com/web/updates/2017/04/devtools-release-notes#coverage) on Chrome to find where your bundles can be split

## GraphQL + Apollo + Vue - Sara Vieira
- Apollo-queries wrap the components and the template needs to be wrapped with the result data with a slot-scope
- Slides available here: https://vue-apollo-magic.now.sh/

## Desktop applications with Vue
- An overview of packages that can be used for Desktop apps using Vue
- Can use not only [Electron](https://electronjs.org/), but [Nw.js](https://nwjs.io/) and [Vuido](https://github.com/mimecorg/vuido)

## Designing components in Vue - Damian Dulisz
- One approach to design components is **prop-based** solution
  - Has low flexibility
  - End up a lot of conditionals in the templates
  - Hard to maintain
- Slot-based solution is the best solution in most cases

## Full Stack Vue in the Era of Serverless Computing - Nader Dabit
- A glimpse on tools that AWS provides for serverless applications ([AWS Amplify](https://aws-amplify.github.io/))
- Resource: https://medium.com/@dabit3/full-stack-development-in-the-era-of-serverless-computing-c1e49bba8580

## Design Patterns for Vue - Jacob Schatz
- Vue Builder Pattern example for FormBuilder [see](https://codesandbox.io/s/rmmprvonnm)
- [vuecommander.com](https://vuecommander.com/) for the command pattern
- Recommended book: Design Patterns - Elements of Reusable Object-Oriented Software
