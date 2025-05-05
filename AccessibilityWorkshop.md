# Accessibility Workshop

- [Attendants](#attendants)
- [Workshop](#workshop)
  - [Topics](#topics)
  - [GitHub repository](#github-repository)
  - [Takeaways](#takeaways)
    
# Attendants
- Anna Condal - annac@empathy.co

# Workshop
Speaker: [Marcy Sutton Todd](https://frontendmasters.com/teachers/marcy-sutton/)
<br>
Platform: [FrontendMasters](https://frontendmasters.com/workshops/accessibility-v3/)
<br><br>
The workshop is focused on accessible coding. It starts introducing some accessibility main principles and then explores more deeply some [topics](https://web-accessibility-v3.vercel.app/topics), providing great testing & fixing code examples. Recommended mainly for frontend developers, but maybe also suitable for product owners and designers.

## Topics
### 1. Intro
The cost of inaccessibility is getting some people marginalized from using the web.
Types of disabilities: vision, movement (ex. not able using mouse, need of captions..), thinking, remembering, learning, communicating, hearing, mental health, social relationships.
Breaking the typical sighted mouse-user as a default: People interacts with computers in other different ways: switch devices (limited set of keys), braille displays, screen magnifications, head wands, mouth sticks, eye tracking technologies, by voice (where semantic HTML)... Also, accessibility is not only for screen readers users.
Accessibility overlaps with other benefits: semantic structure benefits both accessibility & *SEO* reachability; a high *performance* website is more accessible as a screen reader user can interact quicker; *security* is involved when a user cannot access to an interface without help (e.g, need to share a PIN or other personal data); *business grow* if more people can use/contract.
Standards & definitions: [WCAG](https://www.w3.org/WAI/standards-guidelines/wcag/), [ARIA](https://github.com/w3c/aria), [A11y](https://www.a11yproject.com/).
<br><br>
Further info:
- [https://a11ywins.tumblr.com/](https://a11ywins.tumblr.com/)

### 2. Screen readers
Screen readers should not be tracked in terms of privacy. Not only used by fully blind people, also used in cognitive distractability & sensitivity to light and motion. They are both software & hardware. Some computers with already built-in screen readers, also third party software can be installed ([NVDA](https://nvda.es/), [JAWS](https://www.tecnoaccesible.net/catalogo/jaws)).

#### Alt text as a basic providing accessibility for screen readers:
- Provide when necessary, skip with empty alt for decorative images.
- Hide (clip) HTML content that can markup background images, so content won't be rendered but will get accessible. Here an example to be inspected with devTools: [https://web-platform-ddeyuo.stackblitz.io/](https://web-platform-ddeyuo.stackblitz.io/).

#### Some references regarding screen readers:
- [WebAIM Surveys](https://webaim.org/projects/screenreadersurvey9/)
- [AssistivLabs](https://assistivlabs.com/)
- [VoiceOver for desktop cheat sheet, macOS users](https://dequeuniversity.com/screenreaders/voiceover-keyboard-shortcuts)
- [NVDA Keyboard shortcuts, Windows users](https://dequeuniversity.com/screenreaders/nvda-keyboard-shortcuts)
- [Talkback shortcuts, Android users](https://dequeuniversity.com/screenreaders/talkback-shortcuts)
- [W3C's Alt Decision tree](https://www.w3.org/WAI/tutorials/images/decision-tree/)

### 3. Accessibility debugging
#### Testing steps: 
   1. Use tab key to navigate through the page and check: all interactive elements are available, focus is visually reachable, there are no blocking areas (unable to escape, stuck behind a modal...), common key commands work properly (arrows, escape, space).
   2. Use a browser DevTools extension for each page state to look for accessibility violations
   3. Zoom page at least 200%: all layouts should [reflow](https://www.w3.org/WAI/WCAG21/Understanding/reflow.html) and components still usable.
   4. Test visual modes (light/dark) & Test animation & motion can be turned off.
   5. Run screen reader following cheat sheets
   6. Check missing transcripts or captions.
<br>
<br>
### 4. Accessible HTML
The basics for achieving well-structured HTML is using its inner structural semantics meaningful tags instead of only ```<div>```. Only semantic HTML will be put into the accessibility tree structure. Also, built-in components with default behaviour & accessibility granted for free (specially form involved ones).
So:
- **Headings**, ```h1```-```h6```, consider having the heading level configurable in components to always fit the tree, so, dynamic tag element. Put them in priority 1 in terms of semantic relevance to have them well implemented.
- **Landmark elements** (```nav```, ```main```, ```section```, ```header```) & use ```aria-label``` & ```aria-labelledby``` on them, as having several sections without any unique labels would be the same as having multiple divs. Some basic rule: only one ```header``` with ```role=banner```.
- **Lists** (```ul``` ```ol```) with list items as direct descendants. Lists will be counted automatically in screen readers. Take into account that Safari needs role list to announce them & don't get messed counting the lists.
- **Forms**, ```form```, ```fieldset```, ```legend```... Labels essential for ``ìnputs``, ``textareas`` in assistive technologies. 2 ways: explicit labels with ```for``` and `ìd`, implicit with labels wrapping an input.
- **Buttons and links**: Free behaviour available in HTML buttons: focusability, built-in role, keyboard & click events. Built-in behaviour in links, as history, ```href``` necessary to be keyboard-accessible. Use buttons for toggle things, links just for navigate.
- **Dialogs**
<br><br>
Important to set lang in a page to get it well-read. Page level lang can be overridden if there are fragments on other languages (use case of having some author names, toponyms, etc).

### 5. ARIA
HTML and ARIA working closely. HTML provides accessibility information based on the semantics, it affects focusability, visual style and behaviour. ARIA will affect the Accessibility Tree and Assistive Technology. Apart from the official [W3C]((https://www.w3.org/WAI/standards-guidelines/aria/)) as a source of truth, also [MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA) is a great & updated resource. And for checking accessibility support in different assistive technologies: [https://a11ysupport.io/](https://a11ysupport.io/)

#### Main ARIA building blocks: 
- **Roles**: what do things do. Notice that custom ``<button>`` HTML tag has the role=button built-in role. Types: Widget roles (interactive), document structure roles (organize content), landmark roles (special navs and landmarks), live region roles (screen reader announcements, use case: item added to shopping basket), window roles (dialogs).
- **States**: active, disabled, selected, checked...
- **Properties**: labels, descriptors, titles

### 6. Focus Management
Keyboard-only mindset as a way to test: everything that can be done with a mouse should be reachable using only the keyboard. Tab key as a keyboard testing tool. Key: Focus moves & gets restored in the right place? 
<br><br>
Skip links as a tool. Notice that "Skip to Content" and "Back to top" links are level A WCAG requirements. They should be visible on focus & target elements (matching ID) on the page to work ok. A ``tabIndex="-1"`` attribute can make doubly-sure that the element will receive focus.

#### Nice website examples with skip links:
- [target.com](https://www.target.com/)
- [github.com](https://www.github.com)

In a [tabs]((https://www.w3.org/WAI/ARIA/apg/patterns/tabs/examples/tabs-automatic/) ) panel context: Tab index is how we make tab navigation work: with 0 or positive values is how we put things in order, while '-1' will remove an element from the tab order.
<br><br>
For debugging focus: use the [activeElement API](https://developer.mozilla.org/en-US/docs/Web/API/Document/activeElement). Recommended also to use visual focus outline.

### 7. Visual Considerations
#### Color Contrast 
- Color/visual contrast as one of the main accessibility issues.
- Some tools: Axe API, WAVE, devTools pickers (Chrome, Firefox).
- AA level defines regular text 24px & below -> 4.5:1 contrast ratio.
- Non-text contrast criteria: button background colors, icon buttons, form controls... -> 3:1

#### Reflow, zoom
- Group items, so they can reflow in a single column (e.g inputs & labels)
- Responsive font size/spacing
- A web tool to test reflow: [Device Toolbar](https://developer.chrome.com/docs/devtools/device-mode?hl=es-419)

#### Reducing Motion
- ```prefers-reduced-motion``` CSS Media Query and platform setting (Mac and iOS, Windows, and Android).

#### Prefers Color Scheme
-  ```prefers-color-scheme``` CSS Media Query for styling users’ preferred light/dark mode color scheme.

#### Accessibility & Performance
- Skeleton layouts, can be used also as screen reader announcements.

## GitHub repository
[https://github.com/marcysutton/frontend-masters-web-accessibility-v3](https://github.com/marcysutton/frontend-masters-web-accessibility-v3)

## Takeaways
Some useful resources to test/fix accessibility issues:
- [axe-devtools](https://chromewebstore.google.com/detail/axe-devtools-web-accessib/lhdoppojpmngadmnindnejefpokejbdd). An accessibility testing tool. It's a browser extension available both for Chrome and Mozilla. It works similar to browser's accessibility tools, also being able to click & inspect directly the elements that need to be improved, but provides more accurate information about the accessibility tree structure (nodes, roles, accessible names, states...) of your webpage, & also highlights the HTML pieces of code involved & provides key info to solve the issues.
- [axe linter](https://www.deque.com/axe/devtools/linter/), it includes GitHub actions & other integrations.
- [VS Code extension](https://marketplace.visualstudio.com/items?itemName=deque-systems.vscode-axe-linter)
- [ESLint Plugin for React apps](https://www.npmjs.com/package/eslint-plugin-jsx-a11y)
- [Accessibility insights extension](https://chromewebstore.google.com/detail/accessibility-insights-fo/pbjjkligggfmakdaogkfomddhfmpjeni?pli=1)

For further info consider watching [Juanjo Montiel's](https://youtu.be/sdlB-On6Rfk?si=B8Nx2kvCH3mPRjjs) talk that was hold in the [WAC 2021](https://webaudioconf.com/).



