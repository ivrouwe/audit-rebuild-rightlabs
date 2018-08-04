# (Draft -- In Progress) audit-rebuild-rightlabs
Providing solutions to increase the accessibility, performance, and SEO of RightLabs' website using web standards and industry-recommended best practices

## Methodology

I audited [RightLabs' home page](https://rightlabs.com/) using Google Chrome's "Audits" panel, [the aXe accessibility extension for Chrome](https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd), [WebAIM's WAVE Web Accessibility Evaluation Tool](https://wave.webaim.org/), [the HTML5 Outliner extension for Chrome](https://chrome.google.com/webstore/detail/html5-outliner/afoibpobokebhgfnknfndkgemglggomo?hl=en), [Google's PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/), and [Think With Google's Test My Site](https://testmysite.thinkwithgoogle.com/).

I will be summarizing the results of these audits, along with proposed solutions, in the "Areas For Growth" section below. Where relevant, I will be including quotes from people in the industry to offer further explanation for the solutions I've proposed.

## Areas For Growth

### 1. Accessibility

#### 1. Mobile Navigation Is Not Keyboard-Accessible, and That Same Navigation Has Spotty Keyboard Accessibility In Wider Viewports

##### Why This Is A Problem

* Users who rely on a keyboard are unable to properly access the website's navigation. In order to uphold RightLabs' goals of "creat[ing] user oriented accessible websites" and "[living] by the design principle of 'don’t make me think'", this needs to be fixed.

##### Possible Solution(s)

* _On mobile:_ the menu toggle button can be converted into a `<button>` element with the correct aria attributes and values. Clicking the button (via keyboard or mouse) will adjust the appropriate attribute values on the `<button>` and toggle the `hidden` property of the adjacent `<ul>`. Submenu heading text nodes can be wrapped in `<button>`s; when those `<button>`s are clicked, the adjacent content is toggled.
* _For wider viewports:_ a throttled event listener can be used to listen for changes to the viewport width. If the viewport width crosses its assigned threshold, the new menu toggle `<button>` can be hidden (or shown), and the `hidden` property can be removed (or added) to the adjacent content. CSS media queries can be used to hide submenu `<button>`s (except when focused) in wider viewports, and the `:hover` pseudo selector can be used to allow mouse users equivalent access to the submenus (for them, the submenu toggle `<button>`s would not be visible) 

(In Progress; To Be Continued)
