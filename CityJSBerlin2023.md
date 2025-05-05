# CityJS Berlin 2023

- [CityJS Berlin 2023](#cityjs-berlin-2023)
- [Attendants](#attendants)
- [Talks](#talks)
	- [Centering DIVs in new and exciting wrong ways with AI?](#centering-divs-in-new-and-exciting-wrong-ways-with-ai)
	- [What You will Love about Vue in 2024](#what-you-will-love-about-vue-in-2024)
	- [One Build Tool For All Your Needs](#one-build-tool-for-all-your-needs)
	- [NuxtJS - Just Vue and a bit of magic?](#nuxtjs---just-vue-and-a-bit-of-magic)
	- [An architectural pattern on Ui library workflows with Storybook and Azure](#an-architectural-pattern-on-ui-library-workflows-with-storybook-and-azure)
	- [Funky Hardware Beats: The Story of dance-mat.js](#funky-hardware-beats-the-story-of-dance-matjs)
	- [Database Guardrails - New Age for Developers and Databases](#database-guardrails---new-age-for-developers-and-databases)
	- [Going Beyond Passwords: The Future of User Authentication](#going-beyond-passwords-the-future-of-user-authentication)
	- [Creating a WebXR Tic-Tac-Toe game without using any Virtual and Augmented Reality tools!](#creating-a-webxr-tic-tac-toe-game-without-using-any-virtual-and-augmented-reality-tools)
	- [Understanding Rendering Patterns](#understanding-rendering-patterns)
	- [Monsters of Web Performance](#monsters-of-web-performance)
	- [Controlling the Web with a PS5 Controller?](#controlling-the-web-with-a-ps5-controller)
	- [From Bias to Belonging: Creating inclusive Tech Communities](#from-bias-to-belonging-creating-inclusive-tech-communities)
	- [DIYing My Wedding The Hacker’s Way](#diying-my-wedding-the-hackers-way)
	- [How not(!) to build real-time app](#how-not-to-build-real-time-app)
	- [All things Astro](#all-things-astro)
	- [Gateway to React: the react.dev story](#gateway-to-react-the-reactdev-story)
	- [Getting up to Speed with JS Today](#getting-up-to-speed-with-js-today)

# Attendants

- Anna Condal - annac@empathy.co

# Talks
The event would be recommended for Frontend Engineers.
Main Stage talks can be watched at the (CityJS Conference channel in youTube)[https://www.youtube.com/watch?v=jOZonLbLfsE].

## Centering DIVs in new and exciting wrong ways with AI?
Speaker: (Chris Heilmann)[https://berlin.cityjsconf.org/speaker/6eTvzgPj5ZjQ9k0x1Uea3S]

It makes a critique of AIs around their -limited- ability to generate meaningful tags, that is, a lack of semantic capacity in this sense.

It states that these website boilerplates have always existed and that in the medium/long term, they end up generating buggy things. It talks about the need to have something that can work in various environments, allow customization, prioritize interactions... things that have to do with decisions not only about writing code but decisions that AI cannot achieve.

It also talks about data security, dealing with unknown content, balancing between performance and UX.

Hype-driven focus: code less, do more (discussion about when jQuery emerged and the reality that now it would be a performance and security issue); always be shipping (discussion about Tailwind); iterate, assume that things will break, it's part of the deal; know the product well to deliver what is needed; think in components, not in products; productivity = UX;

SUMMARY —→ We won't be replaced by AI if the delivery is meaningful, if it contributes more than just code (if it's not repetitive, if it's not reproducible).

AI: conversational: the results will only be as good as the questions, the generated code you don't really control where it comes from (no reliable attribution, e.g., if license, performance security issues...), it also takes some time to come up with the correct response. More useful is Stack Overflow where there is a community behind that evaluates answers, there is a discussion behind, and you can find more elements to assess the suitability of the solution.

Focus shift: write to review, the more the review, the more seniority achieved. If we only rely on ChatGPT, we will harm junior devs; who will review/teach them?

To make good use of these things, it is important not to lose context (ChatGPT doesn't have it) and document the code. It prefers Copilot over ChatGPT because Copilot doesn't lose context and "learns" from how you work, ex-code creation via prompt, using the chat to document the code you've written (without losing sight of the code).

## What You will Love about Vue in 2024
Speaker: (Alex Kyriakidis)[https://berlin.cityjsconf.org/speaker/6VrtrOEhpsqboLeckDCKDT]

- DevTools
- Nuxt’s rich modules collections, SEO, metatags, layout, nuxtDevTools
- Pinia, SSR support, TS support
- Quasar, alternative to Nuxt, Vuetify, Iconic
- FormKit
- VueUse, functions to use
- PrimeVue, ui suite (themes, components…)
- Storefront UI, ecommerce, DS
- Capasitor, compile for iOs & Android (capacitor js)
- Vuei18n, Vuetify, TresJS(3D), Nuxt UI, Historie
- Composition API - using it in no Vue apps
- Tutorials, VueSchool, VueMastery, Discord, (Newsletters)[vuejs.org/ecosystem/newsletters], Hiring app, Certification program


## One-Build Tool For All Your Needs
Speaker: (Santosh Yadav)[https://berlin.cityjsconf.org/speaker/7iGu5sq9J2t8mUfQvJqeCs]

The Nx build tool provides:
- a better development experience 
- efficient server bundling
- optimized code
- type checking
- reduce in build times
- removing dead code

With a focus on speed and adaptability, Nx supports mono-repos, making it suitable for managing large-scale projects. Offers a smart and intuitive interface that delivers precisely what developers need without unnecessary complexity.

Nx introduces concepts such as distributed task execution and distributed caching, suggesting a sophisticated approach to task parallelization and build optimization. Also allows the definition of rules for build and lint tasks, ensuring consistency in development workflows. 

## NuxtJS - Just Vue and a bit of magic?
Speaker: (Alexander Lichter)[https://berlin.cityjsconf.org/speaker/7tDqB5LY4xJjkYiLrNL034]

- Emphasis on the router, auto-imports, also on custom composables, modules
- Emphasis on the NuxtContent module, content as markdown, json, csv, writing components inside markdown
- Nitro is its server engine, used to set up endpoints & middleware on the server side, plus deployment
- Brief overview of the nuxtConfig file, very powerful, like DevTools
- useFetch() (fetch(api/myendpoint))
- End-to-end type safety
- Rendering modes, define routeRules for rendering, mix up different modes

## An architectural pattern on Ui library workflows with Storybook and Azure
Speaker: (Rodney Wormsbecher)[https://berlin.cityjsconf.org/speaker/6pWzIvBfZJDZzA3eiU591M]

Some notes/steps about NPM Package Publishing and CI/CD Workflow:
- Login to npm
- Run npm publish (regenerates the dist folder)
- Pay attention to the version of the package being published; if there are changes, update it - (information accessible on npm profile > packages, point to dist folder to upload the compiled package)
- After publishing, set up CI/CD: obtain an npm token to publish (from npm user profile, generate and configure permissions, etc.) ➔ GitHub repo > settings > add a new secret ➔ actions/secret/new repo secret
- Return to branch, update version, check workflow on push, set Node version, and configure a workflow to update the version in npm (using the generated token).
- Code coverage must be at least 80% (configured in the package.json)
- Set up Docker (copy the build and the nginx config, generate the config file) into Docker container ➔ this is done in the Dockerfile (containerized Storybook using Docker)
- Run the container and execute the npm package we created and are using in the Storybook application
- Azure Container Registry: create - use basic config. Create user & pass, switch to GitHub Action with a workflow to register and deploy (push) the Azure container (similarly, create the secret for the Azure server on GitHub and use the workflow).

## Funky Hardware Beats: The Story of dance-mat.js
Speaker: (Ramón Huidobro)[https://berlin.cityjsconf.org/speaker/1B7PzfxhR8nQhWOjxTW1Kk]

(https://github.com/hola-soy-milk/picap-dance-mat)[https://github.com/hola-soy-milk/picap-dance-mat]
It's a library that the guy has set up, connecting the keyboard inputs of a Raspberry Pi with JS code using the fetch API, enabling the Raspberry Pi to function as if it were a USB. The keys correspond to an array of tones (bytes - (Uint8Array)[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array)), creating variables in this way (translating each key from a Raspberry Pi into a conventional keyboard key), and the sounds are generated ((linux-device)[https://www.npmjs.com/package/linux-device] is the npm package used to establish this communication).

## Database Guardrails - New Age for Developers and Databases
Speaker: (Adam Furmanek)[https://berlin.cityjsconf.org/speaker/5pb38rQ9MMj8FY9cYPY0no]

As databases become more complex, their Structure also becomes more intricate. The challenge is not to get carried away by "graphing" or monitoring everything. The key is to monitor the functioning of a database, not the database itself.

- Telemetry (standard for capturing signals, metrics, logs)
- Visibility
- Application Performance Management (2to2)
- Observability (technical details, monitoring errors)

Monitoring should serve to detect bugs and unforeseen opportunities, allowing for the identification and improvement of any inefficient database system before users experience issues.

## Going Beyond Passwords: The Future of User Authentication
Speaker: (Gift Egwuenu)[https://berlin.cityjsconf.org/speaker/4NGxsyIx7eZzLd91fHg6gH]

Recital of bad passwords: 84% of breaches/thefts result from weak passwords.
[haveibeenpwned.com](https://haveibeenpwned.com/)

From the dev world, what can be done is to request certain requirements in password creation, including uppercase and lowercase letters, numbers, and symbols.

A public/private key pair is also not the solution.

Which approach? ->

- **Passwordless authentication** (something other than a password, e.g., SMS, magic links, one-time passwords = OTPs, [Auth0](https://auth0.com/))
- **Multi-factor authentication** (password, passphrase, PIN, soft or hard token, fingerprint, or other biometric data). Identity Provider Auth, SMS & Voice Multifactor auth.
- **Single sign-on authentication**: [Passkeys](https://passkeys.dev/)


## Creating a WebXR Tic-Tac-Toe game without using any Virtual and Augmented Reality tools!
Speaker: (Dwane Hemmings)[https://berlin.cityjsconf.org/speaker/7DWrGVcCAvnUyGcd8PYZ9C]

- [TicReactToe.com](https://ticreacttoe.com/)
- [modelviewer.dev](https://modelviewer.dev/) *
- [xoXR.games](https://xoxr.games/)
- Tools for creating webXR environments:
  - [aframe.io](http://aframe.io)
  - [babylonjs.com](https://babylonjs.com)
- Tools to get 3D models:
  - [clara.io](http://clara.io)
  - [sketchfab.com](http://sketchfab.com)
  - [turbosquid](https://www.turbosquid.com/)
- Tools to create models:
  - [blender.org](http://blender.org)
  - [sketchup.com](http://sketchup.com)
  - Seems like a joke, but Microsoft 3D Paint's cousin
- Create custom events:
  - [developer.vonage.com/client-sdk](https://developer.vonage.com/client-sdk)
- [xoXR.games](https://xoxr.games/), 👀 there’s a FE masters course

## Understanding Rendering Patterns
Speaker: (Atila Fassina)[https://berlin.cityjsconf.org/speaker/2ENQWa6mgoZxXoe8iVyIew]

What is slow is creating and removing elements in the DOM.

React attempts to reconcile these two realities: change and DOM rendering.

Context re-render can be painful if a small piece changes. `Memo()` is used to break this dynamic. So that a reused component is only rendered in its context (2 counters, one changes, only one is re-rendered).

One possible "solution" involves creating a pattern of observables (observer pattern) that can detect when the data changes and then execute/map the DOM. It is push-based: emits data to the consumer.

The other version is to use Signals, push-then-pull, where the producer notifies changes, and consumers pull changes. They are essentially function calls (so a declared variable does not "re-render," I would say that the ComposAPI goes in this direction??).

Almost all frameworks today use some type of Signal:

- Vue does it with `shallowRef()`
- Quick uses `useSignal()`
- Angular uses `signal()` (define const/set/update)
- Svelte uses `$state()` (define and return a getter)

React is willing to do something else, but nowadays does not have a built-in signal system, primarily relies on its virtual DOM and the concept of state and props for managing reactivity. Provides hooks like `useState`, `useEffect`, and `useContext` to manage state and side effects in a component.


## Monsters of Web Performance
Speaker: (Jamund Ferguson)[https://berlin.cityjsconf.org/speaker/4fOar9hEENnQtDp547ZFJc]

Exposes some of the reasons that can affect slowdown:

- Provides an interesting example: `flag-icon-css` with a 7MB bundle size using flags —> burn them all XD. This could be mitigated by using dynamic imports for large chunks.

- Check polyfill versions; one should be sufficient.

- Migrating frameworks is not the solution. If there's a bundle size issue, it will persist.

- CSS libraries: Stick to one; don't use more than one in the same project.

- Evaluate the percentage of CSS we are using to see which part can be eliminated (CSS render-blocking resource). Also, minify (CSS purge).

- Coexisting old code with new code can also generate significant psychodrama (ajax + HTML "jQuery" vs. ajax + JSON "Jamstack," the example given).

- HTML, JS Download, JS processing, data, render data, page ready → this is the order of things. Use the performance tool to analyze which tasks are taking more time than necessary & delay these tasks to avoid blocking the first contentful paint. —> strategies, techniques: use pre-fetching, parallelize loading data with loading JS.

- Use Performance profiler 👀 → Performance profilers are software development tools designed to help you analyze the performance of your applications and improve poorly performing sections of code, e.g., [Performance Profiling JavaScript in Visual Studio Code](https://code.visualstudio.com/docs/nodejs/profiling)


## Controlling the Web with a PS5 Controller?
Speaker: (Harshil Agrawal, @harshil1712)[https://berlin.cityjsconf.org/speaker/5DiTFWeMGh8bFR349WGLfK]

It has the limitation of not being real-time.

Check out the [WebHID API](https://developer.mozilla.org/en-US/docs/Web/API/WebHID_API),
[WebHID API GitHub](https://wicg.github.io/webhid/).

Each device has a specific ID that it uses for connection. → 👀 Check `window.navigator.getDevices()`.

## From Bias to Belonging: Creating inclusive Tech Communities
Speaker: (Josefine Schaefer)[https://berlin.cityjsconf.org/speaker/1iFYymecEnu6yzeXq6AVK2]

Differences between stereotypes (=conscious) and biases (unconscious, fueled by stereotypes). It also includes the gender aspect in companies, and paradoxically, these types of talks are usually given by women... so the group that historically experiences biases in both personal and professional life is the one most sensitized and introduces the topic into a predominantly male-dominated dev environment. Despite a good purpose... we are reproducing the bias instead.

## DIYing My Wedding The Hacker’s Way
Speaker: (Kevin Lewis)[https://berlin.cityjsconf.org/speaker/2RqqNKEDQ6HK0GE4hXIgua]

Allegory/metaphor about organizing a wedding, orchestrating an event, and managing the data.

**Fields & Layout** —> Collecting people & event data to eventually have a shopping list generator with gathered info (preferences, allergies, drink preferences) & validating attendees' phone numbers (form validation).

[Directus](https://www.notion.so/Deploy-to-prod-no-brand-50870137425f44c0aef37a54e36f2c5a?pvs=21) - backend service for wellness certifications & security lists

## How not(!) to build real-time app
Speaker: (Nikolas Burk)[https://berlin.cityjsconf.org/speaker/49NA99aYRWNCUqvgb5eVcd]

[Prisma](http://prisma.io)
[datadx.io](http://datadx.io) —> Manifesto 👀

1. **Architecting a real-time app:** App-level updates (leaving everything on the server does not scale if we have different data sources).
2. **Polling:** Server asks for updates, which can result in empty responses without data. The data refreshes if available. If there are many users, there will be multiple polls per the number of users, leading to significant traffic, resource-intensive, and it gets complex very fast.
3. **Change Data Capture:** Adding extra infrastructure, publish & subscribe to the **queue** when it receives data, still facing the dual-write problem. Some solution found using—> Debezium, prismaPulse.

## All things Astro
Speaker: (Elian Van Cutsem)[https://berlin.cityjsconf.org/speaker/3MIOZGaoBTsS6YbNuZTFOv]

- Astro suited for content heavy websites
- Any framework can be used in top of it
- Enables having components connected to js & others not: this way saves 75% performance, això diu.
- Some features, xex, Page Partials -> simple HTML, no template, no doctype

(astro.build)[https://astro.build/]

## Gateway to React: the react.dev story
Speaker: (Rachel Nabors)[https://berlin.cityjsconf.org/speaker/5MhTYAYVj6XdGicsaGoF0Y]

About the shortcomings that existed in their documentation and why they have improved it. Both for the web framework and for React Native. Very upset with this "paid" talk, it has borrowed a lot of time to other more interesting ones :/.

## Getting up to Speed with JS Today
Speaker: (Tejas Kumar)[https://berlin.cityjsconf.org/speaker/30quWeRnxjXiFh6u4Ighbx]

Opportunities to boost speed:
- Data fetching
- Rendering
- Edge computing

UiTools, Frameworks recap:
- Angular: suitable for large scale apps, noty it has been totally re-created
- Vue3: Vue2 was not typesafe, Vue3 ++type safe, async single file components + amazing data fetching, no need to have a build step, script tag. 
- React: slowest, virtual DOM ++expensive operations. React priority is dev experience. Undergoing in a big change (React Forget)[https://dev.to/usulpro/how-react-forget-will-make-react-usememo-and-usecallback-hooks-absolutely-redundant-4l68] (more than a compiler, scan code-base, outputs all automatically).
- Svelte: Compiler, not quite jsx. Outputs clean js. Class suport animations.
- Solid: Closest in syntaxt to React, it uses Signals & it's fastest. Built for performance.
- Qwik: Like Solid, but code splits+++, ++fastest.
- [Astro](#all-things-astro)
