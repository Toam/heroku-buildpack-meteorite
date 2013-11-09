# Heroku buildpack: Meteorite

This build pack allows you to easily deploy meteor apps to heroku using [meteorite](http://github.com/oortcloud/meteorite). It's easy to use different branches of meteor and any smart package you can lay your hands on.
This buildpack is based on [https://github.com/oortcloud/heroku-buildpack-meteorite](https://github.com/oortcloud/heroku-buildpack-meteorite) but uses MongoLab instead of MongoHQ (MongoHQ is not yet available in europe on Heroku).

## Usage

```bash
heroku create --stack cedar --buildpack https://github.com/toam/heroku-buildpack-meteorite.git
```

Then `git push` to heroku as usual.

## NOTES

You need to set the `ROOT_URL` environment variable:

```bash
heroku config:add ROOT_URL=your.domain.com
```

You can specify meteor settings by setting the `METEOR_SETTINGS` environment variable:

```bash
heroku config:add METEOR_SETTINGS='{"herp":"derp"}'
```


You need to have a verified account so the buildpack can add a `mongolab:sandbox` addon.
