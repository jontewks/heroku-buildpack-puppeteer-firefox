# heroku-buildpack-puppeteer-firefox

Installs dependencies needed in order to run puppeteer on heroku using Firefox instead of Chrome. Be sure to include

```
{
  args: ['--no-sandbox'],
  product: 'firefox'
}
```

in your call to `puppeteer.launch`.

## Usage

To use the latest stable version run:

```sh-session
$ heroku buildpacks:add jontewks/puppeteer-firefox
```

Or use the source code in this repository:

```sh-session
$ heroku buildpacks:add https://github.com/jontewks/heroku-buildpack-puppeteer-firefox.git
```

You'll also need to add an environment variable of `PUPPETEER_PRODUCT=firefox` on heroku so firefox will be installed instead of chromium.

## Issues

A common issue that people run into often is a cache issue with heroku. Often when you start seeing errors that chrome won't start and some libraries are missing, you can resolve it by clearing your heroku cache. Instructions for that can be found here: https://help.heroku.com/18PI5RSY/how-do-i-clear-the-build-cache

If you are still running into any issues with this buildpack after doing the above, please open an issue on this repo and/or submit a PR that resolves it. Different versions of chrome have different dependencies and so some issues can creep in without me knowing. Thanks!
