---
title: How to keep compatible from 1.0.0
author: SiCo
layout: post
category: guide
comments: true
---

##### Example
- Code update everytime
- Somebody import a package and call a function
- You change function income type or amount , or returns 
- Compile error 
<!-- more -->
- Maybe developers like you package and import to there project
- Also cannot compile, CI failed.
- You make them difficult to fixed , so nobody use you package.
- Damage recycle.

##### Deal
- A function that shoule not export, just change it . 
- Only can create rpc service when you want to change *.proto files, Or you can make a new folder to use you new feature. Don't modify and delete any of them .
- Function can export, and maybe import by another project , cannot change params and returns. Just open a new function to do it, and must tag a depreciated on the old functions, so developers have more time to migrate to new function .
- Http handle func cannot change when there is a frontend has implement the API . Create new route map with handle func .

#### Recommend
- keep all http response have the similar structs .
- Content-Type: application/json , like
{% highlight json %}
{
  "code": 1001,
  "response": "[Hellium] Authorization failed"
}
{% endhighlight %}
- Or
{% highlight json %}
{
  "code": 0,
  "response": {
    "id": "abc90876543def21",
    "key": "12cdb0987654a3fe"
  }
}
{% endhighlight %}
