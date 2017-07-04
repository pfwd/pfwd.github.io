---
title: Test Post 3
date:   2015-02-17 16:16:01 -0600
categories: php
permalink: /blog/:categories/:title
layout: post
---

When rendering a Symfony2 form in a twig template I often get caught out when applying css classes to a label.

Label attributes are handled differently from a forms attribute and this often leads to confusion.

## Form attributes

Adding css class attributes to a Symfony form field is done like so:

{% highlight php %}
    <?php echo 'hello'; ?>
{% endhighlight %} 
<!-- {% gist 9ef332d380f63fb8c935898f14f73407 %} -->

## Label attributes

As you can see the parameter attr is supplied with a key of class. This is not the case when adding css class attributes to labels.

Not only is the attr parameter named differently but its also the third parameter of the label control:

{% gist d67965bc2e5da1c411e347787793bfc2 %}

So the parameter you need is label_attr. The second parameter is the label value. Set this to null if you want to use the label value defined in the form class.

You can find out more about using labels in twig templates by reading the Symfony2 documentation