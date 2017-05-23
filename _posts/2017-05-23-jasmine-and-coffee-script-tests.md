---
layout: base
title:  "Jasmine and Coffee-Script tests"
date:   2017-05-23
tags: [jasmine, coffee-script, tdd]
---
Install `jasmine` and `coffee-script`:

{% highlight sh %}
npm install jasmine coffee-script --save-dev
{% endhighlight %}

Initialize `jasmine`:

{% highlight sh %}
./node_modules/.bin/jasmine init
{% endhighlight %}

Instruct `jasmine` to use `coffee-script` files. Edit `spec/support/jasmine.json` `spec_files` config option:

{% highlight json %}
  …
  "spec_files": ["**/*[sS]pec.coffee"],
  …
{% endhighlight %}

Add `test` script to `package.json`:

{% highlight json %}
  …
  "scripts": {
    …
    "test": "node --require coffee-script/register ./node_modules/.bin/jasmine",
    …
  },
  …
{% endhighlight %}
