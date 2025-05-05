# GitNation 2024

- [GitNation 2024](#gitnation-2024)
- [Attendants](#attendants)
- [Talks](#talks)
    - [10 Years of Independent OSS: A Retrospective](#10-Years-of-Independent-OSS-A-Retrospective)
    - [ESLint One for All Made Easy](#ESLint-One-for-All-Made-Easy)
    - [Privacy-First Architecture](#Privacy-First-Architecture)
    - [Dive Into Advanced TypeScript](#Dive-Into-Advanced-TypeScript)
    - [Install Nothing: App UIs With Native Browser APIs](#Install-Nothing-App-UIs-With-Native-Browser-APIs)
    - [AI First: Applications of the Future](#AI-First-Applications-of-the-Future)
    - [WebXR? Virtual Reality and Augmented Reality Natively on Browsers](#WebXR-Virtual-Reality-and-Augmented-Reality-Natively-on-Browsers)
    - [htmx Is Pro-JavaScript](#htmx-is-pro-javascript)
    - [Mastering Cryptography Fundamentals With Node’s Crypto Module](#mastering-cryptography-fundamentals-with-nodes-crypto-module)
    - [Forget Polygons – Gaussian Splats, the New Approach to Photorealistic 3D Graphics](#forget-polygons--gaussian-splats-the-new-approach-to-photorealistic-3d-graphics)
    - [What’s the Deal With Drizzle ORM?](#whats-the-deal-with-drizzle-orm)
    - [JS on the Big Screen: Making TV Apps](#js-on-the-big-screen-making-tv-apps)
    - [Internationalization (i18n) With AI-Powered Language Model](#internationalization-i18n-with-ai-powered-language-model)
    - [Infinite Patterns in the Digital Canvas: Unleashing Creativity With JavaScript in Algorithmic Art](#infinite-patterns-in-the-digital-canvas-unleashing-creativity-with-javascript-in-algorithmic-art)


# Attendants

- Anna Condal - annac@empathy.co

# Talks
The event would be recommended for Frontend Engineers.

## 10 Years of Independent OSS: A Retrospective
Speaker:
[Evan You](https://portal.gitnation.org/person/evan_you) - [GitHub](https://github.com/yyx990803)
----
Describes different stages that open source projects often go through: initiation, expectations, burnout, resumption, all intertwined with life events.
What it means is that development is never a linear process; rather, there are often stages of lower productivity, crises, burnout, and rest.
Composition API turning point, framework reinvented.
The project transcends him; there is a community, he cannot do everything.
Now they are improving the project in terms of performance, memory usage, and adding more features to the [DevTools](https://devtools.vuejs.org/).
Cross-framework utilities: Vite, [Volar](https://blog.vuejs.org/posts/volar-a-new-beginning), [unjs](https://unjs.io/), [Nitro](https://nitro.unjs.io/).
Finally, describes the evolution and layering of tools designed to improve the web development workflow:
- [Vite](https://vitejs.dev/) (Build Tool) provides a modern, fast development environment and optimized build process using [Rollup](https://rollupjs.org/) under the hood.
- [Rolldown](https://rolldown.rs/) (WIP, Bundler) aims to enhance the bundling capabilities with better performance and features.
- [oxc](https://oxc.rs/) Built on Top of Rolldown, offering low-level tools for code parsing, transformation, and linting, contributing to a more robust and efficient development pipeline.

## ESLint One for All Made Easy
Speaker: 
[Anthony Fu](https://portal.gitnation.org/person/anthony_fu) - [GitHub](https://github.com/antfu)
----
ESLint has introduced a new way to configure linting rules using a flat configuration file, **eslint.config.js**, as opposed to the older .eslintrc.json format. This new approach offers several benefits:
- **Explicit Native Imports**: Instead of using a JSON configuration file, the new flat config allows you to use JS (native import statements). This leads to more explicit and clear configuration.
- **Plugins as Objects**: Plugins and configurations are now imported and used directly as objects, providing more flexibility.
- **Easier Customization**: The JS-based config makes it easier to programmatically adjust settings and conditions, & set the linting rules to specific needs.

Example of old .eslintrc.json:
```
{
  "extends": ["eslint:recommended", "plugin:react/recommended"],
  "rules": {
    "no-console": "warn",
    "semi": ["error", "always"]
   }
}
```
Example of new eslint.config.js:
```
import { eslint } from "eslint";
import reactPlugin from "eslint-plugin-react";

export default [
  {
    ignores: ["node_modules/**"],
  },
  eslint.configs.recommended,
  reactPlugin.configs.recommended,
  {
    rules: {
      "no-console": "warn",
      "semi": ["error", "always"],
    },
  },
];
```

#### Migration Tool: [@eslint/migrate-config](https://www.npmjs.com/package/@eslint/migrate-config)
#### Example Config: [antfu/eslint-config](https://github.com/antfu/eslint-config)

#### New tools and utilities:
- **Inspector (`--inspect-config`)**: provides a visualization of your ESLint config, helps to get an overview, filter, and search through rules. It enhances understanding and debugging of the ESLint setup.
- **Flat Config Utils: `compose()`**: compose multiple config objects into one, making it easier to manage complex configs and share common settings across different parts of a project or across multiple projects.
- **Single Shared Config for Several Projects**: using a single shared configuration file.
- **[eslint stylistic](https://eslint.style/)**: as a formatter & linter, rather than prettier.
- **[codemod](https://codemod.com/)**: tool/library to assist with large-scale codebase refactors that can be partially automated but require human oversight & some intervention. It can be used in conjunction with ESLint for refactoring code to meet new linting rules or stylistic guidelines.


## Privacy-First Architecture
Speaker:
[Andrey Sitnik](https://portal.gitnation.org/person/andrey_sitnik) - [GitHub](https://github.com/ai) - [Evil Martians](https://evilmartians.com/)
----
#### Why and how to care about the privacy of your users?
Open Source is political. Software development always has been about principles and politics. The word “free” in [free software] does not refer to price; it refers to freedom. […]. The freedom to change a program, so that you can control it instead of it controlling you.
Talks about how some governments have used personal collected data or technologies to repress citizens (IP domains, facial recognition, stored emails...).

#### Why is privacy important?
**Mistake 1**: Google is just for better ads. False -> It is for data brokers for resell.
<br>
**Mistake 2**: This company doesn’t sell data. False -> [If data is stored it can be leaked](https://www.techtarget.com/whatis/34-Cybersecurity-Statistics-to-Lose-Sleep-Over-in-2020)
<br>
**Mistake 3**: My email is not sensitive data. False -> Big data connects different leaks. Now the security lack is based on email and location, before it was based on email and username. Google Analytics tracks connected to account (email based). GA tracks >52.6% of websites, but only c.com is invisible for GA.
<br>
**Mistake 4**: I have nothing to hide. False -> Somebody else has something to hide and to fear: example of 54-year-old teacher, Mohammad bin Nasser al-Ghamdi, received
a death sentence for tweeting mild criticism of the authorities to his 10 followers on Twitter; example of “VisionLabs’ algorithm has been used in Moscow’s facial recognition system”; example of “Proton Mail Discloses User Data Leading to Arrest in Spain”

#### What can we do?
**Step 1**: Remove GDPR popup. There is no “popup” in GDPR law -> With GDPR Popup we punish users with until they agree to give us personal data.
<br>
Consent popup is just dark design pattern: 
- Popup blocks content,
- UI is unclear,
- the biggest button is "Allow".
<br>
The real “We care about privacy” way:
- GDPR compatible analytics,
- no popup
- You ask users when you need data (for instance, in Sign Up form)
<br>
Analytics without popup:
- Page view, browsers, countries
- Traffic sources
- Track website events, campaigns from click to conversion (?utm)
- Can’t connect events with session/user ID, 
- Can’t collect social network ID for ads (Remarketing)
<br>
Some Cookieless Tracking tools:
- [Plausible](https://plausible.io/)
- [PostHog](https://posthog.com/)
- [Matomo](https://matomo.org/)
- [umami](https://umami.is/)
<br>
Deal with marketing manager asking for GA:
- You can't trust data only from opt-in users, 32-64% of users press Yes on GDPR banners.
- Popup only for EU is not an option
<br>

**Step 2**: Reduce privacy data processors: Fewer services = fewer risks.
<br>
How to reduce number of services?
- No public CDN for libs (also better performance)
- No public CDN for fonts (also better performance)
- Self-hosted tools (like analytics)
- Combine CDN and cloud.
<br>

**Step 3**: Local-First. Rich client keeps data and processing locally, the server is just for sync. Gives the example of [Notion](https://www.notion.so/es-la/product) as server-first based app vs [Obsidian](https://obsidian.md/) as local-first app.
<br>
**How to:**
<br>
**Step 1: Storage: All client’s data stores locally**. More data on the client (20-500 MB).Proper client-side database (SQLite -WASM-): for good performance, for rich query language. Why not IndexedDB?: SQLite works on ReactNative and desktop, indexedDB query API is limited, Performance.
<br>
**Step 2: Add log and separate read and write**. 
**Step 3: 2 passwords for end-to-end encryption**

#### Unexpected benefits of Local-First
- Very simple server (sync changes, auth, check access for collaboration)
- No server in prototype stage
- Cheap scale
- No private data → no problem
- Developer productivity
- Local data = 0 latency

 
## Dive Into Advanced TypeScript
Speaker:
[Luca Del Puppo](https://portal.gitnation.org/person/luca_del_puppo) - [GitHub](https://github.com/Puppo)
----
[Talk repository](https://github.com/Puppo/dive-into-advanced-typescript)
<br>
Form validation TS based talk using Typeguards:
[`expect-type` lib](https://www.npmjs.com/package/expect-type): `expectTypeOf(string).toMatchTypeOf<Something>()`:
  - [example 3](https://github.com/Puppo/dive-into-advanced-typescript/blob/main/src/solutions/03-solution.ts)
  - [example 4](https://github.com/Puppo/dive-into-advanced-typescript/blob/main/src/solutions/04-solution.ts)
  - [example 5](https://github.com/Puppo/dive-into-advanced-typescript/blob/main/src/solutions/05-solution.ts)
[Schema based validation library: `zod`](https://zod.dev/):
  - [example 6](https://github.com/Puppo/dive-into-advanced-typescript/blob/main/src/solutions/06-solution.ts)
<br>
Shared resources:
[TS tips & tricks](https://dev.to/puppo/series/11213)
[Ts tips video lessons](https://www.youtube.com/watch?v=CLSdQ7IBFOY&list=PLvenS7mPQE1GtqAVRDSXXJhrN6jW3Gf4n)


## Install Nothing: App UIs With Native Browser APIs
Speaker: 
[Scott Tolinski](https://portal.gitnation.org/person/scott_tolinski) 
----
Talk based on several examples. They can be found at: [Talk resouces](https://tolin.ski/talks/install-nothing)
<br>
#### Modals, alerts & dialogs
1. HTML `<dialog>` element + query selectors + calling showModal(). No need to code some functionality ourselves, as accessibility features provided by the system. Available in 96% browsers:
  - it applies directly on your page without having to do the `overflow:hidden` trick to prevent scrolling
  - gives you keyboard shortcuts (ex, hit esc to close it)
  - captures your focus (can start typing right away).

2. Animating with [WAAPI](https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API/Using_the_Web_Animations_API): the animation, the positioning will work with no css. It can save you from import a full animation library, which depending on the animation there's no need for that. Available in 97% browsers:
   - `window.requestAnimationFrame()` method.
   - `animate()` method.

3. [View Transitions API](https://developer.mozilla.org/en-US/docs/Web/API/View_Transitions_API): no need to apply css, by default you wrap something inside `startViewTransition` & it fades. Don't even have to program the animation on fade-out when you hit the Esc key 72% available in browsers.
   - `document.startViewTransition()`.

4. Animating with CSS:
  - Transtion behavior: [allow-discrete](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-behavior#allow-discrete): allows you to transition `display:none`. 71% coverage.
  - [@starting-style](https://developer.mozilla.org/en-US/docs/Web/CSS/@starting-style): the style of sthg before it enters the DOM. Still experimental technology.

#### Menus & Popovers
1. [Popover API](https://developer.mozilla.org/en-US/docs/Web/API/Popover_API). Can be created declaratively, via a set of new HTML attributes (`popovertarget` attr -the btn-, connected to an `id` & `popover` attrs -the content-). Accessibility features provided by the system (hit Esc) + automatically put into the top layer (no worry about the `z-index`, because of top layer). Additionally, you can define a `popovertargetaction` (show/hide). 96% available in browsers.

2. Positioning popover: Can't position it relatively because of the top layer (it set in another context). [They way: WAAPI x JS Anchor](https://tolin.ski/cool-treats/popover): Updating the position using the `getBoundingClientRect()` method & running that on resize & on scroll.

3. [CSS only w/anchor](https://developer.chrome.com/blog/anchor-positioning-api?hl=es-419). Sets `anchor-name`, then tells the thing you want to anchor how to use it. Still 48% coverage (just implemented in chrome).

#### Movile nav and drawers
1. WAAP & popover API. Can also reach the same using View Transitions API with the difference that a `view-transition-name` is given (& then the transition is done with CSS).

#### Accordions
1. Using `<details>` and `<summary>` HTML tags. It works by wrapping `<summary>` tag in `<details>`. 97,5% browsers coverage.
2. Animate using WAAP api. View Transitions are out of this kind, won't be able to reach the same slide feel until we get the starting-style and allow-discrete properties.
3. Css only: using starting-style and allow-discrete properties.
He would recommend to use a JS library to animate in this case.

#### Swippers and SlideShows
1. [CSS Scroll snap API](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_snap): [`scroll-nap-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-type) CSS property with `x mandatory` value & [`scroll-snap-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-align) prop with `start` value. Just running with a minimal JS update function each time we want to change slide. 97,7% browsers coverage.


## AI First: Applications of the Future
Speaker:
[Evan Seaward](https://portal.gitnation.org/person/evan_seaward) - [GitHub](https://github.com/evanSe)
----
Just building chatbots with AI has very limited potential. Compares to mobile first design patters, the same switch of mind should be done & go to an AI-first approach. This approach assumes that AI will evolve, prioritizes AI leads to more advances apps.
Shows a project with a llm embed, AI acts as a proactive assistant, when user talks, the transcription is happening in the browser & leads to user actions in the browser, too.


## WebXR? Virtual Reality and Augmented Reality Natively on Browsers
Speaker:
[Erick Wendel](https://portal.gitnation.org/person/erick_wendel) - [GitHub](https://github.com/erickwendel)
----
#### Tools:
- WebXR = [Augmented Reality + Virtual Reality](https://developer.mozilla.org/en-US/docs/Web/API/WebXR_Device_API) native APIs.
- A-Frame = Just an abstraction for those. Built in top of [Three.js](https://threejs.org/)
- [XR Browser](https://apps.apple.com/us/app/xr-browser/id1588029989)
- [WebXR Viewer](https://apps.apple.com/us/app/webxr-viewer/id1295998056)
- [Sketchfab models](https://sketchfab.com/3d-models)
- [mixmamo](https://www.mixamo.com/#/)


## htmx Is Pro-JavaScript
Speaker:
[Carson Gross](https://portal.gitnation.org/person/carson_gross)
----
An alternative JS library.
[https://htmx.org/](https://htmx.org/)
Makes any html tag a hypermedia control.
The four generalisations of htmx: 
- hx-post (or -get, or -put or -delete)
- hx-trigger attribute: makes it possible to trigger any action
- hx-target attribute: makes it possible to replace any element on the screen
- hx-swap: how the content should be inserted in html

Based on attributes that would perform actions, so, just HTML markup with a few extra attributes without writing JS.
[Active search example](https://htmx.org/examples/active-search/)
[Sort example](https://htmx.org/examples/sortable/)


## Mastering Cryptography Fundamentals With Node’s Crypto Module
Speaker:
[Yonatan Mevorach](https://portal.gitnation.org/person/yonatan_mevorach) - [GitHub](https://github.com/cowchimp)
----
[cryto module](https://nodejs.org/api/crypto.html)
[Advance Encryption Standard](https://docs.anchormydata.com/docs/what-is-aes-256-cbc):
`aes-256-cdc` (256-> the number of combinations, cbc block cipher mode)
- Encryption process: Plain text (original message) + key (piece of data that we pass) would provide an encryption message. Decryption would be performed accessing to that key-message.
- Crypto methods to create & decrypt a message.
- key Derivation Function: We would not use a password as a key, we would use a one way f(), it is an expensive f() expected to be run once.
- Randomness: Use random vals, not use JS math.random but `crypto.randomUUID([options])` method.
- Key Distribution Problem/ Asymetric Encryption: To avoid public key issue, use different encrypt & decrypt keys. `crypto.generateKeyPair(type, options, callback)`
- Signing & Verifying: `Sign` class (sign, update methods), `Verify` class (update, verify methods)
- Public key certificates helps to make sure the trust between 2 sources, proves that key's source is reliable. `new X509Certificate(buffer)` class.

[Talk repo](github.com/cowchimp/crypto-talk-code)


## Conquering Complexity: Refactoring JavaScript Projects
Speaker:
[Phil Nash](https://portal.gitnation.org/person/phil_nash) - [GitHub](https://github.com/philnash)
----
Sometimes JS jobs ends on managing complexity as a project increases.
Top 5 issues in JS projects: 
1. `var` instead of `let` or `const`
2. Complexity of functions too high *****
3. Sections of code commented out
4. `==` and `!=` instead of `===` and `!==`
5. unused assignments

#### What is too high? How would we measure complexity?
- Cyclomatic complexity: measures the number of paths through a function (too long loops, switch)
- Cognitive complexity: creates a score by incrementing for breaks in flow (loops/conditionals), incrementing a nesting score

<br>
A tool to check code complexity:
[SonarLint](https://www.sonarsource.com/products/sonarlint/)
<br>
Some recommendations: 
- extract a helper methods
- language features: optional chaining operators, nullish operators


#### Forget Polygons – Gaussian Splats, the New Approach to Photorealistic 3D Graphics
Speaker:
[Dylan Ebert](https://portal.gitnation.org/person/dylan_ebert)
----
[gsplat.js](https://github.com/huggingface/gsplat.js/)


#### What’s the Deal With Drizzle ORM?
Speaker:
[Dan Kochetov](https://portal.gitnation.org/person/dan_kochetov) - [GitHub](https://github.com/dankochetov)
----
[Drizzle](https://orm.drizzle.team/)
[Drizzle Studio](https://orm.drizzle.team/drizzle-studio/overview)


## JS on the Big Screen: Making TV Apps
Speaker:
[Mo Khazali](https://portal.gitnation.org/person/mo_khazali) - [GitHub](https://github.com/mojavad)
----
Native based vs web based OP systems
- ReactNative (native support of tvOS, android tv), Preact, Solid, lightningjs
- Open source for web based tv apps: T.A.L, LRUD Spatial
- tvOS, androidTV, fire, Roku

#### Considerations when developing: 
1. User Interaction:
    - based on remote control: more limited interactions compared to web or mobile (arrow)
    - focus management problem: edge cases using arrows: which element should be focused after clicking arrows --> need to configure the remote control: [react-tv-space-navigation](https://github.com/bamlab/react-tv-space-navigation)
2. Performance: minimize the number of components, reduce mount/unmount expensive computations using virtualized lists.


#### Internationalization (i18n) With AI-Powered Language Model
Speaker:
[Sintija Birgele](https://portal.gitnation.org/person/birgele) - [GitHub](https://github.com/sintijab)
----
[Source code](https://github.com/sintijab/i18n-open-ai)
HTML content types: markdown, JSON, YAML: give the precise system instructions regarding the content type to AI to translate effectively. Localisation with CMS middleware. AI API with Node.js.


#### Infinite Patterns in the Digital Canvas: Unleashing Creativity With JavaScript in Algorithmic Art
Speaker:
[Francisca Beatriz Medina Concha](https://portal.gitnation.org/person/francisca_beatriz_medina_concha) - [GitHub](https://github.com/frani-be)
----
Algorithmic Art: the exact result can be unpredictable and surprisingly complex
Programming and technology play a fundamentalist role in the creation of the work, transforming algorithms and data into visual and sensory experiences. Created works are often impossible to be generated manually. Fractals, geometric shapes, randomness...
- [p5.js library](https://p5js.org/es/) - [GitHub repo](https://github.com/processing/p5.js/tree/main)
- [Three.js](https://threejs.org/)
- [Paper.js](http://paperjs.org/)
- [Open processing](https://openprocessing.org/)
