---
title: Contributing to this project
layout: default
---

# Contributing to this project

The content of the guides is stored as [a GitHub repository](https://github.com/adaptation-gardening/crop-guides/). Contributions can be made directly in the form of Issues and Pull Requests. You may also post in the [Going to Seed Community Forum](https://goingtoseed.discourse.group/).

## Markdown formatting
The content of the guides is written in a relatively simple text syntax called Markdown. Link: [Guide to Markdown syntax](https://www.markdownguide.org/basic-syntax/).

## Internal links
When linking from one page to another inside the crop guides, a combination of Jekyll and Markdown syntax can be used.

### Example: Internal Links
* [Link to a crop guide document several layers into the tree]({% link guides/cucurbita/argyrosperma/index.md %})
* [Link to the README document in the root level of the tree]({% link README.md %})

#### Source
{% raw %}
```
* [Link to a crop guide document several layers into the tree]({% link guides/cucurbita/argyrosperma/index.md %})
* [Link to the README document in the root level of the tree]({% link README.md %})
```
{% endraw %}
The path to the post, page, or collection is defined as the path relative to the root directory where the `config.yml` file is located, not the path from your existing page to the other page. Read more at: [https://jekyllrb.com/docs/liquid/tags/#link](https://jekyllrb.com/docs/liquid/tags/#link)

## Images

Images should be stored in `/assets/images`, within a subfolder that corresponds to the subfolder name of the 'primary' page that uses the image. An image related to a Cucurbita argyrsperma "Pumpkin Pie" recipe should be stored at a path like `/assets/images/cucurbita/argyrosperma/recipes/cushaw-pumpkin-pie`.

### Using the `embed_image` template
Images can be embedded using standard Markdown syntax, but this offers limited formatting options and does not provide a convenient method to caption images. A Jekyll template called `embed_image.html` offers the ability to embed an image with more flexibility than Markdown.

#### `embed_image` parameters
 * `url`
 * `alt`
 * `caption` - optional
 * `thumbnail` - optional

### Example: Image without caption

{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/cushaw-homepage-banner-1000x250.png"
    alt="College of Cucurbita argyrosperma fruit in various situations"
%}

#### Source
{% raw %}
```
{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/cushaw-homepage-banner-1000x250.png"
    alt="College of Cucurbita argyrosperma fruit in various situations"
%}
```
{% endraw %}

### Example: Image with caption
Invoke the template with a caption to wrap the image with the html element `figure` and add a caption wrapped in `figcaption`.

{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/cushaw-homepage-banner-1000x250.png"
    alt="College of Cucurbita argyrosperma fruit in various situations"
    caption="Sometimes a caption adds valuable information that can't easily be conveyed any other way."
%}

#### Source
{% raw %}
```
{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/cushaw-homepage-banner-1000x250.png"
    alt="College of Cucurbita argyrosperma fruit in various situations"
    caption="Sometimes a caption adds valuable information that can't easily be conveyed any other way."
%}
```
{% endraw %}


### Example: Wrap text around floating captioned image

{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/recipes/cut-fruit-with-seeds-350w.jpg"
    alt="Saved seeds in a colander"
    caption="Seed saving and sharing is integrated into the guide"
    thumbnail="true"
%}
The text in this paragraph wraps to the left side of the image, assuming the window is wide enough.

#### Source
{:class="clear-right"}

{% raw %}
```
{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/recipes/cut-fruit-with-seeds-350w.jpg"
    alt="Saved seeds in a colander"
    caption="Seed saving and sharing is integrated into the guide"
    thumbnail="true"
%}
```
{% endraw %}

### Example: A gallery of images

Three thumbnail images can be placed in a row. The `<hr>` element or another element with `clear: right;` such as `<h1>` should be used after each row.

{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/recipes/cut-fruit-with-seeds-350w.jpg"
    alt="Saved seeds in a colander"
    caption="Seed saving and sharing is integrated into the guide"
    thumbnail="true"
%}
{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/recipes/cut-fruit-with-seeds-350w.jpg"
    alt="Saved seeds in a colander"
    caption="Seed saving and sharing is integrated into the guide"
    thumbnail="true"
%}
{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/recipes/cut-fruit-with-seeds-350w.jpg"
    alt="Saved seeds in a colander"
    caption="Seed saving and sharing is integrated into the guide"
    thumbnail="true"
%}
<hr>
{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/recipes/cut-fruit-with-seeds-350w.jpg"
    alt="Saved seeds in a colander"
    caption="Seed saving and sharing is integrated into the guide"
    thumbnail="true"
%}
{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/recipes/cut-fruit-with-seeds-350w.jpg"
    alt="Saved seeds in a colander"
    caption="Seed saving and sharing is integrated into the guide"
    thumbnail="true"
%}
{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/recipes/cut-fruit-with-seeds-350w.jpg"
    alt="Saved seeds in a colander"
    caption="Seed saving and sharing is integrated into the guide"
    thumbnail="true"
%}
<hr>

#### Source
{:class="clear-right"}

{% raw %}
```
{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/recipes/cut-fruit-with-seeds-350w.jpg"
    alt="Saved seeds in a colander"
    caption="Seed saving and sharing is integrated into the guide"
    thumbnail="true"
%}
{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/recipes/cut-fruit-with-seeds-350w.jpg"
    alt="Saved seeds in a colander"
    caption="Seed saving and sharing is integrated into the guide"
    thumbnail="true"
%}
{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/recipes/cut-fruit-with-seeds-350w.jpg"
    alt="Saved seeds in a colander"
    caption="Seed saving and sharing is integrated into the guide"
    thumbnail="true"
%}
<hr>
{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/recipes/cut-fruit-with-seeds-350w.jpg"
    alt="Saved seeds in a colander"
    caption="Seed saving and sharing is integrated into the guide"
    thumbnail="true"
%}
{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/recipes/cut-fruit-with-seeds-350w.jpg"
    alt="Saved seeds in a colander"
    caption="Seed saving and sharing is integrated into the guide"
    thumbnail="true"
%}
{% include embed_image.html
    url="assets/images/cucurbita/argyrosperma/recipes/cut-fruit-with-seeds-350w.jpg"
    alt="Saved seeds in a colander"
    caption="Seed saving and sharing is integrated into the guide"
    thumbnail="true"
%}
<hr>
```
{% endraw %}