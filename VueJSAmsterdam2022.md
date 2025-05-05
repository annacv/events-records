# VueJS Amsterdam 2022

- [VueJS Amsterdam 2022](#vuejs-amsterdam-2022)
- [Attendants](#attendants)
- [Talks](#talks)
- [State of the Vuenition](#state-of-the-vuenition)
- [GETTING MORE OUT OF YOUR PINIA STORES](#getting-more-out-of-your-pinia-stores)
- [FAST STORIES POWERED BY VITE; HISTOIRE](#fast-stories-powered-by-vite-histoire)
- [THE UNWANTED STACK](#the-unwanted-stack)
- [REUSABLE WIDGETS THAT WORK!](#reusable-widgets-that-work)
- [IT'S A (TESTING) TRAP! - COMMON TESTING PITFALLS AND HOW TO SOLVE THEM](#its-a-testing-trap---common-testing-pitfalls-and-how-to-solve-them)
- [ANIMATING WITH VUE](#animating-with-vue)
- [THE NUXT WEB](#the-nuxt-web)
- [FULL STACK DEVELOPMENT WITH NUXT 3 AND NITRO](#full-stack-development-with-nuxt-3-and-nitro)
- [DEVELOPER EXPERIENCE WITH NUXT 3](#developer-experience-with-nuxt-3)
- [LOCAL STATE AND SERVER CACHE: HOW TO BALANCE THEM WITH VUE-QUERY](#local-state-and-server-cache-how-to-balance-them-with-vue-query)
- [BRIDGING THE GAP - BUILDING COMPONENTS FOR VUE 2+3](#bridging-the-gap---building-components-for-vue-23)
- [FIVE THINGS TO MOVE YOUR WEB APP TO WEB3 UNIVERSE!](#five-things-to-move-your-web-app-to-web3-universe)
- [HOW VITE CHANGES THE GAME FOR VUE AND WEB DEVELOPMENT](#how-vite-changes-the-game-for-vue-and-web-development)
- [VUE 2 TO 3 MIGRATION – A PRACTICAL JOURNEY](#vue-2-to-3-migration--a-practical-journey)
- [COMPONENT TESTING WITH VITE, VUE, AND CYPRESS](#component-testing-with-vite-vue-and-cypress)
- [EVERYTHING YOU NEED TO KNOW ABOUT WEB PERFORMANCE](#everything-you-need-to-know-about-web-performance)
- [THE MAGIC OF DX IN THE VUENIVERSE](#the-magic-of-dx-in-the-vueniverse)
- [PETITE-VUE - PROGRESSIVELY ENHANCING ANY APPLICATION?](#petite-vue---progressively-enhancing-any-application)

# Attendants

- Iván Tajes - ivant@empathy.co
- Alonso García - alonsog@empathy.co
- Abraham Pérez - abrahamp@empathy.co
- Andrea López - andreal@empathy.co
- Anna Condal - annac@empathy.co
- Beltrán García - beltrang@empathy.co
- Daniel Adrian - danieladrian@empathy.co
- Diego Pascual - diegopf@empathy.co
- Gerardo Vázquez - gerardov@empathy.co
- Guillermo Cacheda - guillermoc@empathy.co
- Iván Palleiro - ivant@empathy.co
- Javier Igleisas - javieri@empathy.co
- John Cifuentes - johnc@empathy.co
- Jose A. Cabañeros - joseac@empathy.co
- Lucía Blanco - luciab@empathy.co
- Luís Martínez - luism@empathy.co
- Manuel Cid - manuelc@empathy.co
- Manuel Navarro - manueln@empathy.co
- Mavi Fernández - mavif@empathy.co
- Victor Caballero - victorcg@empathy.co

# Talks

The event would be recommended for Frontend Engineers specially Vue.js users.

# State of the Vuenition
Speaker: Evan You - Creator of Vue.js, vite, etc.

- New versions:
	- Vitepress
	- Vuetify
	- Volar
	- Vite 3.0 (WIP):
		- node 12 deprecation → full ESM
		- SSR build defaults to ESM output 👏🏻👏🏻👏🏻
		- ESbuild used in dev and prod builds to optimise dependencies.
	- Vue Core
		- Massive patch 3.2.25~26
		- SFC Playground
			- Switching between prod/dev
			- Support SSR reproductions in browser
		- Vue 2.7
			- Build in Composition API
				- Named exports
				- Full type support
				- Similar restrictions from the @vue/composition-api plugin
			- `<script setup>`
			    - logic moved from @vue/component-compiler-utils (!! CSS injector !!!)
			    - No longer need to separately install vue-template-compiler
			- Improved TypeScript support (Moved codebase to TypeScript)
			- Timing estimated is still in flux, but should be within 2~3 months from now.
			- Modernised test setup with Vitest (same config as Vite, no need for separated config)
			- pnpm monorepo
			- Vue 2 will have 18 months of LTS after the release of vue 2.7
			- Estimated EOL for Vue 2.x: End of year 2023. Could extend if enough interest is shown by the community
		- Vue 3.3
			- Stabilize Suspense
			- Stabilize Reactivity Transform
			- SSR Improvements
				- Lazy /conditional hydration fro async components
				- Improved SSR mismatch warnings
				- Q3 2022 estimation
		- Experimental
			- Very early exploration phase
			- Solid.js inspired
			- No Virtual DOM
			- Imperative DOM initialization + accurate reactivity bindings

# GETTING MORE OUT OF YOUR PINIA STORES
Speaker: Eduardo San Martin Morote - Creator at Vue-Router at Vue.js

- Pinia holds the state of the stores, allowing the users to also access them via Pinia's object. For example:

```js
const authStore = useAuthStore()
// authStore.$state -> pinia.state.value.auth

pinia.state.value.auth.user.login //bob
authStore.$state.user.login //bob
authStore.$state.login //bob
```

- If you want to persist a Pinia store in Client Side Rendering:

```js
import {useLocalStorage} from '@vueuse/core'

const useAuthStore = defineStore('auth', {
    state: () => ({
	    user: {
		    login: useLocalStorage('pinia/user/login', 'alice'),
	    },
    }),
})

```

- New hooks for SSR: 
    - hidratate(): To to hidratate the state. 
    - skipHidrate(): Tells Pinia to skip the hydration process of a given object. This is useful in setup stores (only) when you return a stateful object in the store but it isn't really state. e.g. returning a router instance in a setup store.

# FAST STORIES POWERED BY VITE; HISTOIRE
Speaker: Guillaume Chau - Vue.js Core Team at Vue.js

- Show components in Stories
    - Organize and document
    - Showcase features and components
    - Test Components (visual regression)
    - Design System (compatible with Tailwind)
    - Component Library
- Writing Stories
    - Improve the Developer Experience
    - Make stories feel ‘native’ to the project
    - Meet the developer where he is
    - Customizable and polished
    - Be fast

    ```jsx
    <template>
        <Story title="😺">
            <Meow/ >
        </Story>
    </template>
    ```

    - Vite Native
        - Reuse the same build pipeline
        - Less time and effort setting up
        - Fast boot and instant HMR
- **Histoire**
    - Stories are useful for several reasons:
        - Organize and document components for other developers
        - Showcase different use cases covered by your components
        - Develop components in isolation
        - Test visual regressions by taking screenshots
    - Native to Vite projects
        - Idiomatic
        - Fast and light
        - Customizable
        - Great UX
    - Dynamic source
    - [Automatic design tokens with Tailwind](https://histoire.dev/guide/#art-automatic-design-tokens)
    - Dark Theme
    - Flexible controls
    - Markdown docs
    - Responsive testing
    - Variant grids
    - Fuzzy search
    - Visual regression testing

- [Histoire](https://histoire.dev/guide/getting-started.html)

- [https://github.com/histoire-dev/histoire](https://github.com/histoire-dev/histoire)

# THE UNWANTED STACK
Speaker: Maya Shavin - Senior Software Engineer at Microsoft

- Evolution of building a window:
	- Delivery/Deploying
	- Team
	- Scalability
	- Maintenance
	- Integration
- It’s about project
	- Deployment CI/CD
	- Architecture
	- Compliance
	- Platforms
- Select new cool tool
	- Priorities
	- Alternatives comparison
	- Compatibility
	- Proposal with all this collected data data
- Select new e2e test
	- speed?
	- Visual support?
	- Cross-browser support
	- Flexibility in changing test runner
	- Parallel testing?
	- Accessibility testing support?
	- How compatible is it
		- Platform Integration?
		- CI/CD integration?
		- Maintenance effort?
		- Learning effort?
	- Why is the new testing tool the solution?
		- What are the tradeoffs?
		- Developer experience?
		- Community support
		- Comparisons
		- Scalability
- Be ready for questions

- Keep the coding standard
- Use TypeScript
- Be open-minded
- create a solution, not refactor
- Understand your window nature first
- Plan your window
- Instead of why, try “What can be better?”

# REUSABLE WIDGETS THAT WORK!
Speaker: Maria Lamardo - Head of Accessibility Training and Sr Manager of Accessibility Engineering at CVS Health at CVS Health

- Accessibility tips:
    - [https://docs.google.com/presentation/d/1CHrgC5UBMvamCjQh8oCaWqkWDKBeScY9R3azDrqYRuA/mobilepresent?slide=id.g130e402a03d_0_4800](https://docs.google.com/presentation/d/1CHrgC5UBMvamCjQh8oCaWqkWDKBeScY9R3azDrqYRuA/mobilepresent?slide=id.g130e402a03d_0_4800)

    - [https://github.com/mlama007/Widgets](https://github.com/mlama007/Widgets)

# IT'S A (TESTING) TRAP! - COMMON TESTING PITFALLS AND HOW TO SOLVE THEM
Speaker: Ramona Schwering - Software Developer at Shopware
[Slides](https://speakerdeck.com/leichteckig/its-a-testing-trap-common-testing-pitfalls-and-how-to-solve-them)

- Keep doing as we do

# ANIMATING WITH VUE
Speaker: Ramona Biscoveanu - Frontend Developer at SAP

- Green Sock selling

# THE NUXT WEB
Speaker: Sebastien Chopin - Co-Founder at Nuxt

[Thread with slides](https://twitter.com/Atinux/status/1532405883929608197)

- edge side rendering
- Nuxt 3.0 ~ summer 2022:
	- Nuxt Image
	- Hibrid rendering: Server + SWR + Pre-rendering
	- Full static generation
	- Preview mode

# FULL STACK DEVELOPMENT WITH NUXT 3 AND NITRO
Speaker: Pooya Parsa - Head of Framework at Nuxt & Passionate People

- [https://nitro.unjs.io/](https://nitro.unjs.io/)

# DEVELOPER EXPERIENCE WITH NUXT 3
Speaker: Daniel Roe - Core Team Member at Nuxt

Talk about DX of Nuxt 3 and some tools like isomorphic fetch, dynamic routing and more shipped in Nuxt 3. 

[Similar video by Daniel in another event](https://portal.gitnation.org/contents/optimising-developer-experience-with-nuxt-3)

# LOCAL STATE AND SERVER CACHE: HOW TO BALANCE THEM WITH VUE-QUERY
Speaker: Natalia Tepluhina - Staff Engineer at GitLab

- [https://www.apollographql.com/docs/react/](https://www.apollographql.com/docs/react/)
- [https://github.com/DamianOsipiuk/vue-query](https://github.com/DamianOsipiuk/vue-query)

# BRIDGING THE GAP - BUILDING COMPONENTS FOR VUE 2+3
Speaker: Thorsten Lünborg - Core Team Member at Vue.js

- What is the gap:
	- write compatible code that respects breaking changes
	- write tests that can be run against both versions
	- Manage conflicting dependencies
	- decide how to bundle and publish the project
- Vue-bridge
	- [https://github.com/vue-bridge/vue-bridge](https://github.com/vue-bridge/vue-bridge)
	- [https://vue-bridge.docs.netifly.app/](https://vue-bridge.docs.netifly.app/)
	- runtime:  polyfills some bridging code at runtime 600b
	- testing: wrappers for vues test utils providing unified API
	- eslint-config: small set of helpful eslint rules
	- vite-plugin: vuite plugin providing additional optimizations at build time for edge cases
- Vue 2.7
	- Supports composition API in Vue2
	- Vue-demi @vue/composition-api no needed any more.
- Dependency issues in flat repositories
	- Workspaces in a monorepo: pnpm workspaces
- Different packages, and /src shared by symlink

[Slides](https://github.com/LinusBorg/talk-cross-compatible-vue-components)

# FIVE THINGS TO MOVE YOUR WEB APP TO WEB3 UNIVERSE!
Speaker: Tomasz Kania-Orzeł aka TKO - Head of Technology at Monterail

- Individual oriented (privacy)
- Descentralized: instead client → server  now is node ←→ node
- Optimistic UI
	- quick action on UI
	- [https://medium.com/distant-horizons/using-optimistic-ui-to-delight-your-users-ac819a81d59a](https://medium.com/distant-horizons/using-optimistic-ui-to-delight-your-users-ac819a81d59a)
- Decentralized state
	- [libp2p](https://libp2p.io/) peer-to-peer network
	- conflict free framework, solving conflicts in distributed data
- Deployment
	- [IPFS](https://ipfs.io/)
	- p2p hypermedia protocol
- Offline
	- [workbox](https://github.com/GoogleChrome/workbox)
- App Versions
	- compatibility & breaking changes
	- propagate service worker update (workbox)
	- Setup IPNS for IPFS deployments (DNS alike for distributed)
	- use Semantic Versionning
- NFTS, CRYPTO, can be scams
	- but with good tech under the hood

[Post by the author](https://dev.to/kaniaorzel/web3-what-is-this-4ko4)

# HOW VITE CHANGES THE GAME FOR VUE AND WEB DEVELOPMENT
Speaker: Alex Kyriakidis - Co-Founder of VueSchool, Team Member of Vue.js and Author of the Majesty of Vue.js at VueSchool

[Slides](https://slides.com/hootlex/how-vite-changes-the-game-for-vue-and-web-development)
[https://vitejs.dev/guide/](https://vitejs.dev/guide/)

# VUE 2 TO 3 MIGRATION – A PRACTICAL JOURNEY
Speaker: An Phan - Vue Core Team

- [https://v3-migration.vuejs.org/](https://v3-migration.vuejs.org/)

# COMPONENT TESTING WITH VITE, VUE, AND CYPRESS
Speaker: Jessica Sachs - Tech Lead at Cypress.io

- Cypress 10 update:
  - New UI
  - Component testing: allows the developer to mount a component in the browser to test its funtionality independenly from the rest of the app. [Example image](https://cypress-io.ghost.io/blog/content/images/size/w2400/2022/05/component-in-test-runner.png)
  - Ability to change browsers from within the Cypress app
- [https://fakerjs.dev/guide/](https://fakerjs.dev/guide/)
- [https://www.cypress.io/blog/2022/06/01/cypress-10-release/](https://www.cypress.io/blog/2022/06/01/cypress-10-release/)
- [on.cypress.io/component](https://docs.cypress.io/guides/component-testing/writing-your-first-component-test)
- [Github](https://github.com/JessicaSachs/)
- [Twitter](https://twitter.com/_JessicaSachs)

# EVERYTHING YOU NEED TO KNOW ABOUT WEB PERFORMANCE
Speaker: Filip Rakowski - Co-Founder & CTO at VueStorefront and creator of StorefrontUI at VueStorefront

Some tools:
- [Bundlesize](https://www.npmjs.com/package/bundlesize)
- [Lighthouse Ci](https://github.com/GoogleChrome/lighthouse-ci)
- [Partytown](https://github.com/BuilderIO/partytown)

[Slides](https://docs.google.com/presentation/d/1889qR-FbAB-DBf41-ZX-16TbH67PwyOqCK5lLnhKEpE/edit)

# THE MAGIC OF DX IN THE VUENIVERSE
Speaker: Alex Jover - Storyblok Ambassador & Founder of VueDose

- [Storyblok and nuxt ultimate tutorial](https://www.storyblok.com/tp/storyblok-nuxt-ultimate-tutorial)
- [Nuxt3 cheatsheet](https://a.storyblok.com/f/88751/x/f08e494225/cs-nuxt3.pdf)
- [Twitter](https://twitter.com/alexjoverm)
- [Github](https://github.com/alexjoverm)
- [Blog](https://alexjover.com/)

# PETITE-VUE - PROGRESSIVELY ENHANCING ANY APPLICATION?
Speaker: Alexander Lichter - Nuxt.js Core Team and Founder of Developmint and a passionate Full-Stack Developer

Introduced [petite-vue](https://github.com/vuejs/petite-vue), an alternate distribution of Vue with limited functionality, but also highly reduced bundle size. It is inspired in Alpine, a minimalistic frontend framework.

It is specially nice in cases where some basic interactivity needs to be added to a static site, without creating a complete SPA.
