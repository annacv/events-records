# Wey Wey Web 2023

- [Wey Wey Web 2023](#wey-wey-web-2023)
- [Attendants](#attendants)
- [Talks](#talks)
	- [Auditing Design Systems for Accessibility](#auditing-design-systems-for-accessibility)
	- [Building Web Applications Without a Framework](#building-web-applications-without-a-framework)
    - [TypeScript for JavaScripties](#typescript-for-javascripties)
	- [3 reasons to switch to OKLCH](#3-reasons-to-switch-to-oklch)
	- [ChatGPT and AI for web developers](#chatgpt-and-ai-for-web-developers)
	- [Discover the power of a headless CMS](#discover-the-power-of-a-headless-cms)
	- [Let's shrink the web!](#lets-shrink-the-web)
	- [Real Time Nostalgia with Web Sockets?](#real-time-nostalgia-with-web-sockets)
	- [The Future of UI Design?](#the-future-of-ui-design)
	- [Portable, secure, and lightweight: Wasm runtimes and their use-cases](#portable-secure-and-lightweight-wasm-runtimes-and-their-use-cases)
    - [3D in the web, how hard can it be?](#3d-in-the-web-how-hard-can-it-be)
    - [Lessons learned from building Session Replay, a DOM capturing product](#lessons-learned-from-building-session-replay-a-dom-capturing-product)
    - [Form follows emotion](#form-follows-emotion)
    - [Declarative Design](#declarative-design)
    - [The Future is Malleable](#the-future-is-malleable)
    - [Solving Components errors with Server Side Rendering](#solving-components-errors-with-server-side-rendering)
    - [Collaborative software with State Machines](#collaborative-software-with-state-machines)
    - [Let's get visual - Visual testing in your project](#lets-get-visual---visual-testing-in-your-project)

# Attendants
- Anna Condal - annac@empathy.co

# Talks
The event would be recommended for Frontend Engineers and UI Designers. Talks are labelled as "Everybody", "Intermediate", "Advanced" accordingly, but only few "Intermediate" talks & no advanced ones.

## Auditing Design Systems for Accessibility
Speaker: Anna E. Cook - @AnnaeCook
<br> 
Everybody
1. Accessible DS:
<br> 
All atomic parts should be accessible. If an issue happens in an atomic part, it will be scale to everywhere. At the same time if its well scaled, a fix would scale as a fix everywhere (opportunity). Some examples:
    - menu (label, at least programmatically)
    - forms informed required fields
    - info form instructions
    - color contrast in form fields, buttons...
2. Auditing DS. Ways:
    - WCAG based, A, AA, AAA. A & AA legal standards.
    - accInsights (tool) - automatic test.
    - Also a linter for accessibility in code.
    - Guided manual testing
3. What can be audited:
    - Design
    - Code /alt, headings, page titles, arias
    - Documentation -> IMB example as well doc/designed DS
    
[IBM Design Language](https://www.ibm.com/design/language/)<br> 
[Carbon Design System](https://carbondesignsystem.com/)

## Building Web Applications Without a Framework
Speaker: Simon MacDonald
<br> 
Workshop. Everybody

At the end the speaker was actually introducing a framework...what a pity.
Here some references used in the workshop: 
- https://github.com/macdonst/enhance-workshop-weyweyweb
- https://macdonst.github.io/enhance-workshop/

## TypeScript for JavaScripties
Speaker: Josh Goldberg
<br> 
Workshop. Everybody

Basic TS concepts: The 7 primitive types, all variables can be undefined or null, TS validation while dev, JS runtime...
A trick: ```^?``` would show the type of the variable (this is TS playground), also an VSCode extension (```vscode-twoslash-queries```).

Some links used around the workshop:
- [Speaker website](https://www.joshuakgoldberg.com/speaking/)
- [Learning Typescript Book](https://www.learningtypescript.com/projects)
- [Book exercices shared](https://onedrive.live.com/view.aspx?resid=D699ACCFCBD51CF5%211028625&authkey=!ACGWgq1rZ2CcERo)
- [TS lang playboard](typescriptlang.org/play)
- [9998 issue](github.com/Microsoft/Typescript/issues/9998)
- [TS error translator](https://ts-error-translator.vercel.app/)

## 3 reasons to switch to OKLCH
Speaker: Anton Lovchikov
<br> 
Everybody ---overlaps with workshop.

Some references searched:
- https://oklch.com/#70,0.1,72,100
- https://evilmartians.com/chronicles/oklch-in-css-why-quit-rgb-hsl

## ChatGPT and AI for web developers
Speaker: [Maximiliano Firtman](https://firt.dev/)
<br> 
Everybody

Related tecnologies: 
- LLM (large language model)
- GPT (generative pre-trained transformer)

- ChatGPT uses LLM.
- Code copilots GPT model.
- LLM can be used in different things, not only for large texts.
- The basics of LLM are suggestions.
- Token are the minimum character unit that LLM uses to make a suggestion.
- Everyone creating their own LLM.
- Different cloud services f() generative AI (1 model, 1 provider)
- LLM not always picks the first suggestion, it behaves with the aim to be more creative, so not all the time gets the same answer, sometimes the model is "hallucinating".
- Temperature: a variable that we can change to pick answers.
- ChatGPT browse the web -> responds with text and link to raw origin & data.
- Cannot read JSbased content, as ChatGPT browser does not execute JS.
- robots.txt -> ChatGPT-User (user agent) disallow can be set. So, you can do the same that you would do in robots.txt but pointing to ChatGPT user agent.

-> [Nice article on his web with further info](https://firt.dev/chatgpt-web/)


## Discover the power of a headless CMS
Speaker: Luis Majano
<br> 
Everybody

Traditional Content Management Systems:
- usually monolith
- ++ coupled front & back

Headless CMS: 
- Separation of concerns
- Layers can be deployed together or separated, so easier refactors.
- Body > Content > backend API
- Head > freedom to choose framework as concerns are separated
- More security.
- Content can be delivered in many platforms & monitorize content.
- [An open-source Headless CMS](https://www.contentboxcms.org/)


## Let's shrink the web!
Speaker: [Lemon](https://ahoylemon.xyz/)
<br> 
Intermediate

Assertions:
- Websites have doubled in size every three years.
- The average web page is bigger than the 1993 video game DOOM.
- There is a geographical inequality regarding speed both in desktop/mobile devices. For mobile the situation is worse at it gets involving money (consuming data, MB).
- Bounce rates of conversion fail along with the most time consumed to render resources: download speed here is also geographically biased and increases the issue per zones.

The experience of time gives users the sense that something is happening
<br>
-> Stuff that can be done to reduce the time that users have to wait and improve performance: 
- Images:
    - Photoshop -> Export save for web legacy, an interface will be opened to enable checking the time speed of the image at the same time that checking the quality, img size output can be reduced by reducing the quality a bit to reach the desired speed.
    - [sqoosh.app](https://squoosh.app/) -> More or less that can be reached with Photoshop, but in an automated process.
    - [imgBot](https://imgbot.net/) -> Idem above but using a github repo.
    - Consider using WebP format, also supports transparency.
- Text compression, 3 ways:
    - Server-side compression: Less bits over the wire with [GZIP](https://www.gnu.org/software/gzip/)
    - Bundle: 100k < (10 * 10k). This statement is less true in modern webservers with HTTP/2 where requests are divided by origin, but if GZIP compression is used having 1JS, 1CSS will make the difference as each of the files would have to be compressed & decompressed individually if they are splitted.
    - Minify: Always use minified JS libraries if possible. [prepos.io](https://prepros.io/) compiles & bundles JS, SCCS, CSS (...++file formats).
    - consider using CDN: because the CDN is probably faster than your services, your users have already jQuery (that is already caught, so no new call has to be made). Some examples:
        - [cdnjs](https://cdnjs.com/)
        - [jsdelivr](https://www.jsdelivr.com/)
        - [google hosted libraries](https://developers.google.com/speed/libraries?hl=es-419)
- Use Lighthouse to evaluate your performance improvement possibilities.
- Evaluate project's needs, if it is not so big maybe there's no need of a framework, (or check meta frameworks as next.js, nuxt.js) reduce JS & use HTML & CSS to reach same results.  

## Real Time Nostalgia with Web Sockets
Speaker: Josh Goldberg
<br> 
Everybody

The speaker built a game using ```<canvas>``` and web APIs. Enhances the power of browsers: they enable “safe” execution of arbitrary code on user machines within seconds. He argues that web development is only going to keep getting more powerful, we have reached cleaner, more expressive deploys & stacks.
<br>

Tech Specs:
- [Koa](https://koajs.com/)
- [Next.js](https://nextjs.org/)
- [Socket.io](socket.io)
- [A-Frame.io](https://aframe.io/)
- [Networked Aframe](https://github.com/networked-aframe/networked-aframe)

## The Future of UI Design
Speaker: Michal Malewicz
<br> 
Everybody

Argues the future will be 80% boring, 20% exciting. Past vs present can give clues about the future. IRC as Slack's predecessor example.

Some past milestiones: 
- First iPhone as precursor of the actual UX scenario/trends.
- [Sketch](https://www.sketch.com/) revolution as precursor of actual [Penpot](https://penpot.app/)
- The UI (Sketch) / UX (Azure) division begins to disappear with Figma.
- DS Systems: templeatization of designs -> cheaper designs.
- Skeudomorphism (texturized design) loses rellevance in favour of flat design.

Argues that now quality and creativity in design is lower due to the standarization (flat design). The argument "we can focus on flows" which is exhibited when enhancing flat design is false, thus flows are getting copied all the time also, not only the design templates.

The "go cheeper" mode ends with badly designed buttons, as standards won't fit the font architecture (different white spaces, default font height...).

Airb&b and Shopify as examples of trying to give a bit more sustance to flat designs.

## Portable, secure, and lightweight: Wasm runtimes and their use-cases
Speaker: Natalia Venditto
<br> 
Everybody

JS high level lang running in the browser, rich ecosystem.
<br> 
script --> lexical parsing --> Abstract syntaxt tree --> Compiler --> compiled at a lower level --> Machine code (bynary)
<br>
Performance is important as user's attention span has been reduced to 8".

For a long time all has been happening at client side, whatevr it happens there is affected by the performance. Metaframeworks are build on top of other frameworks to enable additional capabilities (ex server side strategies, improve performance, pass a header, rules).

[Starlight](https://starlight.astro.build/) use case.

Web assembly -> decide what can be ran at 1st (run in specific runtimes), it is a way to compile (compiler target). Binary instructions format. Allows having most of the site static, runtime efficient at low level, minimal use of client side resources. It offers a system of imports/exports in a f(). Fetch we assembky module, arrayBuffer of bites, grab & use it directly in JS. [WebAssemblyMozilla](https://developer.mozilla.org/en-US/docs/WebAssembly). Module chaining can be done.

Secure as [WASI | WebAssembly System Interface](https://wasi.dev) has no acces from the DOM or Network, you control memory save.
<br>
Trade-offs: more layers to debug, starndards are in preview (not v stable, subject to changes to evolve them), toolchanins not available in all languages (no java, x ex).


## 3D in the web, how hard can it be?
Speaker: [Sara Vieira](https://github.com/SaraVieira)
<br> 
Intermediate
<br><br>
Easier with React than in 3D.js.
- To design 3D models: [Blender](https://www.blender.org/). Open source. 
- 2 rendering engines available in Blender: EEVEE and Cycles as rendering engines, availables as opt in [Blender](https://docs.blender.org/manual/en/latest/render/index.html). Recommends [Cycles option](https://docs.blender.org/manual/en/latest/render/cycles/index.html), also see [Cycles](https://www.cycles-renderer.org/) for further info.
- File formats: GLTF binary, GLDF as JSON. Recommends GLDF.
- [React Three Fiber](https://docs.pmnd.rs), imports GLDF (```useGLTF.preload("/gameboy.gltf")```), to be rendered inside a canvas. The model is a custom f() that controls frames, positionning, returns jsx component. OrbitControls is a component imported from ```react-three/drei```
```
<Canvas>
  <Model>
  <OrbitControls>
</Canvas>
```

More doc resouces: 
- https://github.com/pmndrs/drei
- [CodeSandbox examples of drei](https://codesandbox.io/examples/package/@react-three/drei)
- [Rendering a 3D model with Next.js 13, TypeScript, React in medium](https://medium.com/@valentinagaravaglia/rendering-a-3d-model-with-next-js-13-typescript-react-three-fiber-and-react-three-drei-84476c3b6a5d)
- [Speaker repo](https://github.com/SaraVieira/blender-to-web-v3)


## Lessons learned from building Session Replay, a DOM capturing product
Speaker: Francesco Novy
<br>
Advanced
<br>
- [Sentry](https://sentry.io/welcome/)
- [Github repo](https://github.com/getsentry/sentry-javascript)
- [Session Replay](https://docs.sentry.io) -> reproduce UI user errors, debug etc


They use a fork of open source lib [rrweb](https://www.rrweb.io/). Compares a diff of before/after events status in the ```DOM```, use ```MutationObservers``` to capture + ```MonkeyPatching``` styleaheets & ```Canvas APIs``` (update behaviour of code at run-time).

Potentially intrusive, but focused on dev debug tool, no wonders see concrete text inputs of users (so replaced by **) or content that user sees.

Improvements that have been done in the tool related to:
- opt of bundle size (opt for tree shaking,
- rm unused code in the bulndle to have a smarter build),
- security (mentioned above, disabling some stuff so make it unreachable),
- compress data in order to avoid no needed network traffic, they use [fflate](https://www.npmjs.com/package/fflate) library inside a web worker (check ids to have req/resp pattern checking).


## Form follows emotion
Speaker: Isabella De Cuppis
<br>
Everybody
<br>

Argues neutral design is a lie.
<br>
2007, a turning point when Apple removes all gradients from its icons and transitions to a more flat, minimal design. Excessive ornamentation begins to be seen as a distraction.
Bauhaus, rationality, primitivism, basic geometric shapes, presumed objectivity. Nowadays, we see that there was a lot of implicit subjectivity; otherwise, it wouldn't be such a recognizable style. A bit like what happened with the UI is the revolution that the modern movement/Bauhaus represented. After the modern movement, futurism becomes relevant in an exaltation of the machine, metal, strength, industrial technology, using the example of the first Mocha coffee maker as an illustration of this futurism transferred to product design.

The overview is to exemplify that the presumed neutrality of design is a fallacy. Ideology shapes design; technology also shapes design.

Technological advancement is coupled with the "humanization" of the machine in favor of accessibility. It provides different examples of product design. The closest we get to the human body, the more technology gets humanized, for example, calculators. It discusses the need to reintegrate the UI with this humanization (neomorphism).

## Declarative Design
Speaker: Jeremy Keith
<br>
Everybody
<br>
Mindset vs languages. Midset should be aligned with the way of programming: imperative vs declarative. Design Systems embodies companies culture.

A declarative approach would use JS just for what can do & leverage the other stuff that can be done in CSS/HTML there. This can be exemplified with a button: using ```<button>``` instead of ```<div>```. The imperative mindset would use ```<div>```to gain control over the rendering, but would require some costs in terms of development (using custom ```<button>``` features, for example, handling the click event). While the declarative mindset/lang would lead on the default browser's behavior & styles. Designers tend to push to an imperative approach when ```<form>``` elements are involved.

Some CSS new options lead on a declarative mindset: ```calc()```, ```clamp()```, ```min()```, ```max()```, ```max-content```, ```min-content```, ```fit-content```, ```repeat()```, ```minmax()```. These fluent properties enable fitting into viewports and having responsive typographies & spacings. So, fluid (or declarative) design is reached by designing min & max use cases & leverage the calculations to the computers.

Examples declarative vs imperative: 
- OKLHC: declarative approach
- Tailwind, bootstrap: imperative approach.

Resources, articles:
- [Supporting Logical Properties](adactio.com/journal/19487)
- [utopia fluid responsive design](utopia.fyi)
- [Designing Intrinsic Layouts](youtube.com/layoutland)
- [Relearn CSS layout](every-layout.dev)
- [https://buildexcellentwebsit.es/](https://buildexcellentwebsit.es/)
- [https://open-ui.org/](https://open-ui.org/)


## The Future is Malleable
Speaker: Aleksandra Sikora
<br>
Everybody
<br>

Malleable Apps trend === moving from fixed apps to more fluent ones. This trend is based on:
- The assertion that "one-size-fits-all" often fits no one. 
- Empowering users to custom themselves apps, choosing features.
- Breaking the gap between tech & non-tech people on tailoring experiences.
- Solid: 1 plot or multiple plots per user: have a malleable app content into the full gateway, but only serve/set what user is really looking for.

Links:
- [stylebot.dev](https://stylebot.dev/)
- [Malleable Systems Collective](https://malleable.systems/)
- [Moldable Development](https://moldabledevelopment.com/)

## Solving Components errors with Server Side Rendering
Speaker: Simon MacDonald
<br>
Intermediate
<br>

Rehusable vs webComponents: 

Rehusable components: 
- stateful
- DOM sync
- not part of the platform

Web Components:
- Part of the platform
- rehusable
- interoperate
- accessible

** In webComponents mindset, attributes should not be used to pass content, just to modify behavior, so content should rely on slots.

Web Components are built on top of: 
- HTML Templates
- Custom Elements
- ShadowDOM

Issue 1: browsers get undefined custom elements with webComponents as they need that JS to get run.
Issue 2: shadowDOM: does not play well with native forms. Cannot extend elements other than HTMLElement. Form elements in the ShadowDOM are not considered as HTMLElement, as they are not in the same DOM (== they are a shallow copy).

Solutions: 
- via CSS : set it to hidden until it is not defined in the DOM, a bit meh
- Declarative shadowDOM. Allow rendering elements with shadow DOM using server-side rendering. Define the element as HTML element (but this is not supported in Firefox)
- Replace JS behavior by custom HTML behavior if possible (forms).
- WebComponents libraries (he is selling his own framework, Enhance, as an HTML first framework, based on a render method that uses templates).

Some refs: 
- [More about web components](https://coryrylan.com/blog/introduction-to-web-components)
- [Web Components libraries](https://github.com/web-padawan/awesome-web-components#component-libraries)

## Collaborative software with State Machines
Speaker: Laura Kalbag
<br>
Everybody
<br>

Common problems within state machines:
- Complexity
- Concurrency
- DataFlow
- Testing

State machines as a visual representation of code, s/updating state s/updating context.

Actor model - any state chart is runnning then it becomes an actor === no need to be representing it before. Invoke actors when they are powered on.

Recomanable when modeling complex system & want to have it easier to document/debug. The time you loose in the biginning you save it then as techdebt & debugging in the future.
[xstate](https://github.com/statelyai/xstate) library. Here [docs](https://stately.ai/docs).


## Let's get visual - Visual testing in your project
Speaker: Ramona Schwering
<br>
Everybody
<br>

UI issues decreases the trust in an app

Visual testing Tools: 
- [Percy](https://percy.io/)
- [VRT](https://github.com/Visual-Regression-Tracker/Visual-Regression-Tracker)
- [Chromatic](https://www.chromatic.com/)
- [Applitools](https://applitools.com/)

Speaker recommends VRT
