---
title: Running to Stand Still
layout: post
---

## Jekyll Overview

For a project I'm working on, I've been investigating Ruby-based static site generators. There are certainly no shortage of tools that meet this criteria (e.g., [Bonsai](http://tinytree.info/), [Webby](http://webby.rubyforge.org/), [Nanoc](http://nanoc.stoneship.org/) to name but a few), but the one that immediately drew my attention was [Jekyll](http://jekyllrb.com/). Jekyll is notable for a number of reasons:

1. It was written by [Tom Preston-Werner](http://tom.preston-werner.com/), cofounder of [Github](http://github.com). Github is so magical, anything that guy puts his name on is definitely worth a gander.
2. It's the default templating engine behind [Github Pages](http://pages.github.com/), which provides anyone with a Github account a pretty straightforward place to host a basic website. You just need to commit your pages to specially-named github project, and GP automatically processes it using Jekyll into a full-blown website.
3. It has built-in support for blogging. While you can define any pages you want, specially-named files in the `_posts` directory will be treated as blog entries, and given special status in the generator (e.g., for things like latest posts, RSS feeds, etc).

## Limitations

I haven't done a deep dive on all the Ruby static site generators, but Jekyll appears to be unique in one regard: its content is expected to be generated in a hosted environment, namely Github itself. Whereas many of the other generators give you the full power of Ruby and various rich templating languages like Haml or ERB, Jekyll limits markup to HTML, Markdown, or Textile, and all templating is done through the relatively restrictive Liquid library. By doing so, Github can safely use Jekyll on anyone's uploaded content without fear of it taking down the whole site.

There seem to be no limit to the number of Jekyll forks that attempt to extend its functionality to include more dynamic templating and deeper access to Ruby, but unless you really like Jekyll's approach to blog organization, there seem to be better site generators that offer similar levels of control. Jekyll's appeal is its simplicity, focus, and limited scope.

Given these constraints, I believe there are better alternatives to Jekyll if you're looking for a general-purpose static site generator. As a framework for creating a GitHub-hosted personal blog, it's a pretty great tool for the job.

## Surprises

It's pretty bare-bones. It doesn't offer much help or guidance (e.g., default themes or templates) for getting your initial site up-and-running. Jekyll is a blank canvas and some pretty interesting brushes, but not much else. Thankfully, there are tools like Dr. Nic's [jekyll_generator](http://drnic.github.com/jekyll_generator/) that can help get a new Jekyll site up-and-running quickly.

Its page metadata is tightly-coupled to the file. Like many other site generators, Jekyll allows pages to be configured with a set of metadata for things like title, URL structure, and the like. Unfortunatley, Jekyll looks for this metadata in a special block of YAML at the beginning of the file. This means that a Jekyll Markdown file isn't purely a markdown file, but rather Markdown plus some YAML. This can make the file a little harder to work with in your favorite editor, as syntax-highlighting, page previews, and other syntax-aware functionality will undoubtedly be thrown off by this foreign preamble. I would've preferred the option of having this metadata stored in a separate file.

It has meager TextMate support. Given Jekyll's contraints around page metadata and post names, I would've thought there'd be a bundle with various useful commands for defining a YAML block or creating a new post with the current date. Guess I get to figure out how to write that myself.