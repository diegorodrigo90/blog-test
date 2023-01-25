---
title: "How to create static blog whit Hugo"
date: 2022-03-02T15:19:49-03:00
tags: ["blog", "hugo", "golang", "framework", "performance"]
author: "Diego Rodrigo"
draft: false
series: ['hugo framework']
slug: "how-to-create-static-blog-whit-hugo"
cover:
    image: "images/cover.png" # image path/url
    alt: "Hugo Framework" # alt text
---

For those who work with IT, it is very interesting to have a blog, in a way it is a documentation of their learning, it gives strength to the curriculum and also helps the community.

### What is a static blog?

I've used Wordpress a lot and the performance is never that good and not to mention that you need a database and a web server with PHP support, too much for a simple blog, don't you think?

A static blog doesn't need any of that, it generates the HTML, CSS and Javascript files and that's all it needs to work, which makes the site incredibly fast.

Never before with Wordpress did my blog get this result:

<figure>
<img src="images/pagespeed.png" alt="Pagespeed" style="width:100 %" />
<figcaption align="center"><b>Performance testing with static blog</b></figcaption>
</figure>

### What is Hugo?

Hugo is a static HTML and CSS website generator written in Go. It is fast and easy to use, it takes files in a directory and convert them into a complete HTML website.

### Creating the blog

Before we start it is necessary to install Hugo, it is a simple process but as it will vary according to the operating system you use,
<a href="https://gohugo.io/getting-started/installing" target="_blank">follow the instructions here to install</a>.

With Hugo installed we can create the blog with the command:

```bash
hugo new site blog
```

Hugo will create a **blog** folder in the directory with the files for the site, but we still need to choose a theme.

You can choose any theme <a href="https://themes.gohugo.io/" target="_blank">here</a>, in this tutorial I will use <a href="https://themes.gohugo .io/themes/etch/" target="_blank">Etch</a>.

To do this, run the commands:

```bash
cd blog
git init
git submodule add https://github.com/LukasJoswiak/etch.git themes/etch
```

Go back to the project root folder and `config.toml` file and add the following line:

```toml
theme = "etch"
```

Now you can run the server in development mode with the command:

```bash
hugo server -D
```

### Creating your first article

A blog is nothing without a post and to create your first post just run the command:

```bash
hugo new posts/hello-world.md
```

This creates the file in `content/posts/hello-world.md` with the following content:

```md
---
title: "Hello World"
date: 2022-03-02T17:17:22-03:00
draft: true
---
```

Hugo uses `.md` files that use <a href="https://www.markdownguide.org/getting-started/" target="_blank">markdown</a> for their content, just edit and change the `draft` option to `false`, you can also add the author and tags and that's it, post published.

```md
---
title: "Hello world!"
date: 2022-03-02T17:17:22-03:00
draft: false
author: "Diego Rodrigo"
tags: ["tech", "golang"]
---

Post content.
```

See how easy it is, now just host your blog on a platform like <a href="https://www.netlify.com/" target="_blank">Netfly</a> or <a href="https ://aws.amazon.com/en/amplify/" target="_blank">AWS Amplify</a> and be happy😁.
