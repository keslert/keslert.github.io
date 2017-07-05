---
layout: post
title: Pushing a Create React App to Github Pages
categories: [tutorial]
published: true
---

Add the following to **package.json**.

``` json
{
  "homepage": "https://github.com/keslert/app-name",
  "scripts": {
    "deploy" : "react-scripts build && gh-pages -d build"    
  }
}
```

Comment out the following line in **.gitignore**.
``` 
# build/
```

Push your build folder to github.

``` bash
$ yarn add --dev gh-pages
$ yarn build
$ git add build
$ git commit -m "Initial commit to add build folder for gh-pages"
$ git push origin master
```

Deploy build to gh-pages. All future deployments can start with this final step.

``` bash
$ yarn deploy
```