Keep things DRY (Don’t Repeat Yourself).

Take care to choose sensible names.

## LESS

Keep `global.less` short by breaking it into components.

No component less file should contain context-specific styling (put that in the less file for that context component).

Scope all variables and styles within the component’s main class ruleset (such as .molecule-branding { … }).

Add lines immediately following the component’s main class selector to redeclare descriptive variables as semantic 
variables to be used in the rest of the component’s styling. Do not use descriptive variables anywhere else in the 
component’s styling.

Keep print styling out of component stylesheets.

Keep breakpoint styling inside component stylesheets.
