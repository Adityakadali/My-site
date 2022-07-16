---
title: "Images on Web | HTML <img> Tag"
date: 2022-07-16T19:26:50+05:30
type:
  - posts
  - post
tags:
  - HTML
  - <img> tag

categories:
  - Web Development
author:
  name: Aditya Kadali
---

## Basic usage

On every web page we come across images. Those images are placed in HTML using `<img>` tags.
It is a self closing tag.

```HTML
<img src="cute-catimage.jpg"/>
```

## CSS

Default CSS property of img tag is

```CSS
img {
  display: inline-block;
}
```

## Attributes

Some important attributes of image tag are

| Attribute    | Value      | Description                   |
| ------------ | ---------- | ----------------------------- |
| alt          | text       | Sets alt text of image        |
| height/width | pixels     | Sets height/width of image    |
| loading      | eagar,lazy | Sets how browser loads images |
| src          | URL        | Sets path of resource         |

Basic usages of the above tags are

```HTML
<img src="cat-image.png" alt="A image of cat" height="500px" loading="lazy">

<img src="dog-image.jpg" alt="A dog image" width="100px" loading="eagar" >
```

In the above code we have used two `<img>` tags to display a cat image and a dog image using `src` we have set the respective resources to the respective images.

Both these `<img>` tags have their alt text in place when the end user has a slow internet connection these alt texts help them to understand about the content of images without them being loaded completely.

We have set height 500px for cat image and width of 100px for dog image. when we specify only `height` or `width` in `<img>` tag aspect ratio of the image doesn't gets disturbed it is adjusted automatically.

`loading` attribute is used to set priority. Usually HTML is read from top to bottom so automatically higher images gets higher priority while loading. In this example code even the dog image is in bottom of the page it gets loaded first because we have set it's loading flag to eagar so it loads first and lazy elements gets loaded only when user scrolls over it.

There are more attributes we can set to `<img>` tags refer to [MDN Docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Img) for more.

## Captioning images using `<figure>` tag

`<figure>` is a self contained element. For some images like scientific graphs and tables we need cations. by using this `<figure>` tag we can easily add captions to our images

**Eg:**

```HTML
<figure>
  <img src="data-graph.png"
       alt="population density graph">
  <figcaption>A population density graph</figcaption>
</figure>
```

## `<img>` tag in responsive webdesign

There will be times where we need show different resolution of an image or an entirely different set of images for different screen resolutions and different viewport sizes.

To save bandwidth we can load only images required according to the user screen requirements.

### Using attribute `srcset`

`srcset` is a string used to set one or more image resources separaed by`,`

when we use `srcset` we need to specify widths of images we need to load based on the requirement of user. If user has high pixel density screen we need to load high res image.

**Eg.1:**

```HTML
<img src="cat-lowres.png"
     srcset="cat-lowres.png 1x,
             cat-highres.png 2x">
```

In this example browser loads high resoulution image when user had high pixel density device. On web we generally have 1x, 2x, 3x devices.

Along with `srcset` we also need `src` attribute to handle browser compatibility.

**Eg.2:**

```HTML
<img src="cat-lowres.png"
     srcset="cat-lowres.png 100w,
             cat-highres.png 500w
             cat-xtra-highres.png 1000W"
     media="(max-width: 500px) 100vw, 50vw">
```

Along with `srcset` attribute we can also combine this with `size` attribute. In this example our image takes half of the viewport width on screens larger than 500px. `size` attribute determines the element width and sets the image required according to the user screensize.

### Using `<picture>` tag

`<picture>` tag contains zero or more `source` tags and one `image` tag to serve different images for different scenarios.

**Eg:**

```HTML
<picture>
  <source
    media="(max-width: 800px)"
    srcset="cat-sleeping.png"
  />
  <source
    media="(max-width: 300px)"
    srcset="cat-potrait.png"
  />
  <img src="cat.png" alt="A cat image" />
</picture>
```

In this example we are showing two different images at two different break points i.e; 300px and 800px here in first source tag `(max-width: 300px)` means until 300px our browser shows `cat-potrait.png` and then up to `(max-width: 800px)` until 800px our browser shows `cat-sleeping.png` and then when browser breaks above 800px browser defaults to `cat.png`
