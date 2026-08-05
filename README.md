# Fork Awesome

_A fork of the iconic font and CSS toolkit, Font Awesome_

[![npm-badge]][npm-link] [![all-contrib]](CONTRIBUTORS.md) [![jsdeliver-badge]][jsdeliver-link] [![cdnjs-badge]][cdnjs-link] [![build-status-badge]][build-status-link] [![matrix-badge]][matrix-link]

**Fork Fork Awesome is a suite of 796 pictographic and brand icons for easy, scalable vector graphics on websites and beyond.**

This project is as a reactivated fork of [Fork Awesome](https://github.com/ForkAwesome/Fork-Awesome). Which is a fork of [Font Awesome](https://fontawesome.com). Font Awesome was originally created by [Dave Gandy](https://twitter.com/davegandy) and ran as a community project. However, as Font Awesome developed, pull requests from the community stopped being accepted (October 2016) and as of version 5.0 [the build system became private](https://github.com/FortAwesome/Font-Awesome/issues/12199#issuecomment-362919956) (February 2018).

With gratitude to Dave Gandy and the Font Awesome team, [Julien Deswaef](https://merveilles.town/@xuv) forked Font Awesome 4.7 into [Fork Awesome 1.0](https://github.com/ForkAwesome/Fork-Awesome/releases/tag/1.0.0) in February 2018, to continue building the amazing resource in a fully free, libre and open-source fashion, with and for the wider community. After a period of extended inactivity (i.e. no release since February 2019), several Fork Awesome users [got](https://github.com/ForkAwesome/Fork-Awesome/issues/292) [together](https://github.com/ForkAwesome/Fork-Awesome/issues/235) to try and revive the project 🌱

## License

- The Fork Fork Awesome font is licensed under the SIL OFL 1.1:
  - http://scripts.sil.org/OFL
- Fork Fork Awesome CSS, LESS, and Sass files are licensed under the MIT License:
  - https://opensource.org/licenses/mit-license.html
- The Fork Fork Awesome documentation is licensed under the CC BY 3.0 License:
  - https://creativecommons.org/licenses/by/3.0/

We take great pride in recognizing any contributions made to this project. Whether you've written a blogpost about it, fixed a typo in the documentation or submitted new icons or code patches, we will happily list you in our [contributors list](CONTRIBUTORS.md).

## Versioning

Fork Fork Awesome will be maintained under the Semantic Versioning guidelines as much as possible. Releases will be numbered
with the following format:

`<major>.<minor>.<patch>`

And constructed with the following guidelines:

- Breaking backward compatibility bumps the major (and resets the minor and patch)
- Big changes, without breaking backward compatibility, bumps the minor (and resets the patch)
- Bug fixes, small adaptations, adding a few icons and misc changes bumps the patch
- The fork started from FontAwesome 4.7 (last commit by Dave is [bdfa9823](https://github.com/ForkAwesome/Fork-Awesome/commits/master?after=b0bc8f6fb74e05c987ef7ce1525cd3ab8390a1c3+69)).
- The project starts at version 1.0.0. All references to versions before the fork are named 0.4.7

For more information on SemVer, please visit http://semver.org.

## Building Fork Fork Awesome

**Before you can build the project**, you must first have the following installed:

- [Ruby](https://www.ruby-lang.org/en/)
- Ruby Development Headers
  - **Ubuntu:** `sudo apt-get install ruby-dev` _(Only if you're **NOT** using `rbenv` or `rvm`)_
  - **Windows:** [DevKit](http://rubyinstaller.org/)
  - **macOS:** no extra step required
- [Bundler](http://bundler.io/) (Run `gem install bundler` to install).
- [Node Package Manager (aka. `npm`)](https://docs.npmjs.com/getting-started/installing-node)
- Tools required to build the font:
  - **Ubuntu:** `sudo apt-get install fontforge woff-tools woff2`

From the root of the repository, install the tools used to develop.

    $ bundle install
    $ npm ci

Build the font:

    $ make -C src/icons

Build the web documentation:

    $ npm run build

Or serve it on a local server on http://localhost:7998:

    $ npm run dev

### Build the font in a Docker container

Another possibility is to build the font using the Dockerfile provided.

First, build the Docker image:

    $ docker build -t fa-builder .

Then, run the Docker container:

    $ docker run --rm -it \
        -u $(id -u):$(id -g) \
        -v $(pwd):/workspace \
        -p 7998:7998 \
        fa-builder

Within the container, build the font:

    $ npm ci
    $ make -C src/icons

Build the web documentation and serve it on a local server on http://localhost:7998:

    $ npm run dev
