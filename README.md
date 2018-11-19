# Blog as a (free!) service

This project builds a simple deployable static blog to a
directory (/dist).

It uses SEO-friendly client-side hash routing, and
as such can be hosted on Github Pages for free.

You might, for instance, use Husky to run a script that
runs build.js, copy the contents of dist to a Github Pages
repo and pushes.

It:

- is lightweight and very fast to load
- is mobile first
- uses relatively basic concepts were possible, so it's easily hackable
- includes a simple client-side search
- uses your installed version of graphicsmagick to automagically compress
  images and then generates srcsets to let the browser load the best one
- interlaced jpegs to allow nicer gradual image loading
- completely free to use, tweak and host

It is setup to preload a variable font (Inter UI) so supported browsers
load even faster.

I have included some of my posts in the /src directory as an
example of how it works.

You can exclude a post from being published or included by
using the special comment `post-inactive`.

```
<!-- post-inactive -->
```

Indeed, the blog uses these comments to encode extra data that
might be useful to the client or build process, which is valid a HTML,
and therefore Markdown, comment:

```
<!-- post-title: A quick analysis of popular app names by first letter -->
<!-- post-timestamp: 1540864068232 -->
```

It *should* support everything back to IE11 well, and shouldn't break on many
non-ancient browsers beyond that.

It also builds a posts/index.json so you kind of get a free JSON API showing
all of your posts - kinda cool.

The build script expects that:

- you have installed dependencies, `npm install` / `yarn`
- you are using a recent version of node that supports
  async/await and destructuring
- you have graphicsmagick installed (it's a nicer imagemagick imo)
- you have added the images that you are referencing in the markdown source
  to the images directory
- that you don't mind images being converted to jpgs (no alpha detection or
  anything like that, but you can easily add it)

This project uses the "do wtf you want" licence, here: http://www.wtfpl.net/.
