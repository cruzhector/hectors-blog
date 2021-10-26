+++
title = "Hugo and Gh Pages"
date = "2021-03-20T12:53:18+05:30"
author = "Hector"
tags = ["hugo", "gh-pages"]
keywords = ["hugo"]
description = "How to create a blog with hugo and github pages"
showFullContent = false
+++

Let me give a brief introduction to [Hugo](https://gohugo.io/). Hugo is a framework for generating static sites meaning it will provide us with a template to create static websites.

Now let us get started with creating out first blog with hugo and host it on Github pages.

## Step-1 Download Hugo

We have to download the framework to work on templates and run them.

A beautiful documentation is provided by hugo for each machine respectievly. Download it from here https://gohugo.io/getting-started/installing/

If you want to check just type ```hugo help``` in your bash if you see the list of items then the installation was a success.

## Step-2 Create Github repositories

Now we have to create 2 github repositories.

**But why 2 repos?** One repo will have hugo template where in you write your posts(nothing but content for your blog) and the other is for hosting the hugo template with the content you wrote on a Github page.

We will name the 1st repo as blog(Of course you can name it with whatever name you want) and the 2nd repo we have to name it this way `<github-username>.github.io` example: my username is cruzhector so my repo name will be `cruzhector.github.io`. This way github will automatically create a website for you.

## Step-3 Pick a template and Start the Hugo server

There are beautiful and hassle free templates available in the hugo themes space, You can find them here https://themes.gohugo.io/

For this tutorial we will use [terminal-template](https://github.com/panr/hugo-theme-terminal)

Now clone the 1st repository we created in the step-2 open the folder and run `hugo new site .`(If you want to create site in a nested folder then instead of (.) specify folder name it will create automatically).

Next do `cd themes` and clone the [terminal-template](https://github.com/panr/hugo-theme-terminal) repo. Now come back to the root folder `cd ..` open `config.toml` file and paste this [config.toml](https://github.com/panr/hugo-theme-terminal#how-to-configure) file.

Run this command `hugo server -w` from the root folder to start the hugo server. Hugo will read the template mentioned in the config.toml file and serves it on `localhost:1313`.

## Step-4 Write a post

It is time for you to write a post. Open terminal in the root folder and run this `hugo new post/first-post.md`. This will create a .md file in the content/posts folder. Open the file and provide few details like title, description and write some content below the +++ section.

If you have stopped the hugo server then restart that. If you havent then you should see your first post in the browser.

So cool right with a minimum effort you are able to write content.

## Github page

Now let us make your content visible for others as well.

Clone the 2nd repo we create that is `<github-username>.github.io` in the same folder where you cloned your 1st repo that is blog. The structure might look this the below.

```
projects
    /blog
    /<github-username>.github.io
```

Now from blog folder run `hugo -d ../<github-username>.github.io`. This will output the content from the blog folder to the website folder. If you open the website folder you will see static files like html, css etc.. Push the files to git. Once you push the files then open this url `https://<github-username>.github.io` in my case it is `https://cruzhector.github.io/`.

Voila!! your blog. Thats it you have created you first blog with Hugo and Github pages.