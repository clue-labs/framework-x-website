# Framework X website

[![CI status](https://github.com/clue/framework-xwebsite/workflows/Deploy/badge.svg)](https://github.com/clue/framework-x-website/actions)

Source code for the Framework X website.

## Build

You can build the website like this:

```bash
$ make
```

> Note that this command will clone Framework X which is currently in early access.
  See https://github.com/clue/framework-x for more details.

Once built, you can manually browse the `build/` directory or run the development
web server like this:

```bash
$ make serve
```

Once built, you can clean up like this:

```bash
$ make clean
```

## Deploy

Once built (see previous "Build" section), you can simply deploy the `build/`
directory behind a web server of choice.

The live website is deployed by pushing the contents of the `build/` directory to
the `live` branch like this:

```bash
$ make deploy
```

## Auto-Deployment

The website can be automatically deployed via the GitHub Pages feature.

Any time a commit is merged (such as when a PR is merged), GitHub actions will
automatically build and deploy the website. This is done by running the above
deployment script (see previous chapter).

> Repository setup:
> Note that this command will clone Framework X which is currently in early access.
> We're using a read-only SSH deploy key for reading from this source repository.
> Make sure the required `DEPLOY_KEY` secret is set in the repository settings on GitHub.
> See [action documentation](https://github.com/JamesIves/github-pages-deploy-action#using-an-ssh-deploy-key-)
> for more details.