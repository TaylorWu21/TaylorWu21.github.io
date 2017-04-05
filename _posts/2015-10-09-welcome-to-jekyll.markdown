---
layout: post
title:  "Jekyll Markdown Examples"
date:   2015-10-09 00:49:37
categories: jekyll
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help

Jekyll is simple but powerfull, and can hosted easely on github.
This is cheat codes for creating beautiful article with GFM (Github Flavored Markdown).
For more information about GFM, [click here](https://help.github.com/articles/github-flavored-markdown/).

##### # Links

Example :

[click here](https://github.com/riefachan).

Return :

```
[click here](https://github.com/riefachan)
```


##### # italic

Example :

*this is italic !*

Return :

```
*this is italic !*
```


##### # bold

Example :

**this is bold !**

Return :

```
**this is bold !**
```


##### # List

Example :

* Item 1
* Item 2
* Item 3

Return :

```
* Item 1
* Item 2
* Item 3
```


##### # code

Example :

```
function hello(){
	return "Hello World!";	
}
```

Return :

{% highlight text %}
```
function hello(){
	return "Hello World!";	
}
```
{% endhighlight %}


##### # code (inline)

Example :

`echo "Hello World!";`

Return :

````
`echo "Hello World!";`
````


##### # code (with highlight)

Example :

{% highlight javascript %}
function hello(){
	return "Hello World!";	
}
{% endhighlight %}

Return :

{% highlight text %}
{%raw%}
{% highlight javascript %}
function hello(){
	return "Hello World!";	
}
{% endhighlight %}
{%endraw%}
{% endhighlight %}
