[![](https://i.imgur.com/zNBkzj1.png)](https://beautifuljekyll.com/plans/)

# Beautiful Jekyll - WIN GitLab Pages theme template

[![Gem Version](https://badge.fury.io/rb/beautiful-jekyll-theme.svg)](https://badge.fury.io/rb/beautiful-jekyll-theme)

> By [Dean Attali](https://deanattali.com) &middot; [Demo](https://beautifuljekyll.com/)

**Beautiful Jekyll** is a ready-to-use template to help you create a beautiful website quickly. Perfect for personal sites, blogs, or simple project websites.  [Check out a demo](https://beautifuljekyll.com) of what you'll get after just two minutes.  You can also look at [my personal website](https://deanattali.com) or [my consulting website](https://attalitech.com) to see it in use, or see [examples of websites](http://beautifuljekyll.com/examples) other people created using this theme.

**If you enjoy Beautiful Jekyll, please consider [supporting [Dean Attali](https://github.com/sponsors/daattali) for over 5 years of development (and to unlock rewards!) ❤**


# Build your website in a few easy steps

There's a very easy way to use this theme, and there's a hard way. For most people (including myself!), the easy route is recommended. If you're an advanced user and want to tinker with the hard way (using ruby gems), then [skip the easy way](https://github.com/daattali/beautiful-jekyll#the-hard-way-using-ruby-gems) if you know what you're doing.

## The easy way (recommended!)

> A reminder for *advanced users only*: you can follow the instructions for [building locally](https://beautifuljekyll.com/getstarted/#install-steps-hard) if you want more control but higher difficulty

### 1. Fork this project

Fork this project by clicking the __*Fork*__ button at the top right corner of this page. Forking means that you now copied this entire project and all the files into your account.

### 2. Rename the project

In your version of the project, click on __*Settings*__ on the left (the cog icon) and rename the project (*Project name*) to something meaningful to you. In the __*Advanced*__ settings (bottom of the page), check that the path matches what you expect given your desired project name. 

### 3. Set the _config.yml url and update the "served at " description

In the file `_config.yml`, update line 16 so the baseurl matches the path of your project. The baseurl should start with `"/pages/"` and end without a trailing `/`. 

In the project settings, update the description to match the address of where your build page will be rendered. This is the combnined url+baseurl addresses from your `_config.yml`.

### 4. Turn on CI Runners

You need to enable a "runner" in order for GitLab to "build"/"serve" your page. Go to __*Settings*__ > __*CI/CD*__ > __*Runners*__. Tick `enable shared runners`.

### 5. Customize your website settings

Edit the `_config.yml` file to change any additional settings you want. To edit the file, click on it to view the file and then click on the pencil icon to edit it.  The settings in the file are self-explanatory and there are comments inside the file to help you understand what each setting does. Any line that begins with a hashtag (`#`) is a comment, and the other lines are actual settings.

**We suggest you start by making a small change (for example updating the title or author) then commit this change. Making the commit will trigger the CI, which will take a few moments to build your page.** You can monitor the progress of the CI in `CI/CD pipleines` (rocket icon on the left navigation bar).

### 6. Add your own content

To add pages to your site, you can either write a markdown file (`.md`) or you can write an HTML file. It's much easier to write markdown than HTML, so that's the recommended approach ([here's a great tutorial](https://markdowntutorial.com/) if you need to learn markdown in 5 minutes).

To see an example of a markdown file, click on any file that ends in `.md`, for example [`aboutme.md`](./aboutme.md). On that page you can see some nicely formatted text (there's a word in bold, a link, a few bullet points), and if you click on the pencil icon to edit the file, you'll see the markdown code that generated the pretty text. Very easy!

In contrast, look at [`tags.html`](./tags.html). That's how your write HTML - not as pretty. So stick with markdown if you don't know HTML.

Any markdown or HTML file that you create will be available on your website under `https://<yourusername>.github.io/<pagename>`. For example, if you create a file `about.md` (or `about.html`) then it'll exist at `https://<yourusername>.github.io/about`.

Files you create inside the [`_posts`](./_posts) directory will be treated as blog entries. You can look at the existing files there to get an idea of how to write blog posts. Note the format of the blog post files - they must follow the naming convention of `YEAR-MONTH-DAY-title.md`. After you successfully add your own post, you can delete the existing files inside [`_posts`](./_posts) to remove the sample posts, as those are just demo posts to help you learn.

#### Examples

Take a look at the [Plasticity Group RED January recruitment page](https://open.win.ox.ac.uk/pages/plasticity/RED-January/) to see a slim version of this theme hosted on WIN GitLab.

Take a look at the [Open Research Calendar](https://openresearchcalendar.org) and [Open Science Room 2020](https://ohbm.github.io/osr2020/) pages to see examples of customised versions of this theme (note both of these are hosted via GitHub rather than GitLab, so the `.gitlab-ci.yml` file is not present in these, and the `baseurl` and `url` are not defined in the `_config.yml`). Don't forget to look at the GitHub repositories for both sites (follow the GitHub logos on the bottom) to see how the customisation was acheived.

# Customizing parameters for each page

**One last important thing**: In order to have your new pages use this template and not just be plain HTML pages, **you must add [YAML front matter](https://jekyllrb.com/docs/front-matter/) to the top of each page**:


```
---
---
```

This is where you'll be able to give each page some extra parameters (such as a title, a subtitle, an image, etc - [below is a list of all parameters](#supported-parameters)). Add any parameters you want between these two dashed lines, for example:

```
---
title: Contact me
subtitle: Here you'll find all the ways to get in touch with me
---
```

If you don't want to use any parameters on a page, you still need to use the two dashed lines. If you don't, then your file will be shown as-is without the Beautiful Jekyll template.

You can look at the top of [`aboutme.md`](https://raw.githubusercontent.com/daattali/beautiful-jekyll/master/aboutme.md) as an example.

**Important takeaway: ALWAYS add the YAML front matter, which is two lines of three dashes, to EVERY page. If you have any parameters, they go between the two lines.**

# Supported parameters

Below is a list of the parameters that Beautiful Jekyll supports (any of these can be added to the YAML front matter of any page). Remember to also look in the `_config.yml` file to see additional site-wide settings.

## Main parameters

These are the basic YAML parameters that you are most likely to use on most pages.

Parameter   | Description
----------- | -----------
title       | Page or blog post title
subtitle    | Short description of page or blog post that goes under the title
tags        | List of tags to categorize the post. Separate the tags with commas and place them inside square brackets. Example: `[personal, analysis, finance]`
cover-img   | Include a large full-width image at the top of the page. You can either provide the path to a single image (eg. `"/path/to/img"`) , or a list of images to cycle through (eg. `["/path/img1", "/path/img2"]`). If you want to add a caption to an image, then you must use the list notation (use `[]` even if you have only one image), and each image should be provided as `"/path/to/img" : "Caption of image"`.
thumbnail-img | For blog posts, if you want to add a thumbnail that will show up in the feed, use `thumbnail-img: /path/to/image`. If no thumbnail is provided, then `cover-img` will be used as the thumbnail. You can use `thumbnail-img: ""` to disable a thumbnail.
comments    | If you want do add comments to a specific page, use `comments: true`. Comments only work if you enable one of the comments providers (Facebook, disqus, staticman, utterances, giscus) in `_config.yml` file. Comments are automatically enabled on blog posts but not on other pages; to turn comments off for a specific post, use `comments: false`.

## Parameters for SEO and social media sharing

These parameters let you control what information shows up when a page is shown in a search engine (such as Google) or gets shared on social media (such as Twitter/Facebook).

Parameter   | Description
----------- | -----------
share-title | A title for the page. If not provided, then `title` will be used, and if that's missing then the site title (from `_config.yml`) is used.
share-description | A brief description of the page. If not provided, then `subtitle` will be used, and if that's missing then an excerpt from the page content is used.
share-img   | The image to show. If not provided, then `cover-img` or `thumbnail-img` will be used if one of them is provided.

## Less commonly used parameters

These are parameters that you may not use often, but can come in handy sometimes.

Parameter   | Description
----------- | -----------
readtime    | If you want a post to show how many minutes it will take to read it, use `readtime: true`.
show-avatar | If you have an avatar configured in the `_config.yml` but you want to turn it off on a specific page, use `show-avatar: false`.
social-share | By default, every blog post has buttons to share the page on social media. If you want to turn this feature off, use `social-share: false`.
nav-short   | By default, the navigation bar gets shorter after scrolling down the page. If you want the navigation bar to always be short on a certain page, use `nav-short: true`
gh-repo   | If you want to show GitHub buttons at the top of a post, this sets the GitHub repo name (eg. `daattali/beautiful-jekyll`). You must also use the `gh-badge` parameter to specify what buttons to show.
gh-badge  | Select which GitHub buttons to display. Available options are: [star, watch, fork, follow]. You must also use the `gh-repo` parameter to specify the GitHub repo.
last-updated | If you want to show that a blog post was updated after it was originally released, you can specify an "Updated on" date.
layout      | What type of page this is (default is `post` for blog posts and `page` for other pages). See _Page types_ section below for more information.

## Advanced parameters

These are advanced parameters that are only useful for people who need very fine control over their website.

Parameter   | Description
----------- | -----------
footer-extra | If you want to include extra content below the social media icons in the footer, create an HTML file in the `_includes/` folder (for example `_includes/myinfo.html`) and set `footer-extra` to the name of the file (for example `footer-extra: myinfo.html`). Accepts a single file or a list of files.
before-content | Similar to `footer-extra`, but used for including HTML before the main content of the page (below the title).
after-content | Similar to `footer-extra`, but used for including HTML after the main content of the page (above the footer).
head-extra   | Similar to `footer-extra`, but used if you have any HTML code that needs to be included in the `<head>` tag of the page.
language    | HTML language code to be set on the page's &lt;html&gt; element.
full-width  | By default, page content is constrained to a standard width. Use `full-width: true` to allow the content to span the entire width of the window.
js          | List of local JavaScript files to include in the page (eg. `/assets/js/mypage.js`)
ext-js      | List of external JavaScript files to include in the page (eg. `//cdnjs.cloudflare.com/ajax/libs/underscore.js/1.8.2/underscore-min.js`). External JavaScript files that support [Subresource Integrity (SRI)](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity) can be specified using the `href` and `sri` parameters eg.<br/>`href: "//code.jquery.com/jquery-3.1.1.min.js"`<br/>`sri: "sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8="`
css         | List of local CSS files to include in the page
ext-css      | List of external CSS files to include in the page. External CSS files using SRI (see `ext-js` parameter) are also supported.

## Page types

- **post** - To write a blog post, add a markdown or HTML file in the `_posts` folder. As long as you give it YAML front matter (the two lines of three dashes), it will automatically be rendered like a blog post. Look at the existing blog post files to see examples of how to use YAML parameters in blog posts.
- **page** - Any page outside the `_posts` folder that uses YAML front matter will have a very similar style to blog posts.
- **home** - The home layout is meant to act as the homepage of your blog posts - it will display all your blog posts, sorted from newest to oldest. A file using the `home` layout must be named `index.html` (not `index.md` or anything else!).
- **minimal** - If you want to create a page with minimal styling (ie. without the bulky navigation bar and footer), assign `layout: minimal` to the YAML front matter.
- If you want to completely bypass the template engine and just write your own HTML page, simply omit the YAML front matter. Only do this if you know how to write HTML!

# Featured users (success stories!)

Visit the [Official website](http://beautifuljekyll.com/examples) to see sample websites using Beautiful Jekyll.

If you'd like to showcase yourself and join this list, [upgrading to the Individual plan](https://github.com/sponsors/daattali/sponsorships?&tier_id=7362) will give you that publicity plus some other rewards!

# FAQ and support

Visit the [official FAQ page](https://beautifuljekyll.com/faq) for answers to commonly asked questions.

Beautiful Jekyll is used by 50,000+ people with wildly varying degrees of web skills, so it's impossible to answer all the questions that may arise. For any question that's not specifically related to Beautiful Jekyll and is more about Jekyll or web development in general, the answer can often be found on Google, in the [Jekyll documentation](https://jekyllrb.com/), or on the [Jekyll support forum](https://talk.jekyllrb.com/).

To receive support, select one of the [different plans](https://beautifuljekyll.com/plans) Beautiful Jekyll offers. You can also use the [Discussions](https://github.com/daattali/beautiful-jekyll/discussions) area to try to get help from the community.

# Contributions

Thank you to [all past contributors](https://github.com/daattali/beautiful-jekyll/graphs/contributors). If you find any problems or would like to contribute in any way, feel free to create a pull request/open an issue/send me a message.

You can also contribute by becoming an [official sponsor](https://github.com/sponsors/daattali/sponsorships?tier_id=39856) to help keep Beautiful Jekyll well-maintained.

# Credits

This template was not made *entirely* from scratch. I'd like to give special thanks to [Jekyll Now](https://github.com/barryclark/jekyll-now) and [Bootstrap Clean Blog](https://github.com/IronSummitMedia/startbootstrap-clean-blog), from whom I've taken several ideas initially.

I'd also like to thank [Dr. Jekyll's Themes](https://drjekyllthemes.github.io/), [Jekyll Themes](http://jekyllthemes.org/), and another [Jekyll Themes](http://jekyllrc.github.io/jekyllthemes/) for featuring Beautiful Jekyll in their Jekyll theme directories.
