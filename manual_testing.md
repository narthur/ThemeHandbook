---
title: Manual Testing
permalink: /manual-testing/
---

When testing a theme manually, here are some things to check.

## Categories

- Accessibility
- Aesthetics
- Functionality
- Graceful Degradation
- Performance
- Responsiveness

## Items

- Does all text meet [WCAG standards](http://webaim.org/resources/contrastchecker/)?
- Does every page and component function properly [at any screen size](https://developers.google.com/web/tools/chrome-devtools/device-mode/?utm_source=dcc&utm_medium=redirect&utm_campaign=2016q3)?
- Does the theme still function properly given any combination or extreme of user-supplied configuration values?
- What happens if the user sets all theme colors to white? Black?
- Is the site still usable without JavaScript? Without CSS?
- Does the site [validate](https://validator.w3.org/)?
- Does the site function properly in all browsers?
- Does the site function properly when accessed in a browser for the blind or the visually impaired?
- Does the site handle the extremes of content well? Lots of content? No content? Lost of icons? No icons? Etc.
- Does content jump around when [connection speed is throttled](https://css-tricks.com/throttling-the-network/)?
- Are emails linked using `mailto:` and phone numbers linked using `tel:`?
- Are small versions of large images served on mobile?

## See Also

- [External Resources](external_resources.md)
