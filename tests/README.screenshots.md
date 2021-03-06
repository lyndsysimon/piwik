# Screenshots UI tests

Piwik contains UI tests that work by taking a screenshot of a URL and comparing it with
an expected screenshot. If the screenshots do not match, there is a bug somewhere. 

## Requirements 
These tests are in another repository but are included in Piwik as a submodule. To get the tests, run the following commands:

    $ git submodule init
    $ git submodule update

In order to run UI tests, you need to have [phantomjs](http://phantomjs.org) version 1.9.0 or greater
installed on your machine. You can download phantomjs [here](http://phantomjs.org/download.html). phantomjs is headless, so even if you're on a server without the X window system, you can still run the
UI tests.

On Ubuntu:

    $ sudo apt-get install ttf-mscorefonts-installer imagemagick imagemagick-doc

To generate screenshots identical to those generated by Travis, we install some extra fonts. 

Imagick is used to generate the "difference" screenshots which show which pixels have changed.

Removing this font may be useful if your generated screenshots' fonts do not match the expected screenshots:

    $ sudo apt-get remove ttf-bitstream-vera

## Running Tests

You can test the UI by running:

    $ cd PHPUnit
    $ phpunit --group UI

## Learn more 

Check out this blog post to learn more about Screenshot Tests in Piwik:
[QA Screenshot Testing blog post](http://piwik.org/blog/2013/10/our-latest-improvement-to-qa-screenshot-testing/)
