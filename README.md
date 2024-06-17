# Material for MKdocs CSS Tweaks
CSS Tweaks made to Material for mkdocs that I re-use in all sites.

Want to submit your ideas or request another style, please submit an [issue](https://github.com/TJohnson93/mkdocs-material-tweaks/issues).

---

# CSS Tweaks

Add the below CSS styling to your `extra.css` file.

## Root Variables
``` css
:root {
  --base-border-radius: 0.5 rem;
  --base-table-header-font-color: #ffffff;
  --base-table-header-background-color: #000000;
}
```

## Typography

### Headers
Add a line under headers like GitHub

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/144d49a8-c276-4276-a15f-05c1b447a864)

``` css
h2,
h3 {
  /* Add Line under Header like GitHub */
  margin-bottom: 0px;
  border-bottom: 1px solid var(--md-default-fg-color--lightest);
}
```

### Subtitles

#### Page Subtitle
Add a page subtitle that applies directly under the H1 tag (Page Title)

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/fc8c7300-5097-435b-94d8-72f1b044a8a2)

``` css
.md-typeset h1 {
  margin: 0px;
}

.page-subtitle {
  /* Create a subtitle on the page that sits under the page h1 Title */
  font-style: italic;
  font-size: 0.9em;
  color: rgb(168, 168, 168);
}
```
To use the page subtitle, wrap your content in a `span` tag
```markdown
<span class="page-subtitle">Here is an example of a page header style</span>
```

#### Section Subtitle
Add a subtitle under a specific H2 or H3 heading

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/b0330d97-430a-4135-94f9-ba41beebc7ec)


``` css
.section-subtitle {
  /* Create a subtitle on the page that sits under a H2 or H3 element */
  font-style: italic;
  font-size: 0.95em;
  color: rgb(138, 138, 138);
}
```

To use the section subtitle, wrap your content in a `span` tag
```markdown
<span class="section-subtitle">Here is an example of a section header style</span>
```

### Figure Captions
Add a caption under an image: 

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/408e5372-1690-4a9f-b23f-ad57b42eb237)

``` css
figcaption {
  /* Caption under image formatting */
  font-size: 0.8em;
  color: rgb(155, 155, 155);
}
```

You apply this by enclosing your caption in a `<figure >` tag
``` html
<figure markdown="span">
  ![Alt Text](example.png)
  <figcaption>Example Image</figcaption>
</figure>
```

## Tables
Make the tables 100% of container, round the edges of the table and update the table header color.

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/da774178-65cd-4a88-809b-d2d618ed90d5)

``` css
/* Table 100% Width fix */
.md-typeset__table {
  min-width: 100%;
}
.md-typeset table:not([class]) {
  display: table;
  border: 0.05rem solid var(--md-typeset-table-color);
  border-radius: 6px;
}
/* Table Header Colour */
.md-typeset__table thead {
  background-color: var(--base-table-header-background-color);
  color: var(--base-table-header-font-color);
}
/* Round the  Table Header Corners*/
th:first-of-type {
  border-left: 0.05rem solid var(--md-typeset-table-color);
  border-radius: 6px 0 0 0;
}
th:last-of-type {
  border-right: 0.05rem solid var(--md-typeset-table-color);
  border-radius: 0 6px 0 0;
}
```

## Search Bar Border Radius
![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/553589de-b6cf-4937-81a2-480d72a1b4cd)
![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/58abe39b-720f-4e6d-b6e5-c3d50c094338)

``` css
/* Search Forms */
.md-search__form {
  border-radius: var(--base-border-radius);
}

[data-md-toggle="search"]:checked ~ .md-header .md-search__form {
  border-top-right-radius: var(--base-border-radius);
  border-top-left-radius: var(--base-border-radius);
}

[dir="ltr"] .md-search__output {
  border-bottom-right-radius: var(--base-border-radius);
  border-bottom-left-radius: var(--base-border-radius);
}
```

## Code Block Border Radius

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/638986d0-d4db-4939-89b6-08293f4d10a5)
![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/a9f04a37-001d-4904-a0a7-ca8b107198bd)

``` css
/* Change font family of filename present on top of code block. */
.highlight span.filename {
  border-bottom: none;
  border-radius: var(--base-border-radius);
  display: inline;
  font-family: var(--md-code-font-family);
  border-bottom-left-radius: 0;
  border-bottom-right-radius: 0;
  margin-bottom: 5px;
  text-align: center;
}
.highlight span.filename + pre > code {
  border-radius: var(--base-border-radius);
  border-top-left-radius: 0;
}
.md-typeset pre > code {
  border-radius: var(--base-border-radius);
}
```

## Navigation Status

### New Statuses
#### Under Review
![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/c905a5b0-9310-47f3-98e6-846819d31cff)

``` css
.md-status--review {
  --md-status: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M11.986 23.972C5.411 23.972 0 18.561 0 11.986 0 5.411 5.411 0 11.986 0c6.575 0 11.986 5.411 11.986 11.986a11.9 11.9 0 0 1-2.492 7.281l2.062 2.062c.293.293.458.691.458 1.106 0 .859-.706 1.565-1.565 1.565-.415 0-.813-.165-1.106-.458l-2.062-2.062a11.9 11.9 0 0 1-7.281 2.492Zm6.664-6.001a8.936 8.936 0 0 0 2.31-5.985c0-4.923-4.051-8.974-8.974-8.974-2.702 0-5.141 1.22-6.792 3.135h5.255v2.458H3.681a8.851 8.851 0 0 0-.536 1.844H9.22v2.459H3.06c.087.845.297 1.673.621 2.459h4.31v2.458H5.194c1.651 1.915 4.09 3.135 6.792 3.135 2.29 0 4.392-.877 5.985-2.31a1.59 1.59 0 0 1 .679-.679Zm-9.43-.146h7.376v-2.458H9.22v2.458Zm6.147-4.917h4.917v-2.459h-4.917v2.459Zm-4.918 0h3.074v-2.459h-3.074v2.459Zm1.844-4.303h4.918V6.147h-4.918v2.458Z"/></svg>');
}
```

#### Upcoming
![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/e563e764-7bd5-4341-b09a-e4d8173a5623)

``` css
.md-status--upcoming {
  --md-status: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M21 13.1c-.1 0-.3.1-.4.2l-1 1 2.1 2.1 1-1c.2-.2.2-.6 0-.8l-1.3-1.3c-.1-.1-.2-.2-.4-.2m-1.9 1.8-6.1 6V23h2.1l6.1-6.1-2.1-2m-8.1 7c-5.1-.5-9-4.8-9-9.9C2 6.5 6.5 2 12 2c5.3 0 9.6 4.1 10 9.3-.3-.1-.6-.2-1-.2-.8 0-1.4.4-1.8.8l-2.7 2.7-4-2.4V7H11v6l4.4 2.7-4.4 4.4v1.8Z"/></svg>');
}
```

#### Draft
![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/c0b3bb6e-f6eb-4dc0-84ed-5bc1245af031)

``` css
.md-status--draft {
  --md-status: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M6 2c-1.1 0-2 .9-2 2v16c0 1.1.9 2 2 2h4v-1.9l10-10V8l-6-6H6m7 1.5L18.5 9H13V3.5m7.1 9.5c-.1 0-.3.1-.4.2l-1 1 2.1 2.1 1-1c.2-.2.2-.6 0-.8l-1.3-1.3c-.1-.1-.2-.2-.4-.2m-2 1.8L12 20.9V23h2.1l6.1-6.1-2.1-2.1Z"/></svg>');
}
```

Add the below to `mkdocs.yml`
``` yaml
extra:
  status:
    new: Recently Added
    deprecated: Deprecated
    draft: Documentation in Draft
    review: Documentation under Review
    upcoming: Coming Soon
```

### Right align status icons
``` css
/* Force Status icons to the max right for consistency */
.md-nav__link .md-ellipsis {
  width: 100%;
}
```

## External Links Icon
This css provides an external link icon next to hyperlinks where it doesn't finish in `sites domain`, `#` or `/`. Use the standard link markdown format.

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/a34aeb59-6197-4069-a9e5-859528ab91f0)

``` css
  a:not([href*="example.com"]):not([href^="#"]):not([href^="/"]):not(
    [href^="../"]
  ):not(.md-content__button):not(.md-tag):after {
  content: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M15.5 2.25a.75.75 0 0 1 .75-.75h5.5a.75.75 0 0 1 .75.75v5.5a.75.75 0 0 1-1.5 0V4.06l-6.22 6.22a.75.75 0 1 1-1.06-1.06L19.94 3h-3.69a.75.75 0 0 1-.75-.75Z"/><path d="M2.5 4.25c0-.966.784-1.75 1.75-1.75h8.5a.75.75 0 0 1 0 1.5h-8.5a.25.25 0 0 0-.25.25v15.5c0 .138.112.25.25.25h15.5a.25.25 0 0 0 .25-.25v-8.5a.75.75 0 0 1 1.5 0v8.5a1.75 1.75 0 0 1-1.75 1.75H4.25a1.75 1.75 0 0 1-1.75-1.75V4.25Z"/></svg>');
  width: 13px;
  /* Grey (#8d8d8d) */
  filter: invert(57%) sepia(30%) saturate(0%) hue-rotate(174deg) brightness(92%)
    contrast(96%);
  display: inline-block;
  vertical-align: top;
  margin-left: 0.25rem;
}
```

## Plugins - Swagger
The below fixes the colours for Dark Mode so you aren't blinded
``` css
/* Swagger API Dark Mode Fix */
  .swagger-ui,
  .swagger-ui .btn,
  .swagger-ui select,
  .swagger-ui .opblock .opblock-summary-description,
  .swagger-ui .opblock-description-wrapper p,
  .swagger-ui .opblock-external-docs-wrapper p,
  .swagger-ui .opblock .opblock-section-header h4,
  .swagger-ui
    .opblock-title_normal
    p
    .swagger-ui
    .opblock-tag
    .swagger-ui
    .parameter__name,
  .swagger-ui .info .title,
  .swagger-ui a.nostyle,
  .swagger-ui a.nostyle:visited,
  .swagger-ui table thead tr td,
  .swagger-ui table thead tr th,
  .swagger-ui .response-col_status,
  .swagger-ui .response-col_links {
    color: #e4e7e9;
  }
  .swagger-ui .dialog-ux .modal-ux,
  .swagger-ui select {
    background: #070c0f;
  }
  .swagger-ui .scheme-container,
  .swagger-ui .opblock .opblock-section-header {
    background: #212528;
  }
  .arrow {
    /* The dropdown arrow of the Swagger Generated API docs */
    filter: invert(17%) sepia(9%) saturate(466%) hue-rotate(163deg)
      brightness(93%) contrast(90%);
  }
  .unlocked {
    /* The auth lock icon of the Swagger Generated API docs */
    filter: invert(77%) sepia(14%) saturate(1710%) hue-rotate(98deg)
      brightness(91%) contrast(81%);
  }
```


## Admonitions

### Decision

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/b8880dcc-83fc-4832-9dd7-924f8b9d48fd)

Commonly used to call out a specific decsion
``` css
/* Customised Admonition - Decision */
:root {
  --md-admonition-icon--decision: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="m23 12-2.44-2.78.34-3.68-3.61-.82-1.89-3.18L12 3 8.6 1.54 6.71 4.72l-3.61.81.34 3.68L1 12l2.44 2.78-.34 3.69 3.61.82 1.89 3.18L12 21l3.4 1.46 1.89-3.18 3.61-.82-.34-3.68L23 12m-13 5-4-4 1.41-1.41L10 14.17l6.59-6.59L18 9l-8 8Z"/></svg>');
}
.md-typeset .admonition.decision,
.md-typeset details.decision {
  border-color: rgb(36, 167, 73);
}
.md-typeset .decision > .admonition-title,
.md-typeset .decision > summary {
  background-color: rgba(36, 167, 73, 0.1);
}
.md-typeset .decision > .admonition-title::before,
.md-typeset .decision > summary::before {
  background-color: rgb(36, 167, 73);
  -webkit-mask-image: var(--md-admonition-icon--decision);
  mask-image: var(--md-admonition-icon--decision);
}
```
**Markdown Format**
``` markdown
!!! decision
    Calls out a design or business decision that provides contextual relevance to the topic. 
    Where possible, this will be linked to a decision register.
```

### Assumption

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/15f6101f-c01b-44f6-bde3-c2340cbc3d9f)

``` css
/* Customised Admonition - Assumption */
:root {
  --md-admonition-icon--assumption: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M3.5 19A1.5 1.5 0 0 1 5 20.5 1.5 1.5 0 0 1 3.5 22 1.5 1.5 0 0 1 2 20.5 1.5 1.5 0 0 1 3.5 19m5-3a2.5 2.5 0 0 1 2.5 2.5A2.5 2.5 0 0 1 8.5 21 2.5 2.5 0 0 1 6 18.5 2.5 2.5 0 0 1 8.5 16m6-1c-1.19 0-2.27-.5-3-1.35-.73.85-1.81 1.35-3 1.35-1.96 0-3.59-1.41-3.93-3.26A4.02 4.02 0 0 1 2 8a4 4 0 0 1 4-4c.26 0 .5.03.77.07C7.5 3.41 8.45 3 9.5 3c1.19 0 2.27.5 3 1.35.73-.85 1.81-1.35 3-1.35 1.96 0 3.59 1.41 3.93 3.26A4.02 4.02 0 0 1 22 10a4 4 0 0 1-4 4l-.77-.07c-.73.66-1.68 1.07-2.73 1.07Z"/></svg>');
}
.md-typeset .admonition.assumption,
.md-typeset details.assumption {
  border-color: rgb(250, 158, 198);
}
.md-typeset .assumption > .admonition-title,
.md-typeset .assumption > summary {
  background-color: rgba(250, 158, 198, 0.1);
}
.md-typeset .assumption > .admonition-title::before,
.md-typeset .assumption > summary::before {
  background-color: rgb(250, 158, 198);
  -webkit-mask-image: var(--md-admonition-icon--assumption);
  mask-image: var(--md-admonition-icon--assumption);
}
```

**Markdown Format**
``` markdown
!!! assumption
    May be used to call out an assumption in a solution or design. 
    Where possible, this will be linked to a decision register
```

### Recommendation

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/705e1fbf-6aee-4cdd-8012-d768f7e721fa)

``` css
/* Customised Admonition - Recommendation */
:root {
  --md-admonition-icon--recommendation: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M16.23 18 12 15.45 7.77 18l1.12-4.81-3.73-3.23 4.92-.42L12 5l1.92 4.53 4.92.42-3.73 3.23L16.23 18M12 2C6.47 2 2 6.5 2 12a10 10 0 0 0 10 10 10 10 0 0 0 10-10A10 10 0 0 0 12 2Z"/></svg>');
}
.md-typeset .admonition.recommendation,
.md-typeset details.recommendation {
  border-color: rgb(103, 218, 255);
}
.md-typeset .recommendation > .admonition-title,
.md-typeset .recommendation > summary {
  background-color: rgba(103, 218, 255, 0.1);
}
.md-typeset .recommendation > .admonition-title::before,
.md-typeset .recommendation > summary::before {
  background-color: rgb(103, 218, 255);
  -webkit-mask-image: var(--md-admonition-icon--recommendation);
  mask-image: var(--md-admonition-icon--recommendation);
}
```

**Markdown Format**
``` markdown
`recommendation`
!!! recommendation
    May be used to call out future recommendations or improvement activities.
```

### Important

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/d3d15bbf-de38-4cd2-b7c1-69fea87db4d1)

``` css
/* Customised Admonition - Important */
:root {
  --md-admonition-icon--important: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M21 19v1H3v-1l2-2v-6c0-3.1 2.03-5.83 5-6.71V4a2 2 0 0 1 2-2 2 2 0 0 1 2 2v.29c2.97.88 5 3.61 5 6.71v6l2 2m-7 2a2 2 0 0 1-2 2 2 2 0 0 1-2-2m9.75-17.81-1.42 1.42A8.982 8.982 0 0 1 21 11h2c0-2.93-1.16-5.75-3.25-7.81M1 11h2c0-2.4.96-4.7 2.67-6.39L4.25 3.19A10.96 10.96 0 0 0 1 11Z"/></svg>');
}
.md-typeset .admonition.important,
.md-typeset details.important {
  border-color: rgb(255, 94, 123);
}
.md-typeset .important > .admonition-title,
.md-typeset .important > summary {
  background-color: rgba(255, 94, 123, 0.1);
}
.md-typeset .important > .admonition-title::before,
.md-typeset .important > summary::before {
  background-color: rgb(255, 94, 123);
  -webkit-mask-image: var(--md-admonition-icon--important);
  mask-image: var(--md-admonition-icon--important);
}
```

**Markdown Format**
``` markdown
!!! important
    Important Note! Listen!
```

### Instruction

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/f8dbdef6-dda2-4444-b8f8-494ba1580d15)

``` css
/* Customised Admonition - Instruction */
:root {
  --md-admonition-icon--instruction: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M19 3h-4.18C14.4 1.84 13.3 1 12 1s-2.4.84-2.82 2H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2M7 8h2v4H8V9H7V8m3 9v1H7v-.92L9 15H7v-1h2.25c.41 0 .75.34.75.75 0 .2-.08.39-.21.52L8.12 17H10m1-13c0-.55.45-1 1-1s1 .45 1 1-.45 1-1 1-1-.45-1-1m6 13h-5v-2h5v2m0-6h-5V9h5v2Z"/></svg>');
}
.md-typeset .admonition.instruction,
.md-typeset details.instruction {
  border-color: rgb(246, 191, 0);
}
.md-typeset .instruction > .admonition-title,
.md-typeset .instruction > summary {
  background-color: rgba(246, 191, 0, 0.1);
}
.md-typeset .instruction > .admonition-title::before,
.md-typeset .instruction > summary::before {
  background-color: rgb(246, 191, 0);
  -webkit-mask-image: var(--md-admonition-icon--instruction);
  mask-image: var(--md-admonition-icon--instruction);
}

.instruction-subtitle {
  color: rgb(126, 97, 0);
  font-style: italic;
  font-size: 0.9em;
}
```

**Markdown Format**
``` markdown
!!! instruction "Instruction <span class="instruction-subtitle">Delete once section is complete</span>"
    Provides a set of instructions to the user (generally within a template), this should be deleted in published documentation
```

### Education

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/1d7634a7-0d20-4184-8079-aeb89bafd5d9)

``` css
/* Customised Admonition - Education */
:root {
  --md-admonition-icon--education: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 512"><!--! Font Awesome Free 6.5.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free (Icons: CC BY 4.0, Fonts: SIL OFL 1.1, Code: MIT License) Copyright 2023 Fonticons, Inc.--><path d="M320 32c-8.1 0-16.1 1.4-23.7 4.1L15.8 137.4C6.3 140.9 0 149.9 0 160s6.3 19.1 15.8 22.6l57.9 20.9C57.3 229.3 48 259.8 48 291.9V320c0 28.4-10.8 57.7-22.3 80.8-6.5 13-13.9 25.8-22.5 37.6-3.2 4.3-4.1 9.9-2.3 15s6 8.9 11.2 10.2l64 16c4.2 1.1 8.7.3 12.4-2s6.3-6.1 7.1-10.4c8.6-42.8 4.3-81.2-2.1-108.7-3.2-14.2-7.5-28.7-13.5-42v-24.6c0-30.2 10.2-58.7 27.9-81.5 12.9-15.5 29.6-28 49.2-35.7l157-61.7c8.2-3.2 17.5.8 20.7 9s-.8 17.5-9 20.7l-157 61.7c-12.4 4.9-23.3 12.4-32.2 21.6l159.6 57.6c7.6 2.7 15.6 4.1 23.7 4.1s16.1-1.4 23.7-4.1l280.6-101c9.5-3.4 15.8-12.5 15.8-22.6s-6.3-19.1-15.8-22.6L343.7 36.1c-7.6-2.7-15.6-4.1-23.7-4.1zM128 408c0 35.3 86 72 192 72s192-36.7 192-72l-15.3-145.4L354.5 314c-11.1 4-22.8 6-34.5 6s-23.5-2-34.5-6l-142.2-51.4L128 408z"/></svg>');
}
.md-typeset .admonition.education,
.md-typeset details.education {
  border-color: rgb(235, 138, 3);
}
.md-typeset .education > .admonition-title,
.md-typeset .education > summary {
  background-color: rgba(235, 138, 3, 0.1);
}
.md-typeset .education > .admonition-title::before,
.md-typeset .education > summary::before {
  background-color: rgb(235, 138, 3);
  -webkit-mask-image: var(--md-admonition-icon--education);
  mask-image: var(--md-admonition-icon--education);
}
```

**Markdown Format**
``` markdown
!!! education
    Provides recommendations, suggestions or requirements for education or skills uplift in relation to a component or service.
```

### Cost Analysis

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/9dc77de9-ef65-43a6-a4a0-3c007b837989)

``` css
/* Customised Admonition - Cost Analysis */
:root {
  --md-admonition-icon--dollar: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><!--! Font Awesome Free 6.5.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free (Icons: CC BY 4.0, Fonts: SIL OFL 1.1, Code: MIT License) Copyright 2023 Fonticons, Inc.--><path d="M416 208c0 45.9-14.9 88.3-40 122.7l126.6 126.7c12.5 12.5 12.5 32.8 0 45.3s-32.8 12.5-45.3 0L330.7 376c-34.4 25.2-76.8 40-122.7 40C93.1 416 0 322.9 0 208S93.1 0 208 0s208 93.1 208 208zM228 104c0-11-9-20-20-20s-20 9-20 20v14c-7.6 1.7-15.2 4.4-22.2 8.5-13.9 8.3-25.9 22.8-25.8 43.9.1 20.3 12 33.1 24.7 40.7 11 6.6 24.7 10.8 35.6 14l1.7.5c12.6 3.8 21.8 6.8 28 10.7 5.1 3.2 5.8 5.4 5.9 8.2.1 5-1.8 8-5.9 10.5-5 3.1-12.9 5-21.4 4.7-11.1-.4-21.5-3.9-35.1-8.5-2.3-.8-4.7-1.6-7.2-2.4-10.5-3.5-21.8 2.2-25.3 12.6s2.2 21.8 12.6 25.3c1.9.6 4 1.3 6.1 2.1 8.3 2.9 17.9 6.2 28.2 8.4V312c0 11 9 20 20 20s20-9 20-20v-13.8c8-1.7 16-4.5 23.2-9 14.3-8.9 25.1-24.1 24.8-45-.3-20.3-11.7-33.4-24.6-41.6-11.5-7.2-25.9-11.6-37.1-15l-.7-.2c-12.8-3.9-21.9-6.7-28.3-10.5-5.2-3.1-5.3-4.9-5.3-6.7 0-3.7 1.4-6.5 6.2-9.3 5.4-3.2 13.6-5.1 21.5-5 9.6.1 20.2 2.2 31.2 5.2 10.7 2.8 21.6-3.5 24.5-14.2s-3.5-21.6-14.2-24.5c-6.5-1.7-13.7-3.4-21.1-4.7V104z"/></svg>');
}
.md-typeset .admonition.dollar,
.md-typeset details.dollar {
  border-color: rgb(63, 136, 65);
}
.md-typeset .dollar > .admonition-title,
.md-typeset .dollar > summary {
  background-color: rgba(63, 136, 65, 0.1);
}
.md-typeset .dollar > .admonition-title::before,
.md-typeset .dollar > summary::before {
  background-color: rgb(63, 136, 65);
  -webkit-mask-image: var(--md-admonition-icon--dollar);
  mask-image: var(--md-admonition-icon--dollar);
}
```

**Markdown Format**
``` markdown
!!! dollar
    Provides contextual cost specific analysis information about the component or service being discussed.
```

## Labels

### Label Sizes (Small, Medium & Large)
``` css
/* Small Label */
.label-sm {
  background-color: rgb(164, 164, 164); /* Grey */
  border: none;
  color: white;
  padding: 1px 5px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  border-radius: 5px;
  font-size: 0.7em;
  margin: 0px 3px;
  text-transform: uppercase;
  vertical-align: middle;
  letter-spacing: 1px;
}

/* Medium Label */
.label-md {
  background-color: rgb(164, 164, 164); /* Grey */
  border: none;
  color: white;
  padding: 2px 7px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  border-radius: 5px;
  font-size: 0.85em;
  margin: 0px 3px;
  text-transform: uppercase;
  vertical-align: middle;
  letter-spacing: 1px;
}

/* Large Label */
.label-lg {
  background-color: rgb(164, 164, 164); /* Grey */
  border: none;
  color: white;
  padding: 3px 12px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  border-radius: 5px;
  font-size: 1.1em;
  margin: 0px 3px;
  text-transform: uppercase;
  vertical-align: middle;
  letter-spacing: 1px;
}
```

#### Example

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/cd776c70-3f9d-418d-9835-c6e63d025caa)

``` html
<span class="label-sm">Small</span> 
<span class="label-md">Medium</span> 
<span class="label-lg">Large</span>
```

### Different Label Types

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/b5948d7a-b1f9-4ad3-9af4-c9de6095c58a)

**Primary**
``` css
/* Primary Label Colour Override */
.label-primary {
  background-color: rgb(62, 138, 204); /* Blue */
}
```

**Success**
``` css
/* Success Label Colour Override */
.label-success {
  background-color: rgb(88, 185, 87); /* Green */
}
```

**Information**
``` css
/* Info Label Colour Override */
.label-info {
  background-color: rgb(86, 192, 224); /* Light Blue */
}
```

**Warning**
``` css
/* Warning Label Colour Override */
.label-warning {
  background-color: rgb(242, 174, 67); /* Yellow */
}
```

**Danger**
``` css
/* Danger Label Colour Override */
.label-danger {
  background-color: rgb(219, 82, 75); /* Red */
}
```

**New / Purple**
``` css
/* New/Purple Label Colour Override */
.label-new {
  background-color: rgb(84, 74, 173); /* Purple */
}
```

**New / Alt / Pink**
``` css
/* New/Alt/Pink Label Colour Override */
.label-alt {
  background-color: rgb(255, 94, 123); /* Pink */
}
```

**Bronze**
``` css
/* Bronze Label Colour Override */
.label-bronze {
  background-color: rgb(100, 61, 49); /* Pink */
}
```

**Silver**
``` css
/* silver Label Colour Override */
.label-silver {
  background-color: rgb(92, 93, 97); /* Pink */
}
```

**Gold**
``` css
/* gold Label Colour Override */
.label-gold {
  background-color: rgb(151, 107, 33); /* Pink */
}
```

**Platinum**
``` css
/* platinum Label Colour Override */
.label-platinum {
  background-color: rgb(56, 57, 70); /* Pink */
}
```

### Label Examples

#### Offical / Sensitive / Protected

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/7a409ab5-196a-4a28-bd1b-a12717441b19)

``` html
<span class="label-sm">:material-eye: Official</span> 
<span class="label-sm label-warning">:material-eye-off: Sensitive</span> 
<span class="label-sm label-danger">:material-eye-lock: Protected</span>
```

#### Risk States

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/3a42a86f-49d1-47ea-9a9a-6fe410e53af3)

``` html
<span class="label-sm label-success">Low</span> 
<span class="label-sm label-warning">Medium</span> 
<span class="label-sm label-danger">High</span>
```

#### Impact States

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/2628e243-405d-4995-988a-5f7bd1cece82)

``` html
<span class="label-sm label-success">Minor</span> 
<span class="label-sm label-warning">Major</span> 
<span class="label-sm label-danger">Critical</span>
```

#### Activity States

![image](https://github.com/TJohnson93/mkdocs-material-tweaks/assets/6167090/a59f8deb-5629-4cb0-9daa-37408cb78d76)

``` html
<span class="label-sm label-new">New</span> 
<span class="label-sm">Ready</span> 
<span class="label-sm label-primary">In Progress</span> 
<span class="label-sm label-warning">Review</span> 
<span class="label-sm label-success">Complete</span>
```
