Keep things DRY (Don’t Repeat Yourself).

Take care to choose sensible names.

# LESS

## Variables

### Naming Convention

Name variables using camel case

#### Yes

`@accentColor`

#### No

```Less
@accent-color
@accent_color
@ACCENTCOLOR
```

### Descriptive vs Semantic Names

Descriptive names describe what the variable contains (`@black`, `@accentColor`). Semantic names describe what a
variable is intended to be used for (`@linkColor`, `@backgroundColor`).

Only use descriptive names for variables in `global.less`. Semantic names should be declared within the component they 
are used.

#### Yes

```Less
// global.less
@accentColor: @config-accentColor;
@black: #1e1e1e;
...
```

#### No

```Less
// global.less
@linkColor: lighten( @accentColor, 10% );
@heroTitleColor: @config-heroTitleColor;
...
```

# Components

Break everything down into components.

Name all files by this form:

```
molecule-branding.html
organism-footer.less
```

## Twig

Keep `layout/*` files short by breaking them into components.

### Independence

Each partial should be able to stand alone logically.

#### Yes

```HTML
<!-- partial/molecule-branding.html -->

<div class="molecule-branding">
	...
</div>
```

#### No

```HTML
<!-- partial/molecule-branding.html -->

</div>

<div class="molecule-branding">
	...
</div>

<span>
```

### Outer Class

Apply the component’s name as a class (`molecule-branding`, for example) to the component’s outermost element.

#### Yes

```HTML
<!-- partial/organism-footer.html -->

<footer class="organism-footer">
	...
</footer>
```

#### No

```HTML
<!-- partial/organism-footer.html -->

<footer>
	...
</footer>
```

## LESS

Keep `global.less` short by breaking it into components.

No component less file should contain context-specific styling (put that in the less file for that context component).

Scope all variables and styles within the component’s main class ruleset (such as .molecule-branding { … }).

Add lines immediately following the component’s main class selector to redeclare descriptive variables as semantic 
variables to be used in the rest of the component’s styling. Do not use descriptive variables anywhere else in the 
component’s styling.

Keep print styling out of component stylesheets.

Keep breakpoint styling inside component stylesheets.
