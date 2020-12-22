# Github Pages NonTheme Template
This is a template for a "themeless" Github Pages repo. Use this if you just want Github to render your markdown into html without *any* frills, but want to provide your own css styling.

---

## The Problem

Github Pages automatically renders markdown files into webpages using Jekyll. By default, it uses the [Primer theme](https://github.com/pages-themes/primer), which looks something like this: 

![A screenshot showing how the default "Primer" theme looks when applied to this repo's index page.](primer-screenshot.png)


Not bad, but what if you want something even simpler? Even something as minimal as the Primer theme has some fluff that can be trimmed:
- There's a fair bit of styling built in. About 75 kb worth.
- Every page has a header linking back to the homepage.
- If your pages repo has certain licenses, then every page has a footer linking to the repo on github.

These are all sensible features that you probably want most of the time. But again, what if you don't want?

## The solution

One option is to follow Primer's instructions to modify the layout and add your own supplmental styling.

That's essentially what I've done here, just with the goal of completely stripping everything out.

## Using this repo as a site starter:
1. Create a new repo using this one as the template.
2. Go to the settings of your new repo, and scroll down to the Github Pages section, and set the source to Branch:main
3. Edit or replace the css file in PLACEHOLDER


