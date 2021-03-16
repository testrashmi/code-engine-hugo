# code-engine hugo

# Scope

This is a tutorial/demo of getting [hugo][mainhugo] to work with [code-engine][codeengine] 
from IBM Cloud.

# Prerequiesits

1. You need hugo installed, there's a few different installation paths, check [this][hugo] out.
1. Create a [GitHub][githubnew] repostiory that you can push your `hugo` site to.

# Steps

1. First thing you need to do is create a example hugo site, you run the following command:
**NOTE**: `code-engine-hugo` is just an example name
```bash
$ hugo new site code-engine-hugo
Congratulations! Your new Hugo site is created in /code-engine-hugo.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.
```

2. Next test your site and create a `git` repository, follow these next directions:
```bash
$ cd /code-engine-hugo
$ git init
$ git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke
$ echo theme = \"ananke\" >> config.toml
$ hugo new posts/my-first-post.md 
$ vim content/posts/my-first-post.md # just fill it with dummy text
$ hugo server -D
```
You should be able to see a site that says "My New Hugo Site". The `my-first-post.md`
has a `draft: true`, when you want to make it real change that to `false`.

3. Now when you make changes or add posts you can run `hugo` (without drafts) and the new site
will be recreated in `public/` in that directory.

4. Push your new site up to the GitHub repository, and we'll start configuring 
code engine next.

```bash
$ cd /code-engine-hugo
$ git add .
$ git commit -m "inital commit"
$ git push origin main
```




[codeengine]: 
[hugo]: https://gohugo.io/getting-started/installing/
[mainhugo]: https://gohugo.io/
[githubnew]: https://github.com/new
