# CityJS London 2024

- [CityJS London 2024](#cityjs-london-2024)
- [Attendants](#attendants)
- [Talks](#talks)
	- [The Alleged End of node.js is Much Ado About Nothing](#the-alleged-end-of-node.js-is-much-ado-about-nothing)
	- [Event Sourcing for JS Devs](#event-sourcing-for-js-devs)
	- [Micro-frontends discovery](micro-frontends-disovery)
	- [Vue Fortified: Best Practices for Web App Security](#vue-fortified-best-practices-for-web-app-security)
	- [Changed Rules: Architectures with Lightweight Stores](#changed-rules-architecture-with-lightweight-stores)
	- [AI in Front-End Dev: Your Creative Partner or Job Snatcher?](#ai-in-front--end-dev-your-creative-partner-or-job-snatcher)
	- [Gen AI for web developers](#gen-ai-for-web-developers)
	- [A nerdy guide to the web trending concepts](#a-nerdy-guide-to-the-web-trending-concepts)
	- [Redefining Module Federation in 2024: Beyond Webpack](#Redefining-Module-Federation-in-2024:-Beyond-Webpack)
	- [The Best TypeScript Features You're Not Using](#the-best-typeScript-features-you-are-not-using)
	
# Attendants

- Anna Condal - annac@empathy.co

# Talks
The event would be recommended for Frontend Engineers.
Main Stage talks can be watched at the (CityJS Conference channel in youTube)[https://www.youtube.com/watch? AFEGIR ENLLAÇ].

## The Alleged End of node.js is Much Ado About Nothing
Speaker: (Matteo Collina)[https://london.cityjsconf.org/talk/2jrZbcnpODr9UDkLMmMkDA]
Main Auditorium
----
15 years since Node.js. According to Stack Overflow, it's the most popular technology. It solved software reuse at scale. No one else did. If you're not on npm, you don't exist. Usage growth +50% yearly.

Some statistics to illustrate that it's a thriving technology:

Commits and PRs: The number of PRs remains stable.
Issues: Average response time for security issues is 2 hours, very impressive.
Matteo highlights that developers sometimes don't update versions promptly, skipping versions like 18, updating from 16 to 18 directly, showing rapid response to security alerts and issues.

**Latest features shipped:**
- Not single thread anymore.
- fetch
- promise specific API,
- watch mode
- AsyncLocalStorage
- webCryptos
- permission system (still experimental),
- testing,
- [require(esm)](https://joyeecheung.github.io/blog/2024/03/18/require-esm-in-node-js/)
- WebSocket

## Event Sourcing for JS Devs
Speaker: (Tejas Kumar)[https://london.cityjsconf.org/talk/5inItJ9WyJHL7u0LuWJkFo]
Main Auditorium

Event sourcing (how did we get there) vs event driven architect (what is the current state).
Event sourcing, state derived from events. Current state as a consequence of state.
Domain driven design - the base of event sourcing.
Powerful as enables debugging easy based on the events fired.

**Use cases:**
- Git is the gold standard of event sourcing
- redux could be
- x-components it is so

#### Where events can be stored:
- eventStore.
- [RAM (doesmydatafitinram?)](https://yourdatafitsinram.net/)
- Snapshots.

[Talk repo](https://github.com/TejasQ/cityjs-london-2024/tree/trad)
[Talk](https://www.youtube.com/live/dDUwsJQ_Nu4?t=4765s)

## Micro-frontends discovery
Speaker: (Luca Mezzalira)[https://london.cityjsconf.org/talk/564JUf2so86cjqcEbQPE7q]
Main Auditorium

**Resources:**
- (github.com/awslabs/frontend-discovery)[github.com/awslabs/frontend-discovery]
- (github.com/awslabs/frontend-discovery-service)[github.com/awslabs/frontend-discovery-service]

microservices.io
Challenges:
- discover new versions
- de-risk deployment
- fallback alternatives

AWS's Module Federations: schema to identify each micro-frontend and specify which module consumes each front.
aws's Deployment section added to manage its relevance, destination.

## Vue Fortified: Best Practices for Web App Security
Speaker: (Ramona Schwering)[https://london.cityjsconf.org/talk/6sdpTIw75yFzqcBMYg3rrH]
Education Centre

1st protection rule: Some parts of the app shouldn't be accessible o people.

* OWASP top 10.
- Authentication error validation: wrong username or password (so specifying one of each is wrong is like giving a key to the attacker)
- Protect agains autoinjection files (inputs): no use non-trusted content (template) implies controlling what is coming from user input, not using it by default in html binding (v-html, ex).
- &quot
- Protect against url injection, some libs can be used to sanitize, or do it in home.
- Protect against style injection: only allow for certain styles (backgr color, color, but no display styling).
- Protect against JS injection: no allow events nor script sect to be prov
- keep dependencies updated, minify outdated ones

## In 2024, was Airbnb wrong to ditch React Native?
Speaker: (Mo Khazali)[https://london.cityjsconf.org/talk/2aR4BIXU2FA7kJEP4DgDnK]
Education Centre

Relaunched to solve some issues/challenges:
R Native replaces the reactDom by app registry auth
UIView the native layer for android
RN = JS layer + native layer
++ relevant companies using it (meta, amazon, MS, shopify...)

RNative to create universal apps: want to make apps also for more devices. html css importable from `react-strict-dom`.
Re.Pack enable micro-frontends for mobile, webpack based.
Metro

## Changed Rules: Architectures with Lightweight Stores
Speaker: (Manfred Steyer)[https://london.cityjsconf.org/talk/5lh5EmSRGG4pazczofPSG1]
Education Centre

Questions big stores like Redux, suggesting lightweight stores.
Only store methods & sync/async actions:
- Baseline architecture.
- Store size and placement.
- Global vs Local stores.
- Prevent cycles, redundancies, and inconsistencies.
- Solid.js as lightweight store

1. Baseline architecture
Apps divided by business domains -> modules with each features based on smart components. With its own data & utilities. This prevents the interdependence that can break and lose control of the code. They do not impact each other, the different modules/business domains would be autonomous and do not affect each other.

2. How large should it be
One big store (source of true Redux) vs several lightweight stores, one per feature, + sub-features.

3. Where put them
Everywhere: component vs module, exposed vs hidden...
Data level vs feature level. Discussion:
- store can live in a component level (store x component, local state), - store per feature (x-modules),
- shared state among several feature -data level-,
- not very freqüent but a store could be on a utility level, xex authentication;
- in a Dump component, xex schedule component with all dates available etc

4. Global vs Local
Some stores may need to be in diff levels: feature service with utility store + feature store + auth store

5. cycles, redundancies & inconsistencies
Think about it in terms of layering, prevent stores accessing each others (prevent cycles), devTools where we have each data to check for redundancies/inconsistencies

## AI in Front-End Dev: Your Creative Partner or Job Snatcher?
Speaker: (Alexa Spalato)[https://london.cityjsconf.org/talk/525hZQJtC8jzHDT9qSUB4j]
Education Centre

Some tools:
- cursor.sh
- pieces.app
- sourcegraph

learing with ai
- gpts as tutor
- navigating documentation

building apps and careers
- ai driven solutions
- run own saas
- ai engineer: new learning path: ML basics + importance of LLMs (large lang models)

AI apis. 
OpenAI, Anthropic, Gemini, Hugging Face

[latent.space/p/ai-engineer](https://latent.space/p/ai-engineer)


## Gen AI for web developers
Speaker: (Roy Derks)[https://london.cityjsconf.org/talk/51Lr3BdcSI00jm1gkoSPPr]
Main Auditorium

2016 based in answering questions related to machine learning, math, data science, statistics. Still based on this but breaking the brecha of knowledge around these areas to be able to use it. 
Based on LLM models, you don't need to interact directly with these models.

LangChain, OpenAi, watsonX
Multiple patterns to go from a question to an answer.
- Prompt engineering
- Few-shot Prompt (adding examples of response, interpellating as an expert of an x area): question + instructions
- Retrieval Augmented Generation: adding additional context: question + context

(promptingguide.ai)[https://promptingguide.ai]

## A nerdy guide to the web trending concepts
Speaker: (Daniel Afonso)[https://london.cityjsconf.org/talk/5Ke8PlUN8ZwswkDhWXuMhn]
Main Auditorium

**Fine-Grained Reactivity**
Reactivity: Watch for when a specific event happens, and react to data changes by firing other events/dispatching actions. Signals (emitters with getters & setters), effects (functions that will subscribe to these signals, ex createEffect -Solid.js, React.js-).
Fine-Grained Reactivity: + Memos: allow to cache derived values (Watch for event derivations): more expensive events, depends on the original ones. Implicit effects.

**Hydration**
Hydration is the process of taking a server-rendered HTML page and converting it into a fully interactive application on the client-side by attaching event handlers and initializing JavaScript components. This is a crucial step in modern web applications that utilize server-side rendering (SSR) for improved performance and SEO benefits. During hydration, the static HTML is "hydrated" with the necessary JavaScript to make it dynamic, thus making the page fully interactive. This process ensures a smooth transition from server-rendered content to client-side interactivity without the need for a complete re-render. Challenges with hydration include ensuring the server-rendered HTML matches the client-side components, managing state between the server and client, and optimizing performance to avoid delays in interactivity.

**Resumability**
Serialises info, waiting for the pages being interactive. (during hydration -slow-). When cli requests a page, it gets immediately interactive thanks to this serialisation (rebuilds page info before response)

## Redefining Module Federation in 2024: Beyond Webpack
Speaker: (Zack Jackson)[https://london.cityjsconf.org/talk/3kOefiqh7vmWf5sntbBrOj]
Main Auditorium

[https://module-federation.io/](https://module-federation.io/)
<br>
Each of these tools serves a specific purpose in the JavaScript ecosystem, and choosing the right one depends on your project's needs, whether it’s the flexibility of micro-frontends, the need for optimized library bundling, or the desire for a rapid development workflow:
<br>
**Module Federation**: Focuses on runtime module sharing for micro-frontend architectures. Best for large-scale applications with independently deployable parts. Focuses on efficient module sharing and loading at runtime.
**Rollup**: Primarily used for bundling libraries and optimizing builds with tree shaking. Suitable for creating optimized libraries and applications. Produces optimized, smaller bundles through tree shaking.
**Vite**: Optimizes development experience with instant server start and HMR, leveraging native ES modules. Ideal for modern web development, offering a fast and efficient development server. Excels in development speed and efficiency, with fast build times and HMR.

## The Best TypeScript Features You're Not Using
Speaker: (Josh Goldberg)[https://london.cityjsconf.org/talk/2Digc6v7JlCkXDkDucEJ5X]
Main Auditorium

IDE Integrations
**++ Configurability: from weakly typed to strongly typed, can be configured**
TS Config file: compilerOptions: 
- { "noImplicitAny": true }: force to explicitly type
- { "strictNullChecks": true }: arg string | null not assignable to string
- { "strict": true } will put the above options to true

**type safety edge cases:** 
Throw is not type safe error (in try/catch) -> tell type of the error
Arrays: unchecked indexed access: noUncheckedIndexedAccess too restrictive in his opinion

Prevent too wide a type declaration: use satisfies to ensure a value fits without widening the value type
Prevent misspelling in type params; use NoInfer to stop a param inference to catch that errors.

**Type checked linting: TSLint**
combines formatting, linting, type checking.
example: detect incorrect async code. (rule typescript-eslint/await-thenable: error)

use **Knip** to check if unused code used in file vs used in whole code knip.dev


