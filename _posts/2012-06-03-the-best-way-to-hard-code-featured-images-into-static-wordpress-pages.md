---
layout: single
title: "The Best Way to Hard Code Featured Images Into Static Wordpress Pages"
date: 2012-06-03 23:32
author: mrbrant
comments: true
categories: [CSS, Development, Development, Featured Image, HTML, Template, Theme, Wordpress, Wordpress Development]
---
As Wordpress is becoming a mainstream CMS rather than just a blog software, developers are constantly looking for novel ways to improve themes. Because I am personally a big fan of full width header images on websites, I have found a great way to define featured images in my theme files, saving my clients a lot of time.

The reality is that the average Westerner is too lazy to read, so if you don't engage them immediately with images they are going to go look at kittens and Harry Potter memes on Tumblr instead.

<img class="alignright size-full wp-image-1563" title="Wordpress Set Featured Image" src="http://michaelbrant.com/wp-content/uploads/2012/06/Screen-Shot-2012-06-03-at-11.28.21-PM.png" alt="Wordpress Set Featured Image" width="287" height="79" />For those familiar the <a href="http://codex.wordpress.org/">Wordpress Codex</a>, the Wordpress developers have provided us with tons of useful shortcuts for use in theme development. One of the best is the Featured Image. Each page and post can have a featured image which is defined on the right sidebar of the Post Editor screen using the media browser to upload an image. Previously we had to use custom fields for this but now there is a great "happy clicky" interface.
<h3>Defining Featured Images</h3>
To insert the featured image into a theme file, one must first define the featured image in the <code>functions.php</code> file.

This can be done as follows:
{code type=php}
add_theme_support( 'post-thumbnails' );
{/code}

Where 'post-thumbnails' can be any name that you want. This is especially useful because you can declare different sizes of the same featured image. For example, for use on your <code>index.php</code>, <code>single.php</code> and <code>category.php</code> pages.

{code type=php}
add_image_size('name',width,height, true);
{/code}

For example:
{code type=php}
add_image_size('michael-is-awesome',600,400, true);
{/code}

You can also choose to define a featured image for only certain taxonomies such as "post" or "page" or "category" as follows:

{code type=php}
add_theme_support('post-thumbnails', array('page'));
{/code}
<h3>Using Featured Images in Templates</h3>
Now that the featured images have been declared, we can call them in the theme file. The following sizes can be declared within <code>Settings &gt; Media</code> within Wordpress and then used within the theme files:
<h4>Large</h4>
{code type=php}
&lt;?php the_post_thumbnail('large');?&gt;
{/code}
<h4>Medium</h4>
{code type=php}
&lt;?php the_post_thumbnail('medium');?&gt;
{/code}
<h4>Thumbnail</h4>
{code type=php}
&lt;?php the_post_thumbnail('thumbnail');?&gt;
{/code}

If you defined custom sizes within the <code>functions.php</code> file you can call custom sizes as follows:
<h4>Custom Defined</h4>
{code type=php}
&lt;?php the_post_thumbnail('michael-is-awesome');?&gt;
{/code}

The advantage of using these pre-defined sizes is that Wordpress automatically generates them when the image is uploaded. This protects you from the security vulnerabilities of the <a href="http://www.darrenhoyt.com/2008/04/02/timthumb-php-script-released/">Tim Thumbs</a> script by eliminating it from the equation. It also causes the website to load faster and decreases bandwidth consumption by loading an optimized version of the image that is exactly the correct size.

The featured image can also be called in the template dynamically using the following script:
<h4>Custom Size</h4>
{code type=php}
&lt;?php the_post_thumbnail( array (width,height) );?&gt;
{/code}

For example:
{code type=php}
&lt;?php the_post_thumbnail( array (250,150) );?&gt;
{/code}

The disadvantage of this is that the image must be dynamically resized every time the page loads, causing increased load on the server, decreased page load time and increased bandwidth consumption. If you are on a shared host and get a lot of traffic, this can be the difference of being shut down or not. In other words, don't do it.
<h3>Styling Featured Images with CSS</h3>
Use CSS to format the Thumbnail with a border, etc:
{code type=css}
.entry-content #post-thumbnail {
float: right;
border: 1px solid black;
margin: 0 0 10px 10px;
}
{/code}

Call the thumbnail within the theme file:
{code type=php}
<div class="entry-content">
<div id="post-thumbnail">&lt;div&gt;
&lt;div id="post-thumbnail"&gt;
&lt;?php the_post_thumbnail('medium');?&gt;
&lt;/div&gt;
&lt;?php the_content('Read more »'); ?&gt;
&lt;/div&gt;</div>
</div>
{/code}
