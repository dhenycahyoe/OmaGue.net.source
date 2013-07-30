#<a href="http://OmaGue.net">OmaGue.net</a> Source code


## Basic Setup for new Jekyll site

1. [Install Jekyll](http://jekyllrb.com) and read through the documentation if you haven't already.
2. Fork the [OmaGue.net repo](https://github.com/dhenycahyoe/OmaGue.net.source/fork)
3. Clone the repo you just forked to your computer.
4. Edit `_config.yml` to personalize your site.
5. Check out the sample posts in `_posts` to see examples for pulling in large feature images, assigning categories and tags, and other YAML data.
6. Read the documentation below for further customization pointers and documentation.

---

## Setup for Existing Jekyll site

1. Clone the following folders: `_includes`, `_layouts`, `assets`.
2. Clone the following files and personalize content as need: `about.md`, `blog.html`, `project.html`, `index.html`, `tags.html`, and `feed.xml`, `sitemap.xls`, `sitemap.xml`,.
3. Set the following variables in your `config.yml` file:

``` yaml
title:            OmaGue.net
description:      Cyberspace Explorers Notes
logo:             site-logo.png
disqus_shortname: omaguenet
#Comment out url when working locally to resolve base urls correctly
url:              http://localhost:4000

# Owner/author information
owner:
  name:           dhenycahyoe
  avatar:         bio-photo.jpg
  email:          dheny@omague.com
  # Social networking links used in footer. Update and remove as you like.
  twitter:        dhenycahyoe
  facebook:       DenyEkaWicahyo
  github:         dhenycahyoe
  stackexchange:  
  linkedin:       
  instagram:      
  flickr:         
  tumblr:         
  # For Google Authorship https://plus.google.com/authorship
  google_plus:    https://plus.google.com/116377306809477014805/posts

# Analytics and webmaster tools stuff goes here
google_analytics:   
google_verify:      
# https://ssl.bing.com/webmaster/configure/verify/ownership Option 2 content= goes here
bing_verify:        

# Links to include in top navigation
# For external links add external: true
links:
  - title: Blog
    url: /blog
  - title: About
    url: /about
  - title: Project
    url: /project
  - title: Blogazine
    url: http://omague.com
    external: true

# http://en.wikipedia.org/wiki/List_of_tz_database_time_zones
timezone:    Asia/Jakarta
future:      true
pygments:    true
markdown:    kramdown

# https://github.com/mojombo/jekyll/wiki/Permalinks
permalink:   /:categories/:title
```

---

## Folder Structure

``` bash
omague.github.io/
├── _includes
|    ├── browser-upgrade.html  //prompt to upgrade browser on < IE8
|    ├── disqus_comments.html  //include disqus comments
|    ├── footer.html  //site footer
|    ├── head.html  //site head
|    ├── highlight.html  //include syntax highlight
|    ├── navigation.html //site navigation and masthead
|    ├── relader.html //reladed post
|    └── scripts.html  //jQuery, plugins, GA, etc.
├── _layouts
|    ├── index-post.html  //index blog page layout
|    ├── index-project.html  //index project page layout
|    ├── page.html  //page layout
|    ├── post.html  //post layout
|    └── project.html  //project layout
├── _posts
|    ├── blog //post category blog
|    |   └── 2013-12-12-sample-post-blog.md //format blog
|    └── project //post category project 
|        └── 2013-12-12-sample-post-project.md //format blog
├── assets
|    ├── css  //preprocessed less styles. good idea to minify
|    ├── fonts //folder web fonts
|    ├── img //folder all images
|    └── js
|        ├── main.js  //jQuery plugins and settings
|        └── vendor  //all 3rd party scripts
├── _config.yml  //Site options
├── about.md  //about page
├── blog.html  //lists all posts blog from latest to oldest
├── project.html //lists all posts project from latest to oldest
├── sitemap.xml //index sitemap.xml
├── sitemap.xls //sitemap layout
├── index.html  //homepage. lists 10 latest posts
└── tags.html  //lists all posts sorted by tag
```

---

## Customization

### _config.yml

Most of the variables found here are used in the .html files found in `_includes` if you need to add or remove anything. A good place to start would be to change the title, tagline, description, logo (or avatar photo), and url of your site. When working locally comment out `url` or else you will get a bunch of broken links because they are absolute and prefixed with `{{ site.url }}` in the various `_includes` and `_layouts`. Just remember to uncomment `url` when building for deployment or pushing to **gh-pages**...

#### Disqus Comments

Create a [Disqus](http://disqus.com) account and change `disqus_shortname` in `_config.yml` to the Disqus *shortname* you just setup. To enable commenting on a post, add the following to its front matter:

``` yaml
comments: true
```

#### Owner/Author Information

Change your name, and avatar photo (crop it square at 200x200 or larger), email, and social networking urls. If you want to link to an external image on Gravatar or something similiar you'll need to edit the path in `head.html` since it assumes it is located in `/images`.

Including a link to your Google+ profile has the added benefit of displaying [Google Authorship](https://plus.google.com/authorship) in Google search results if you've went ahead and applied for it.

#### Google Analytics and Webmaster Tools

Your Google Analytics ID goes here along with meta tags for [Google Webmaster Tools](http://support.google.com/webmasters/bin/answer.py?hl=en&answer=35179) and [Bing Webmaster Tools](https://ssl.bing.com/webmaster/configure/verify/ownershi) site verification.

#### Top Navigation Links

Edit page/post titles and URLs to include in the site's navigation. For external links add `external: true`.

``` yaml
# sample top navigation links
links:
  - title: Blog
    url: /blog
  - title: About
    url: /about
  - title: Project
    url: /project
  - title: Blogazine
    url: http://omague.com
    external: true
```

#### Other Stuff

The rest is just your average Jekyll config settings. Nothing too crazy here...

### _includes

For the most part you can leave these as is since the author/owner details are pulled from `_config.yml`. That said you'll probably want to customize the copyright stuff in `footer.html` to your liking.

### Adding Posts and Pages

There are two main content layouts: `post.html` (for posts) and `page.html` (for pages). Both have support for large **feature images** that span the full-width of the screen, and both are meant for text heavy blog posts (or articles). 

#### Feature Images

A good rule of thumb is to keep feature images nice and wide so you don't push the body text too far down. An image cropped around around 1024 x 256 pixels will keep file size down with an acceptable resolution for most devices. If you want to serve these images responsively I'd suggest looking at [Picturefill](https://github.com/scottjehl/picturefill) or [Adaptive Images](http://adaptive-images.com/).

The two layouts make the assumption that the feature images live in the *images* folder. To add a feature image to a post or page just include the filename in the front matter like so. 

``` yaml
image:
  feature: feature-image-filename.jpg
  thumb: thumbnail-image.jpg #keep it square 200x200 px is good
```

#### Categories

In the sample `_posts` folder you may have noticed `category: articles` in the front matter. I like keeping all posts grouped in the same folder. If you decide to rename or add categories you will need to modify the permalink in `articles.md` along with the filename (if renaming).

For example. Say you want to group all your posts under `blog/` instead of `articles/`. In your post add `category: blog` to the front matter, rename or duplicate `articles.md` to `blog.md` and change the permalink in that file to `permalink: /blog/index.html`.

If done correctly `/blog` should be a page listing all the site's posts.

#### Post/Page Thumbnails for OG and Twitter Cards

Post and page thumbnails work the same way. These are used by [Open Graph](https://developers.facebook.com/docs/opengraph/) and [Twitter Cards](https://dev.twitter.com/docs/cards) meta tags found in `head.html`. If you don't assign a thumbnail the image you assigned to `site.owner.avatar` in `_config.yml` will be used.

#### Videos

Video embeds are responsive and scale with the width of the main content block with the help of [FitVids](http://fitvidsjs.com/).

Not sure if this only effects Kramdown or if it's an issue with Markdown in general. But adding YouTube video embeds causes errors when building your Jekyll site. To fix add a space between the `<iframe>` tags and remove `allowfullscreen`. Example below:

``` html
<iframe width="560" height="315" src="http://www.youtube.com/embed/PWf4WUoMXwg" frameborder="0"> </iframe>
```

#### Twitter Cards

Twitter cards make it possible to attach images and post summaries to Tweets that link to your content. Summary Card meta tags have been added to `head.html` to support this, you just need to [validate and apply your domain](https://dev.twitter.com/docs/cards) to turn it on.

---

## Questions?

Having a problem getting something to work or want to know why I setup something in a certain way? Ping me on Twitter [@dhenycahyoe](http://twitter.com/dhenycahyoe) or [file a GitHub Issue](https://github.com/dhenycahyoe/dhenycahyoe.github.io/issues/new).

---

## License

This theme is free and open source software, distributed under the [GNU General Public License](LICENSE) version 3 or later. So feel free to use this Jekyll theme on your site without linking back to me or using a disclaimer.

If you'd like to give me credit somewhere on your blog or tweet a shout out to [@dhenycahyoe](https://twitter.com/dhenycahyoe), that would be pretty sweet.