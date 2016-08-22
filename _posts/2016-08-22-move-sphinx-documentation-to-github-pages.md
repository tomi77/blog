---
layout: base
title:  "Move Sphinx documentation to GitHub pages"
date:   2016-08-22
tags: [github-pages, sphinx]
---
#### Step 1

Rename `docs` folder to `docs_src`.

#### Step 2

Move `docs_src/_build` folder to `docs`.

#### Step 3

Change `build_sphinx` and `upload_sphinx` sections in `setup.cfg`:

{% highlight ini %}
[build_sphinx]
source-dir = docs_src/
build-dir  = docs

[upload_sphinx]
upload-dir = docs/html
{% endhighlight %}

#### Step 4

Add `docs/doctrees/` to `.gitignore`.

#### Step 5

Add empty `docs/.nojekyll` file.

#### Step 6

Add `docs/index.html` file:

{% highlight html %}
<!DOCTYPE html>
<html>

<head>
    <meta http-equiv="refresh" content="0; url='html/'" />
</head>

<body>
</body>

</html>
{% endhighlight %}

#### Step 7

Go to GitHub project page. Select `Settings` tab. On `GitHub Pages` section set `Source` to `master branch /docs folder`.
