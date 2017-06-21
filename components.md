# Components

## Layers

Components are grouped into three distinct layers:

- **Atoms:** "The foundational building blocks that comprise all our user interfaces. These atoms include basic HTML elements 
like form labels, inputs, buttons, and others that can’t be broken down any further without ceasing to be functional."
- **Molecules:** "Relatively simple groups of UI elements functioning together as a unit. For example, a form label, search 
input, and button can join together to create a search form molecule."
- **Organisms:** "Relatively complex UI components composed of groups of molecules and/or atoms and/or other organisms. These 
organisms form distinct sections of an interface."

(Definitions taken from *Atomic Design*, by Brad Frost, [chapter 2](http://atomicdesign.bradfrost.com/chapter-2/).)

## Benefits

Breaking themes into components several benefits:

- It becomes clear where to look to find all the Less or Twig source related to any given component.
- Components become more portable, as using a component architecture forces a clear separation between the source code of one
component and another.
- This clear separation between components makes modifying a single component easier, as it allows for the assumption that the
source of one component will not affect any other component outside its context.

## File Structure

Each component has a name in the form of `.layer-componentIdentifier`. (For more information on naming components, see 
[naming_things.md](https://github.com/SimpleUpdates/ThemeHandbook/blob/master/naming_things.md).) This name is used for a 
component's Twig partial, Less file, and base CSS classname.

All component Twig partials are placed in the theme's `partial/` folder. All component Less files are placed in the theme's
`style/` folder, and included at the end of `global.less`, grouped by layer, within `.su_bootstrap_safe`, if the theme uses it.

```Less
// Variable declarations ...

.su_bootstrap_safe
  // Global CSS ...

  @import "styleguide";

  @import "atom-button";
  @import "atom-search";

  @import "molecule-branding";
  @import "molecule-breadcrumbs";
  @import "molecule-carousel";
  @import "molecule-nav";
  @import "molecule-icons";

  @import "organism-footer";
  @import "organism-navBar";

  @import "custom";
}
```

Note that, even though each component Less file filename should end with `.less`, it's not necessary to include the 
extension when importing the file in `global.less`.

## Smells

If you notice any of the following in a theme, it's likely that the theme hasn't been broken into components properly.

- **A component's Less file contains CSS that's only relevant in a specific context.** A component's Less file should only
contain CSS that would be relevant to it no matter where in a theme it's used. Whenever you see CSS in a component's Less file
that relates to its use in an ancestor component, that CSS should be moved into its ancestor's Less file.
- **A component's Less file or Twig file is not wrapped with its primary class.** In order to keep components as portable as
possible, it's useful to apply the component's primary class name (in the form of `.layer-componentIdentifier`) to its 
outermost element, and to wrap everything in its Less file, including variable declarations, with the same class. This practice
increases the confidence we can have that a given component's CSS will only ever affect its intended component.
- **A component's CSS references variables not declared in the same file.** Generally, by redeclaring any global variables
within the component's primary class scope, and only using those redeclared variables in the component's CSS, the component is
made more portable and easier to customize. (For more information on naming these redelcared variables, see 
[naming_things.md](https://github.com/SimpleUpdates/ThemeHandbook/blob/master/naming_things.md).) One exception to this rule is
global breakpoint variables (e.g. `@screenSmMax`), which should be referenced without being redeclared. 