# mkdocs-material-tweaks
CSS Tweaks made to Material for mkdocs that I re-use in all sites 



# CSS Tweaks

[[ TOC ]]

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

#### Section Subtitle
Add a subtitle under a specific H2 or H3 heading
``` css
.section-subtitle {
  /* Create a subtitle on the page that sits under a H2 or H3 element */
  font-style: italic;
  font-size: 0.95em;
  color: rgb(138, 138, 138);
}
```

### Figure Captions
Add a caption under an image: 
```
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
Make the tables 100% of container, round the edges of the table and update the table header color
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
``` css
.md-status--draft {
  --md-status: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M6 2c-1.1 0-2 .9-2 2v16c0 1.1.9 2 2 2h4v-1.9l10-10V8l-6-6H6m7 1.5L18.5 9H13V3.5m7.1 9.5c-.1 0-.3.1-.4.2l-1 1 2.1 2.1 1-1c.2-.2.2-.6 0-.8l-1.3-1.3c-.1-.1-.2-.2-.4-.2m-2 1.8L12 20.9V23h2.1l6.1-6.1-2.1-2.1Z"/></svg>');
}
.md-status--upcoming {
  --md-status: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M21 13.1c-.1 0-.3.1-.4.2l-1 1 2.1 2.1 1-1c.2-.2.2-.6 0-.8l-1.3-1.3c-.1-.1-.2-.2-.4-.2m-1.9 1.8-6.1 6V23h2.1l6.1-6.1-2.1-2m-8.1 7c-5.1-.5-9-4.8-9-9.9C2 6.5 6.5 2 12 2c5.3 0 9.6 4.1 10 9.3-.3-.1-.6-.2-1-.2-.8 0-1.4.4-1.8.8l-2.7 2.7-4-2.4V7H11v6l4.4 2.7-4.4 4.4v1.8Z"/></svg>');
}
.md-status--review {
  --md-status: url('data:image/svg+xml;charset=utf-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M11.986 23.972C5.411 23.972 0 18.561 0 11.986 0 5.411 5.411 0 11.986 0c6.575 0 11.986 5.411 11.986 11.986a11.9 11.9 0 0 1-2.492 7.281l2.062 2.062c.293.293.458.691.458 1.106 0 .859-.706 1.565-1.565 1.565-.415 0-.813-.165-1.106-.458l-2.062-2.062a11.9 11.9 0 0 1-7.281 2.492Zm6.664-6.001a8.936 8.936 0 0 0 2.31-5.985c0-4.923-4.051-8.974-8.974-8.974-2.702 0-5.141 1.22-6.792 3.135h5.255v2.458H3.681a8.851 8.851 0 0 0-.536 1.844H9.22v2.459H3.06c.087.845.297 1.673.621 2.459h4.31v2.458H5.194c1.651 1.915 4.09 3.135 6.792 3.135 2.29 0 4.392-.877 5.985-2.31a1.59 1.59 0 0 1 .679-.679Zm-9.43-.146h7.376v-2.458H9.22v2.458Zm6.147-4.917h4.917v-2.459h-4.917v2.459Zm-4.918 0h3.074v-2.459h-3.074v2.459Zm1.844-4.303h4.918V6.147h-4.918v2.458Z"/></svg>');
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
Markdown Format
``` mardown
!!! decision
    Calls out a design or business decision that provides contextual relevance to the topic. 
    Where possible, this will be linked to a decision register.
```
