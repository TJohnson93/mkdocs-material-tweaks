# mkdocs-material-tweaks
CSS Tweaks made to Material for mkdocs that I re-use in all sites 



# CSS Tweaks

Add the below CSS styling to your `extra.css` file.

## Root Variables
``` css
:root {
  --base-border-radius: 0.5 rem;
}
```

## Typography

Add a line under headers like GitHub
``` css
h2,
h3 {
  /* Add Line under Header like GitHub */
  margin-bottom: 0px;
  border-bottom: 1px solid var(--md-default-fg-color--lightest);
}
```

## Subtitles

### Page Subtitle
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

### Section Subtitle
Add a subtitle under a specific H2 or H3 heading
``` css
.section-subtitle {
  /* Create a subtitle on the page that sits under a H2 or H3 element */
  font-style: italic;
  font-size: 0.95em;
  color: rgb(138, 138, 138);
}
```
