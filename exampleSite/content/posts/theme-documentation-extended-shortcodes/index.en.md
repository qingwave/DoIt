---
weight: 4
title: "Theme Documentation - Extended Shortcodes"
date: 2020-03-06T16:29:41+08:00
lastmod: 2020-03-06T16:29:41+08:00
draft: false
authors: [Dillon, PCloud]
description: "DoIt theme provides multiple shortcodes on top of built-in ones in Hugo."
resources:
featuredImage: "featured-image.webp"
featuredImagePreview: "featured-image-preview.webp"

tags: ["shortcodes"]
categories: ["documentation"]
series: ["getting-start"]
series_weight: 4
lightgallery: true
math:
  enable: true
---

**DoIt** theme provides multiple shortcodes on top of built-in ones in Hugo.

<!--more-->

## style

{{< version 0.2.0 changed >}}

{{< admonition >}}
Hugo **extended** version is necessary for `style` shortcode.
{{< /admonition >}}

`style` is a shortcode to insert custom style in your post.

The `style` shortcode has two positional parameters.

The **first** one is the custom style content,
which supports nesting syntax in [:(fab fa-sass fa-fw): SASS](https://sass-lang.com/documentation/style-rules/declarations#nesting)
and `&` referring to this parent HTML element.

And the **second** one is the tag name of the HTML element wrapping the content you want to change the style, and whose default value is `div`.

Example `style` input:

```markdown
{{</* style "text-align:right; strong{color:#00b1ff;}" */>}}
This is a **right-aligned** paragraph.
{{</* /style */>}}
```

The rendered output looks like this:

{{< style "text-align:right; strong{color:#00b1ff;}" >}}
This is a **right-aligned** paragraph.
{{< /style >}}

## link

{{< version 0.2.0 >}}

`link` shortcode is an alternative to [Markdown link syntax](../basic-markdown-syntax#links). `link` shortcode can provide some other features and can be used in code blocks.

{{< version 0.2.10 >}} The complete usage of [local resource references](../theme-documentation-content#contents-organization) is supported.

The `link` shortcode has the following named parameters:

* **href** *[required]* (**first** positional parameter)

    Destination of the link.

* **content** *[optional]* (**second** positional parameter)

    Content of the link, the default value is the value of **href** parameter.

    *Markdown or HTML format is supported.*

* **title** *[optional]* (**third** positional parameter)

    `title` attribute of the HTML `a` tag, which will be shown when hovering on the link.

* **class** *[optional]*

    `class` attribute of the HTML `a` tag.

* **rel** *[optional]*

    Additional `rel` attributes of the HTML `a` tag.

Example `link` input:

```markdown
{{</* link "https://assemble.io" */>}}
Or
{{</* link href="https://assemble.io" */>}}

{{</* link "mailto:contact@revolunet.com" */>}}
Or
{{</* link href="mailto:contact@revolunet.com" */>}}

{{</* link "https://assemble.io" Assemble */>}}
Or
{{</* link href="https://assemble.io" content=Assemble */>}}
```

The rendered output looks like this:

* {{< link "https://assemble.io" >}}
* {{< link "mailto:contact@revolunet.com" >}}
* {{< link "https://assemble.io" Assemble >}}

Example `link` input with a title:

```markdown
{{</* link "https://github.com/upstage/" Upstage "Visit Upstage!" */>}}
Or
{{</* link href="https://github.com/upstage/" content=Upstage title="Visit Upstage!" */>}}
```

The rendered output looks like this (hover over the link, there should be a tooltip):

{{< link "https://github.com/upstage/" Upstage "Visit Upstage!" >}}

## image {#image}

{{< version 0.2.0 changed >}}

`image` shortcode is an alternative to [`figure` shortcode](../theme-documentation-built-in-shortcodes#figure). `image` shortcode can take full advantage of the dependent libraries of [lazysizes](https://github.com/aFarkas/lazysizes) and [lightgallery.js](https://github.com/sachinchoolur/lightgallery.js).

{{< version 0.2.10 >}} The complete usage of [local resource references](../theme-documentation-content#contents-organization) is supported.

The `image` shortcode has the following named parameters:

* **src** *[required]* (**first** positional parameter)

    URL of the image to be displayed.

* **alt** *[optional]* (**second** positional parameter)

    Alternate text for the image if the image cannot be displayed, the default value is the value of the **src** parameter.

    *Markdown or HTML format is supported.*

* **caption** *[optional]* (**third** positional parameter)

    Image caption.

    *Markdown or HTML format is supported.*

* **title** *[optional]*

    Image title that will be shown when hovering on the image.

* **class** *[optional]*

    `class` attribute of the HTML `figure` tag.

* **src_s** *[optional]*

    URL of the image thumbnail, used for lightgallery, the default value is the value of the **src** parameter.

* **src_l** *[optional]*

    URL of the HD image, used for lightgallery, the default value is the value of the **src** parameter.

* **height** *[optional]*

    `height` attribute of the image.

* **width** *[optional]*

    `width` attribute of the image.

* **linked** *[optional]*

    Whether the image needs to be hyperlinked, the default value is `true`.

* **rel** *[optional]*

    Additional `rel` attributes of the HTML `a` tag, if **linked** parameter is set to `true`.

Example `image` input:

```markdown
{{</* image src="/images/lighthouse.webp" caption="Lighthouse (`image`)" src_s="/images/lighthouse-small.webp" src_l="/images/lighthouse-large.webp" */>}}
```

The rendered output looks like this:

{{< image src="/images/lighthouse.webp" caption="Lighthouse (`image`)" src_s="/images/lighthouse-small.webp" src_l="/images/lighthouse-large.webp" >}}

## admonition

The `admonition` shortcode supports **12** types of banners to help you put a notice on your page.

*Markdown or HTML format in the content is supported.*

{{< admonition >}}
A **note** banner
{{< /admonition >}}

{{< admonition abstract >}}
An **abstract** banner
{{< /admonition >}}

{{< admonition info >}}
A **info** banner
{{< /admonition >}}

{{< admonition tip >}}
A **tip** banner
{{< /admonition >}}

{{< admonition success >}}
A **success** banner
{{< /admonition >}}

{{< admonition question >}}
A **question** banner
{{< /admonition >}}

{{< admonition warning >}}
A **warning** banner
{{< /admonition >}}

{{< admonition failure >}}
A **failure** banner
{{< /admonition >}}

{{< admonition danger >}}
A **danger** banner
{{< /admonition >}}

{{< admonition bug >}}
A **bug** banner
{{< /admonition >}}

{{< admonition example >}}
An **example** banner
{{< /admonition >}}

{{< admonition quote >}}
A **quote** banner
{{< /admonition >}}

The `admonition` shortcode has the following named parameters:

* **type** *[optional]* (**first** positional parameter)

    Type of the `admonition` banner, the default value is `note`.

* **title** *[optional]* (**second** positional parameter)

    Title of the `admonition` banner, the default value is the value of the **type** parameter.

* **open** *[optional]* (**third** positional parameter) {{< version 0.2.0 changed >}}

    Whether the content will be expandable by default, the default value is `true`.

Example `admonition` input:

```markdown
{{</* admonition type=tip title="This is a tip" open=false */>}}
A **tip** banner
{{</* /admonition */>}}
Or
{{</* admonition tip "This is a tip" false */>}}
A **tip** banner
{{</* /admonition */>}}
```

The rendered output looks like this:

{{< admonition tip "This is a tip" false >}}
A **tip** banner
{{< /admonition >}}

## music

The `music` shortcode embeds a responsive music player based on [APlayer](https://github.com/MoePlayer/APlayer) and [MetingJS](https://github.com/metowolf/MetingJS).

There are three ways to use the `music` shortcode.

### Custom Music URL {#custom-music-url}

{{< version 0.2.10 >}} The complete usage of [local resource references](../theme-documentation-content#contents-organization) is supported.

The `music` shortcode has the following named parameters by custom music URL:

* **server** *[required]*

    URL of the custom music.

* **name** *[optional]*

    Name of the custom music.

* **artist** *[optional]*

    Artist of the custom music.

* **cover** *[required]*

    URL of the custom music cover.

Example `music` input by custom music URL:

```markdown
{{</* music url="/music/Wavelength.mp3" name=Wavelength artist=oldmanyoung cover="/images/Wavelength.webp" */>}}
```

The rendered output looks like this:

{{< music url="/music/Wavelength.mp3" name=Wavelength artist=oldmanyoung cover="/images/Wavelength.webp" >}}

### Music Platform URL Automatic Identification {#automatic-identification}

The `music` shortcode has one named parameter by music platform URL automatic identification:

* **auto** *[required]* (**first** positional parameter)

    URL of the music platform URL for automatic identification,
    which supports `netease`, `tencent` and `xiami` music platforms.

Example `music` input by music platform URL automatic identification:

```markdown
{{</* music auto="https://music.163.com/#/playlist?id=60198" */>}}
Or
{{</* music "https://music.163.com/#/playlist?id=60198" */>}}
```

The rendered output looks like this:

{{< music auto="https://music.163.com/#/playlist?id=60198" >}}

### Custom Server, Type and ID {#custom-server}

The `music` shortcode has the following named parameters by custom music platform:

* **server** *[required]* (**first** positional parameter)

    [`netease`, `tencent`, `kugou`, `xiami`, `baidu`]

    Music platform.

* **type** *[required]* (**second** positional parameter)

    [`song`, `playlist`, `album`, `search`, `artist`]

    Type of the music.

* **id** *[required]* (**third** positional parameter)

    Song ID, or playlist ID, or album ID, or search keyword, or artist ID.

Example `music` input by custom music platform:

```markdown
{{</* music server="netease" type="song" id="1868553" */>}}
Or
{{</* music netease song 1868553 */>}}
```

The rendered output looks like this:

{{< music netease song 1868553 >}}

### Other Parameters {#other-parameters}

The `music` shortcode has other named parameters applying to the above three ways:

* **theme** *[optional]*

    {{< version 0.2.0 changed >}} the Main colour of the music player, the default value is `#448aff`.

* **fixed** *[optional]*

    Whether to enable fixed mode, the default value is `false`.

* **mini** *[optional]*

    Whether to enable mini mode, the default value is `false`.

* **autoplay** *[optional]*

    Whether to autoplay music, the default value is `false`.

* **volume** *[optional]*

    Default volume when the player is first opened, which will be remembered in the browser, the default value is `0.7`.

* **mutex** *[optional]*

    Whether to pause other players when this player starts playing, the default value is `true`.

The `music` shortcode has the following named parameters only applying to the type of music list:

* **loop** *[optional]*

    [`all`, `one`, `none`]

    Loop mode of the music list, the default value is `none`.

* **order** *[optional]*

    [`list`, `random`]

    Play order of the music list, the default value is `list`.

* **list-folded** *[optional]*

    Whether the music list should be folded at first, the default value is `false`.

* **list-max-height** *[optional]*

    Max height of the music list, the default value is `340px`.


## aplayer and audio

{{< version 0.2.14 >}}

If you need more advanced controls (custom playlist, mini mode, custom audio type...) over the music player, you can use the `aplayer` shortcode along with the `audio` shortcode to reach full power of [APlayer.js](https://aplayer.js.org).

The `aplayer` shortcode is used to create an `APlayer` instance, and the `audio` shortcode is used to store data about each music file. Please refer to [APlayer.js documentation](https://aplayer.js.org/#/home?id=options) for all options.

Example `aplayer` and `audio` input:

```markdown
{{</* aplayer fixed=false mini=false autoplay=false theme="#b7daff" loop="all" order="list" preload="auto" volume=0.7 mutex=true lrcType=1 listFolded=false listMaxHeight="" storageName="aplayer-setting" */>}}
    {{</* audio name="Wavelength" artist="oldmanyoung" url="/music/Wavelength.mp3" cover="/images/Wavelength.webp" /*/>}}
    {{</* audio name="Wavelength" artist="oldmanyoung" url="/music/Wavelength.mp3" cover="/images/Wavelength.webp" */>}}
        [00:00.00]APlayer audio1
        [00:04.01]is
        [00:08.02]amazing
    {{</* /audio */>}}
{{</* /aplayer */>}}
```

Example `aplayer` and `audio` output:

{{< aplayer fixed=false mini=false autoplay=false theme="#b7daff" loop="all" order="list" preload="auto" volume=0.7 mutex=true lrcType=1 listFolded=false listMaxHeight="" storageName="aplayer-setting" >}}
    {{< audio name="Wavelength" artist="oldmanyoung" url="/music/Wavelength.mp3" cover="/images/Wavelength.webp" />}}
    {{< audio name="Wavelength" artist="oldmanyoung" url="/music/Wavelength.mp3" cover="/images/Wavelength.webp" >}}
        [00:00.00]APlayer audio1
        [00:04.01]is
        [00:08.02]amazing
    {{< /audio >}}
{{< /aplayer >}}

Note that these shortcodes cannot be used separately and only named parameters are supported.

If you place the LRC inside the `audio` shortcode, it is passed to the APlayer as a JS string, so the `lrcType` needs to be set to 1. If you set the link to the LRC file through the `lrc` parameter, it will be passed as an LRC file, so the `lrcType` needs to be set to 3.

## bilibili

{{< version 0.2.0 changed >}}

The `bilibili` shortcode embeds a responsive video player for bilibili videos.

When the video only has one part, only the BV `id` of the video is required, e.g.:

```code
https://www.bilibili.com/video/BV1Sx411T7QQ
```

Example `bilibili` input:

```markdown
{{</* bilibili BV1Sx411T7QQ */>}}
Or
{{</* bilibili id=BV1Sx411T7QQ */>}}
```

The rendered output looks like this:

{{< bilibili id=BV1Sx411T7QQ >}}

When the video has multiple parts, in addition to the BV `id` of the video,
`p` is also required, whose default value is `1`, e.g.:

```code
https://www.bilibili.com/video/BV1TJ411C7An?p=3
```

Example `bilibili` input with `p`:

```markdown
{{</* bilibili BV1TJ411C7An 3 */>}}
Or
{{</* bilibili id=BV1TJ411C7An p=3 */>}}
```

The rendered output looks like this:

{{< bilibili id=BV1TJ411C7An p=3 >}}


## script

{{< version 0.2.8 >}}

`script` is a shortcode to insert custom **:(fab fa-js fa-fw): Javascript** in your post.

{{< admonition >}}
The script content can be guaranteed to be executed in order after all third-party libraries are loaded. So you are free to use third-party libraries.
{{< /admonition >}}

Example `script` input:

```markdown
{{</* script */>}}
console.log('Just DoIt!');
{{</* /script */>}}
```

You can see the output in the console of the developer tool.

{{< script >}}
console.log('Just DoIt!');
{{< /script >}}

## friend

{{< version 0.2.11 >}}

`friend` is a shortcode to insert a friend link to your friend's site in your post.

The `friend` shortcode has the following named parameters:

* **name** *[required]* (**first** positional parameter)

    Your friend site's name.

* **url** *[required]* (**second** positional parameter)

    The link to your friend site.

* **avatar** *[required]* (**third** positional parameter)

    Your friend site's avatar.

* **bio** *[required]* (**fourth** positional parameter)

    A short bio of your friend site.

Example `friend` input:

```markdown
{{</* friend "PCloud" "https://github.com/HEIGE-PCloud/" "https://avatars.githubusercontent.com/u/52968553?v=4" "This is PCloud~💤" */>}}
Or
{{</* friend name="PCloud" url="https://github.com/HEIGE-PCloud/" avatar="https://avatars.githubusercontent.com/u/52968553?v=4" bio="This is PCloud~💤" */>}}
```

The rendered output looks like this:

{{< friend name="PCloud" url="https://github.com/HEIGE-PCloud/" avatar="https://avatars.githubusercontent.com/u/52968553?v=4" bio="This is PCloud~💤" >}}

## showcase

{{< version 0.2.12 >}}

`showcase` is a shortcode to insert a showcase of your project in the post.

The `showcase` shortcode has the following named parameters:

* **title** *[required]* (**first** positional parameter)

    The title of your showcase.

* **summary** *[required]* (**second** positional parameter)

    A brief introduction to your project.

* **image** *[required]* (**third** positional parameter)

    The url to the preview image.

* **link** *[required]* (**fourth** positional parameter)

    The url to your project page.

* **column** *[optional]* (**fifth** positional parameter)

    This parameter defines how many showcases are in each row. The default value is 2, which means there will have two showcases in each row. You can change it to 1, 2 or 3. It’s important to note that when a user visits the website on a small screen, the number of the column may be auto-adjusted to provide the best experience.

Example `showcase` input:

```markdown
{{</* showcase title="Theme Documentation - Basics" summary="Discover what the Hugo - DoIt theme is all about and the core-concepts behind it." image="/theme-documentation-basics/featured-image.webp" link="/theme-documentation-basics" */>}}
Or
{{</* showcase "Theme Documentation - Basics" "Discover what the Hugo - DoIt theme is all about and the core-concepts behind it." "/theme-documentation-basics/featured-image.webp" "/theme-documentation-basics" */>}}
```

The rendered output looks like this:

{{< showcase title="Theme Documentation - Basics" summary="Discover what the Hugo - DoIt theme is all about and the core-concepts behind it." image="/theme-documentation-basics/featured-image.webp" link="/theme-documentation-basics" >}}

## math

{{< version 0.2.12 >}}

`math` is a shortcode to insert a math expression in your post. This can prevent [Goldmark](https://gohugo.io/getting-started/configuration-markup/#goldmark) from parsing math expressions into HTML. You no longer need to escape special characters inside this shortcode.

Example `math` input:

```markdown
{{</* math */>}}$\|\boldsymbol{x}\|_{0}=\sqrt[0]{\sum_{i} x_{i}^{0}}${{</* /math */>}}
Or
{{</* math */>}}
$$\|\boldsymbol{x}\|_{0}=\sqrt[0]{\sum_{i} x_{i}^{0}}$$
{{</* /math */>}}
```

The rendered output looks like this:

{{< math >}}$\|\boldsymbol{x}\|_{0}=\sqrt[0]{\sum_{i} x_{i}^{0}}${{< /math >}}

{{< math >}}
$$\|\boldsymbol{x}\|_{0}=\sqrt[0]{\sum_{i} x_{i}^{0}}$$
{{< /math >}}
