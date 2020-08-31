---
layout: single
title: "YAML front matter setup "
category:
  - Tutorial
tags:
  - YAML
  - Front matter
#last_modified_at: 2016-03-09T16:20:02-05:00
excerpt: "Some Front matter setup"
toc: true
toc_sticky: true
---

## Set external video as header

To embed the following YouTube video at url https://www.youtube.com/watch?v=XsxDH4HcOWA (long version) or https://youtu.be/XsxDH4HcOWA (short version) as a video header you'd use the following YAML Front Matter

```yaml
header:
  video:
    id: XsxDH4HcOWA
    provider: youtube
```

To embed following Vimeo video at url `https://vimeo.com/212731897` as a video header you'd use the following YAML Front Matter

```yaml
header:
  video:
    id: 212731897
    provider: vimeo
```


## Post with header image

Post has a header image with an OpenGraph override.

```yaml
header:
  image: /assets/images/page-header-image.png
  og_image: /assets/images/page-header-og-image.png
```

Post has a header image with an OpenGraph override.


```yaml
header:
  overlay_image: /assets/images/unsplash-image-1.jpg
  og_image: /assets/images/page-header-og-image.png
  caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
  actions:
    - label: "Learn more"
      url: "https://unsplash.com"
```

The preferred way of using images is placing them in the `/assets/images/` directory and referencing them with an absolute path. Prepending the filename with `{% raw %}{{ site.url }}{{ site.baseurl }}/assets/images/{% endraw %}` will make sure your images display properly in feeds and such.

Standard image with no width modifier classes applied.

**HTML:**

```html
{% raw %}<img src="{{ site.url }}{{ site.baseurl }}/assets/images/filename.jpg" alt="">{% endraw %}
```


## Overlay filter
You can use it by specifying the opacity (between 0 and 1) of a black overlay like so:


```yaml
excerpt: "This post should [...]"
header:
  overlay_image: /assets/images/unsplash-image-1.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
  caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
  actions:
    - label: "More Info"
      url: "https://unsplash.com"
```

Or if you want to do more fancy things, go full rgba:


```yaml
excerpt: "This post should [...]"
header:
  overlay_image: /assets/images/unsplash-image-1.jpg
  overlay_filter: rgba(255, 0, 0, 0.5)
  caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
  actions:
    - label: "More Info"
      url: "https://unsplash.com"
```


## Enable table of contents

Enable table of contents on post or page by adding `toc: true` to its YAML Front Matter. The title and icon can also be changed with:

```yaml
---
toc: true
toc_label: "Unique Title"
toc_icon: "heart"  # corresponding Font Awesome icon name (without fa prefix)
---
```

"Stick" table of contents to the top of a page by adding `toc_sticky: true` to its YAML Front Matter.

```yaml
---
toc: true
toc_sticky: true
---
```

## side bar
Add this to the front Matter

```yaml
sidebar:
  - title: "Title"
    image: http://placehold.it/350x250
    image_alt: "image"
    text: "Some text here."
  - title: "Another Title"
    text: "More text here."
    nav: sidebar-sample
```


## navigation Sidebar

This post has a custom navigation list set in the post's YAML Front Matter.

```yaml
sidebar:
  title: "Sample Title"
  nav: sidebar-sample
```

Along with navigation elements set in `_data/navigation.yml`.

```yaml
sidebar-sample:
  - title: "Parent Page A"
    children:
      - title: "Child Page A1"
        url: /
      - title: "Child Page A2"
        url: /
      - title: "Child Page A3"
        url: /
      - title: "Child Page A4"
        url: /
  - title: "Parent Page B"
    children:
      - title: "Child Page B1"
        url: /
      - title: "Child Page B2"
        url: /
      - title: "Child Page B3"
        url: /
      - title: "Child Page B4"
        url: /
      - title: "Child Page B5"
        url: /
  - title: "Parent Page C"
    children:
      - title: "Child Page C1"
        url: /
      - title: "Child Page C2"
        url: /
      - title: "Child Page C3"
        url: /
      - title: "Child Page C4"
        url: /
      - title: "Child Page C5"
        url: /
  - title: "Parent Page D"
    children:
      - title: "Child Page D1"
        url: /
      - title: "Child Page D2"
        url: /
```
