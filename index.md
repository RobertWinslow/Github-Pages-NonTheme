---
title: This is the title of this page.
Description: This is the description of the page's contents. It's just metadata. It won't show up in the page itself, but will show up in the preview when you share this page on Discord or the like.
---

# Hello! 

This is an example index page. 
Edit this markdown file to change the homepage of your site.

There's no fancy Jekyll magic to compile a list of your posts, 
so you'll have to manually link them like so:
[Here is a link to another page.](example-page)

And here's [an example of a link to a page in a subdirectory](subdirectory-example/hello),
showing how Jekyll parses all your markdown files unless they're contained in a folder whose name begins with `_`

---

# Markdown Test

Just for good measure, here's a pile of markdown  so you can easily test out your styling:


## Lists

- Here's an
- Unordered list
- With nested lists inside.
    - Here's an example
    - of a nested unordered list
    - and now let's go even deeper
        - 2 layers deep
            - 4 layers deep
                - 5 layers deep
- okay, that's enough of that.



1. Here's an ordered list
2. The markdown parser will automatically redo the numbers
55. This line starts with `55.` in the source file.
4. And here's some nesting behavior for ya
    1. Nest 1
        1. Nest 2
            1. Nest 3
    1. Back down to nested level 1.



Defintion Lists
: Definition lists are a nonstandard feature of markdown and not supported in Github-flavored markdown. However, they're support in kramdown, and I've found them to be very useful.

Second definition example
: This is a second example of the definition list elements.






## Text Elements

Here's some **strong bold text** and here's some *emphasized italic text*. Here's ***some that's both***. ~~Struck-thru text looks like this.~~ `Inline code looks like this`.

And here's a code block for good measure:

~~~python
def eggplant(salt, pepper, water):
    for drop in water:
        print(sprinkle(drop))
~~~

Here's a a [link](http://kramdown.gettalong.org "title text goes here") to the kramdown homepage, which has more documentation on how this markdown is parsed. (Kramdown works slightly differently than github-flavored markdown.) Links can also be defined via references like this: A link to the [kramdown hp].

[kramdown hp]: http://kramdown.gettalong.org "hp"

Here's an image: ![Title text goes here](nonsense.png)

![Title text goes here](nonsense.png)

Inline code `like this` yeh

Footnotes are notstandard, but included in kramdown [^1].

[^1]: And here is the content of the footnote.

Abbreviations are also included in kramdown. This is an HTML example.

*[HTML]: Hyper Text Markup Language

If you want some other kind of fancy styling, you'll have to manually put in a span element. This is <span style="color: red">written *in* red</span>.
This is *red*{: style="color: red"}.







## Tables


| A simple | table |
| with multiple | lines|

Now here's a table with defined header and footer rows:

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3 |

And here's the same table but with `{: rules="all"}` appended to the end, which Kramdown interprets as a property to apply to the table element. 
Huh. Apparently, [the rules attribute is deprecated], but Kramdown uses it in their examples, and I'm just copying those here. So `¯\_(ツ)_/¯`

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3
{: rules="all"}





## Math Support

To accomodate pages which display LaTeX equations, Kramdown doesn't parse any elements inside of double dollar signs `$$ $$`, and replaces the dollar signs with `\[ \]`. That way you can drop in a javascript math rendering library and everything will render smoothly.

For example, the following equation won't be rendered by default, but notice how the underscores and asterisk haven't been interpreted as markdown syntax.

$$a_x^2 + b_x^2 = c_{zy}^2 \; \sum_{i=0}^\infty  \; \frac{a_b c_d}{e*f*g}$$

To get this to render, all you have to do is plop in the code for a library like MathJax or KaTeX. 

~~~html
<!--katex math rendering-->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.12.0/dist/katex.min.css" integrity="sha384-AfEj0r4/OFrOo5t7NnNe46zW/tFgW6x/bCJG8FqQCEo3+Aro6EYUG4+cU+KJWu/X" crossorigin="anonymous">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.12.0/dist/katex.min.js" integrity="sha384-g7c+Jr9ZivxKLnZTDUhnkOnsh30B4H0rpLUpJ4jAIKs4fnJI+sEnkvrMWph2EDg4" crossorigin="anonymous"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.12.0/dist/contrib/auto-render.min.js" integrity="sha384-mll67QQFJfxn0IYznZYonOWZ644AWYC+Pt2cHqMaRhXVrursRwvLnLaebdGIlYNa" crossorigin="anonymous"></script>
<script>
	document.addEventListener("DOMContentLoaded", function() {
		renderMathInElement(document.body, {
			delimiters: [
			  {left: "$$", right: "$$", display: true},
			  {left: "$", right: "$", display: false},
			  {left: "\\(", right: "\\)", display: false},
			  {left: "\\[", right: "\\]", display: true}
			], trust: true,
		});
	});
</script>
~~~

Just place this in the head in the `_layouts/default.html` file and math will automatically render on all your pages.

