
![chefconf_logo](images/chefconf_logo.png)
# HTML5 Slide Template

This was created from the HTML5 slide template for Google I/O 2012. The original
project can be found [here](https://code.google.com/p/io-2012-slides/).

## Using this template

The easiest way to leverage this template is to fork the project and create a
branch for your talk:

    $ git checkout -b Eat-the-Whole-Bowl

If you leave your copy of the master branch untouched you should be able to
pull in improvements/tweaks from this repo as they come available.

## Configuring the slides

Much of the deck is customized by changing the settings in [`slide_config.js`](slide_config.js).
Some of the customizations include the title, Analytics tracking ID, speaker
information (name, social urls, blog), web fonts to load, themes, and other
general behavior.

### Customizing the `#ChefConf` hash

The bottom of the slides include `#ChefConf` by default. If you'd like to change
this, please update the variable `$social-tags: '#ChefConf';` in
[`/theme/scss/default.scss`](theme/scss/default.scss).

See the next section on "Editing CSS" before you go editing things.

## Authoring the slides

You can write your slides in HTML or Markdown.

### HTML

If you choose to use HTML just
edit the [template.html](template.html) file in the root of this repository.

### Markdown

Alternatively you can author your slides in Markdown and convert them to the
proper HTML using the included Python script. See
[scripts/md/README.md](scripts/md/README.md) for more details.

## Editing CSS

[Compass](http://compass-style.org/install/) is a CSS preprocessor used to compile
SCSS/SASS into CSS. We chose SCSS for the new slide deck for maintainability,
easier browser compatibility, and because...it's the future!

That said, if not comfortable working with SCSS or don't want to learn something
new, not a problem. The generated .css files can already be found in
(see [`/theme/css`](theme/css)). You can just edit those and bypass SCSS altogether.
However, our recommendation is to use Compass. It's super easy to install and use.

### Installing Compass and making changes

First, install compass:

    sudo gem update --system
    sudo gem install compass

Next, you'll want to watch for changes to the exiting .scss files in [`/theme/scss`](theme/scss)
and any new one you add:

    $ cd chefconf-slides
    $ compass watch

This command automatically recompiles the .scss file when you make a change.
Its corresponding .css file is output to [`/theme/css`](theme/css). Slick.

By default, [`config.rb`](config.rb) in the main project folder outputs minified
.css. It's a best practice after all! However, if you want unminified files,
run watch with the style output flag:

    compass watch -s expanded

*Note:* You should not need to edit [`_base.scss`](theme/scss/_base.scss).

## Running the slides

The slides can be run locally from `file://` making development easy :)

### Running from a web server

If at some point you should need a web server, use [`serve.sh`](serve.sh). It will
launch a simple one and point your default browser to [`http://localhost:8000/template.html`](http://localhost:8000/template.html):

    $ cd chefconf-slides
    $ ./serve.sh

You can also specify a custom port:

    $ ./serve.sh 8080

### Presenter mode

The slides contain a presenter mode feature (beta) to view + control the slides
from a popup window.

To enable presenter mode, add `presentme=true` to the URL: [http://localhost:8000/template.html?presentme=true](http://localhost:8000/template.html?presentme=true)

To disable presenter mode, hit [http://localhost:8000/template.html?presentme=false](http://localhost:8000/template.html?presentme=false)

Presenter mode is sticky, so refreshing the page will persist your settings.

# License and Author

| &nbsp;               |                                          |
|:---------------------|:-----------------------------------------|
| **Original Author**  | Eric Bidelman (<ebidel@gmail.com>)       |
| **Original Author**  | Luke Mahé (<lukem@google.com>)           |
| **Author**           | Seth Chisamore (<schisamo@opscode.com>)  |
| &nbsp;               |                                          |
| **Copyright**        | Copyright (c) 2012 Google                |
| **Copyright**        | Copyright (c) 2013 Opscode, Inc.         |

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
