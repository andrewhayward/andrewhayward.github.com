---
layout: default
title: Labs > WordPress > Shortbread
header: Shortbread
---

A self-hosted short URL plugin for WordPress. [Available on GitHub](https://github.com/andrewhayward/shortbread).

## Configuration

<figure>
	<img src="/media/images/shortbread/admin-screen.png" alt="A text box for your short domain, and toggles for link redirection and link menu options">
	<figcaption>The Shortbread admin screen</figcaption>
</figure>

There are three configuration options:

1. _Short URL domain_  
   Fairly self-explanatory -- the domain which you wish to use for your short URLs

2. _Redirect links_  
   If you use WordPress links, you can use Shortbread as a URL shortener for any webpage you want. For example, this page exists at `arh.im/lb`.

3. _Force Links menu_  
   As of WordPress 3.5, the links menu doesn't show up if you're not using bookmarks. Turn this on to force that menu option to show up.

## Usage

Shortbread introduces a new function -- `has_shortlink()` -- which tries to indicate whether a short URL is available in your current context. This allows you to put things like this in your templates.

{% highlight php %}
<?php if (has_shortlink()): ?>
<link rel="shortlink" href="<?php echo wp_get_shortlink(); ?>">
<?php endif; ?>
{% endhighlight %}

Otherwise, just use [`wp_get_shortlink()`](http://codex.wordpress.org/Function_Reference/wp_get_shortlink) or [`the_shortlink()`](http://codex.wordpress.org/Function_Reference/the_shortlink) as before. Shortbread tries to stay out of the way as much as possible.
