---
title: "How to setup the The Lazy Universe blog."
author: ["Rajes Kommu"]
date: 2023-09-05T00:00:00-07:00
lastmod: 2023-09-05T14:58:27-07:00
tags: ["blog"]
categories: ["oxhugo"]
draft: false
creator: "Emacs 29.1 (Org mode 9.6.6 + ox-hugo)"
---

<div class="ox-hugo-toc toc">

<div class="heading">Table of Contents</div>

- [Steps](#steps)
    - [Site and Module Initialization](#site-and-module-initialization)
    - [Adding the Theme module](#adding-the-theme-module)
    - [Site Configuration](#site-configuration)
    - [Content Creation](#content-creation)
    - [Test the site locally](#test-the-site-locally)

</div>
<!--endtoc-->


## Steps {#steps}

-   These steps work only for a new site! `thelazyuniverse.github.io` should not exist prior to the sequence of steps described here.


### Site and Module Initialization {#site-and-module-initialization}

-   Initialize the site as Hugo module
    ```shell
    hugo new site thelazyuniverse.github.io
    cd thelazyuniverse.github.io
    git init .
    hugo mod init thelazyuniverse.github.io
    ```


### Adding the Theme module {#adding-the-theme-module}

-   Add the theme as a Module
    ```shell
    hugo mod get gitlab.com/kaushalmodi/hugo-theme-refined
    ```


### Site Configuration {#site-configuration}

-   Edit the `hugo.toml` file
    ```toml
    [module]
      [[module.imports]]
        path = "gitlab.com/kaushalmodi/hugo-theme-refined"
    ```

-   Complete the rest of the `hugo.toml` configuration file editing


### Content Creation {#content-creation}

-   Create a `content-org` folder
-   Create the `cae-setup.org` in the `content-org` folder
-   Create the `oxhugo` folder in the `content-org` folder
    -   This folder will have all the posts related to `@oxhugo` category in one or more
        files. The first file in will be called `posts-0.org`. If and when this file
        gets too big, start the `post-1.org`, then `posts-2.org`, and so on.
-   Create the `images` folder under the `oxhugo` folder
-   Create the `posts-0.org` file
    -   Export the contents of this file
-   Create a folder (with the `images` sub-folder) for each category. Inside the category
    folder, create `org` files following the `posts-N.org` convention, with N=0 &ctdot;


### Test the site locally {#test-the-site-locally}

-   `C-c C-e H A` to export the content defined in the `posts-0.org` file.
-   Run `hugo server -D` and verify everything looks correct.
-   Change status of posts from `DRAFT` to `DONE`
-   Follow the steps listed at [Hosting on GitHub](https://gohugo.io/hosting-and-deployment/hosting-on-github/#procedure)
-   Visit [TheLazyUniverse](https://thelazyuniverse.github.io) to verify the initial post looks ok.
-   The blog is now setup!
