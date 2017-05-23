---
layout: post
title: Lessons learned while learning Phoenix and Semantic-UI
description: "Programming. The struggle is real."
categories: [phoenix, programming]
tags: [research, conference]
published: true
---

## Many to many relationships

Also how could I do something like the following?

``` elixir
book = Book
|> Repo.get!(id)
|> Repo.preload(:book_creators, {:creator, [:book_creators]})
```
I want to have book preload ​*book_creators*​, but ​*book_creators*​ have preloaded ​*creator*​.

For anyone interesting this is how.

``` elixir
book = Book
|> Repo.get!(id)
|> Repo.preload([:book_creators, {:creator, [:book_creators]}])
```
Almost exactly the same, just needed to make it an array.

## Images disappearing
Make sure you know what problem you are solving. I lost a couple of hours trying to figure out how to not make an image update when what was really happening was that the uuid field was changing and essential losing the path to the image.

## Semantic-UI

Had to explicitly bind the semantic-ui functions to jquery. Discovered that jQuery is imported via plugins in webpack.

``` javascript
$.fn.api = require('semantic-ui-api');
$.fn.transition = require('semantic-ui-transition');
$.fn.dropdown = require('../../../vendor/semantic-ui/definitions/modules/dropdown');
$.fn.search = require('semantic-ui-search');
```

## Live Reload not working

``` bash
$ mix deps.clean phoenix_live_reload
$ mix deps.update phoenix_live_reload
$ mix deps.get
$ mix compile
```

## Trying to get parameter options to have sliders

``` javascript
this.forceUpdate();
```

``` javascript
config = {
  setPluginParamOptionWeight: _.debounce((plugin, param, index, weight) => {
    dispatch(Actions.setPluginParamOptionWeight(plugin, param, index, weight))
  }, 10)
}
```


## Trying to catch prevState and nextState to clear the form

``` javascript
componentWillUpdate(prevProps) {
  const { status, clear } = this.props;
  console.log('here');
  if(prevProps.status.submitting && status.success) {
    clear();
  }
}
```

## Deploying

Best tutorials I found was this one:
<http://nhu313.github.io/phoenix,%20deploy/2016/02/16/deploy-to-digitalocean-with-dokku.html>
<https://gist.github.com/dommmel/f79d4d648517ef015682>

You really do need at least a 1GB mem or else idna won't compile.


## Ternary Operator

Remember the commas!
perms = if(user.id < 6, do: %{ admin: [:all]}, else: %{})


## Changeset errors and string interpolation

<https://github.com/elixir-lang/ecto/pull/921>
translate_error
<https://pragprog.com/titles/phoenix/errata?utf8=%E2%9C%93&what_to_show=2041>


## Changing Dokku Hostname

<http://stackoverflow.duapp.com/a/22317907/1560827>

## How to redirec to an external URL

redirect(external: "https://bookroo.cratejoy.com/ac/" <> coupon)

## Cloudflare no websockets
<https://github.com/dokku/dokku-letsencrypt/issues/28>


## How to send html emails

``` elixir
def send_forgotten_password_email(user) do
    send_email to: "keslert@gmail.com",
               from: @from,
               subject: "Bookroo password change request",
               html: Phoenix.View.render_to_string(Bookroo.EmailView, "password_recovery_token.html", user: user)
  end
```

Also, don't get fooled by your own messages! I wasn't using an email in the system,
so the email was never going out....

## Monitoring

<https://medium.com/@mschae/measuring-your-phoenix-app-d63a77b13bda#.x6vojqphu>

Updated tutorial!
<https://alexgaribay.com/2016/02/27/using-elixometer-with-phoenix/>

## It really did take 48 hours for DNS propagation

## Don't use ES6 where it's not available
Maybe there's an even better way to have page specific javascript...

``` javascript
$(function() {
  $('#sidebar-toggle').click(() => {
    $('.ui.sidebar').sidebar('toggle');
  });
})
```

## Vex Dialog is beautiful, but such a pain to get setup!
I ended up using a hack to piece to two parts together. I'm sure a webpack expert could help me figure out the proper way to do this.

``` javascript
vex.dialog = vexDialog;
vex.defaultOptions.className = 'vex-theme-default';
```

## Composable queries
<https://blog.drewolson.org/composable-queries-ecto/>


## pagination
<https://blog.drewolson.org/pagination-with-phoenix-ecto/>
<https://github.com/drewolson/scrivener>


## Ecto.Query.preload is not the same as Repo.preload
The first works on a query, the second works on a model. This was an issue because in example
code people were using preload by itself without showing which module it was coming from.
<http://stackoverflow.com/questions/33815418/preloading-associations-and-paginating>


## overflow-y: scroll vs overflow-y: auto

Most likely you want auto.

## cross Origin

getImageData() error The canvas has been tainted by cross-origin data
<img className="hidden-image" src={imageUrl} ref="hiddenImage" crossOrigin="anonymous" />
<http://stackoverflow.com/questions/26747353/console-log-uncaught-securityerror-failed-to-execute-getimagedata-on-canvas>


## undefined function :ok.id/1 (module :ok is not available)

Insert returns a tuple {:ok, model}

<http://www.glydergun.com/diving-into-ecto/>
