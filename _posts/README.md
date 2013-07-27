# Basic Options Format Post OmaGue.net

### Default Heading for Post and Page

``` yaml
---
layout: post
title: Sample Post
description: "Just about everything you'll need to style in the theme: headings, paragraphs, blockquotes, tables, code blocks, and more."
modified: 2013-05-31
category: blog
tags: [sample post, sample tag, sample]
image:
  feature: default-head.jpg
  thumb: thumbnail-image.jpg #keep it square 200x200 px is good
comments: true
---
```

### Default syntax highlight

Writing sample syntax highlight

``` css
{% highlight css %}
/*CSS JABLAI*/
body{
   max-width:100%;
   margin:0 auto;
   display:inline;
   background:white;
   }
#muka{
   position:fixed;
   }
.badan{
   background:transparent;
   }
.celana-dalem{
   display:none;
   }
{% endhighlight %}
```

### Default images post

Exemplified that the location of the calling of the image file is in the folder `/assets/img/`

``` yaml
![alt images post]({{ site.url }}/assets/img/sample-image.jpg)
{: .pull-right}
```