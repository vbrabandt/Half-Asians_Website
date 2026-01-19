# Half-Asians Website (WIP)

This is the official website for Half-Asians, built using Jekyll and based on the [minimal-music-project](https://github.com/ItsPatrq/minimal-music-project) theme.

[![LICENSE](https://img.shields.io/badge/license-MIT-lightgrey.svg)](LICENSE.txt)
[![Jekyll](https://img.shields.io/badge/jekyll-%3E%3D%203.9-blue.svg)](https://jekyllrb.com/)

## Getting Started

This site is built with Jekyll, a static site generator. To run it locally:

1. Install dependencies:

   ```bash
   bundle install
   ```

2. Start the development server:

   ```bash
   bundle exec jekyll serve
   ```

3. Open your browser at `http://localhost:4000`

The site will automatically regenerate as you make changes to the content.

## Site Structure

This site uses the `jekyll-paginate-v2` plugin for pagination and `jekyll-seo-tag` for SEO tags. Configuration is managed through the `_config.yml` file and various YAML files in the `_data` directory.

### Configuration Files

Structure of `_data/menu.yml`:

* menu_pages: a list of items in menu. Each item contains information:
  * title: Menu position title
  * url: URL for href
  * category: unique identifier of category. Used to determine which menu item is selected
  * tooltip: Tooltip for menu item
* menu_contacts: a list of items to be displayed for a contact section in menu
  * faicon: FavIcon to be displayed in menu
  * url: URL for href
  * target: target value of \<a> tag

Structure of `_data/metaData.yml`:

* author: Site Author name
* logo: relative url to the logo
* clickToEnlargeImages: boolean value to enable/disable "full-screen" images on click
* lang: lang property of HTML.
* cookies: customize information about site cookies
  * enabled: determine if should show cookies pop-up
  * message: text on cookie pop-up
  * agreeButtonText: text on agree button
  * disagreeButtonText: text on disagree button
  * agreeButtonFnName: function in the `window` scope to execute on cookie agree
  * disagreeButtonFnName: function in the `window` scope to execute on cookie disagree
  * header: title of the pop-up window
  * consent: list of objects that will be rendered on a site with "cookies" layout for acceptance. Each object needs to have:
    * name: bolded on render
    * description: description of the cookie
    * cookieName: under what name it will be saved in the local storage (selected checkbox as "true", unselected as "false")
    * alwaysAgree: used for cookies, that cannot be disabled. This will make this consent appear on the "cookies" layout with checked and disabled checkbox. It does not add this cookie under *name* to localStorage

Structure of `_data/customs.yml`:

* custom-css: a list of urls to custom css files
* custom-js: a list of urls to custom javascript files

## Posts front matter parameters

### Description / excerpt

In the post feed / discography each entry will be shown with a text. This text will contain either the content of "description" property from front matter, or  [excerpt](https://jekyllrb.com/docs/posts/#post-excerpts) if the description property is missing.

### Images

There are two parameters responsible for displaying images: *image* and *responsiveImage*. The first one should have string value equal to the relative path to the image to display in a post (and post-feed / discography preview) if *responsiveImage* is not set. This path will always be used for *clickToEnlargeImages* functionality too. The *responsiveImage* is an array of objects that will be transpiled to img in DOM property *srcset*. Each object should contain two properties:

* *src* - path to the file
* *size* - image's intrinsic width in pixels

It's recommended to use *responsiveImage* for responsible image loading.

### Embedding media

Each post can have it's own associated player. Information on how to embed the player should be described under *embed\_player* parameter. Each player should have at least two parameters: *src* and *type*, where *type* will define on how to fill *src*. Supported types:

* soundcloud - src should be full url to song
* bandcamp - on a "embed song" option on bandcamp, everything after *EmbeddedPlayer/* in generated code should be put to src parameter in front matter
* youtube - src should be the *v* uri parameter, e.g. for url <https://www.youtube.com/watch?v=dfdruxvE9-0> the src should be dfdruxvE9-0
* audio_file - src should be path to file. Additionaly, required properties are name of the song (it will display in player) and boolean value *is\_relative\_url* (for easy access to files served from the same domain)

## Adding Content

### Adding News/Posts

Create new markdown files in `home/_posts/` following the naming convention: `YYYY-MM-DD-title.markdown`

### Adding Releases

Create new markdown files in `discography/_posts/` following the same naming convention.

### Adding Collaborations

Create new markdown files in `collaborations/_posts/`.

## Credits

This website is built using the [minimal-music-project](https://github.com/ItsPatrq/minimal-music-project) Jekyll theme.

## License

This project uses a **dual licensing** approach:

### Code License (MIT)

All code, scripts, stylesheets, and technical implementation files are licensed under the [MIT License](LICENSE.txt).

* Original theme: Copyright (c) 2021 Patryk Bieszke  
* Website modifications: Copyright (c) 2026 Half-Asians

The MIT License allows anyone to freely use, modify, and distribute the code.

Custom Volume Slider was developed with the fundaments based on [codepen project](https://codepen.io/EmNudge/pen/rRbLJQ), thus this component is licensed under [Copyright (c) 2021 by EmNudge](https://codepen.io/EmNudge/pen/rRbLJQ).

### Content License (All Rights Reserved)

All creative content including blog posts, music, images, videos, and artwork is:

* Copyright (c) 2026 Half-Asians
* **All Rights Reserved** - may not be reproduced or distributed without permission

For content licensing inquiries, please contact the band directly.
