# symfony-php
A PHP Docker image based on the official PHP Alpine image, and includes additional PHP extensions to run Symfony

[![Build Status](https://travis-ci.org/kariae/symfony-php.svg?branch=master)](https://travis-ci.org/kariae/symfony-php)

Please note that the image contains also [Composer](https://getcomposer.org/)

## Tags
* 8.0 [(Dockerfile)](https://github.com/kariae/symfony-php/blob/master/8.0/Dockerfile)
* 7.4 [(Dockerfile)](https://github.com/kariae/symfony-php/blob/master/7.4/Dockerfile)
* 7.2 [(Dockerfile)](https://github.com/kariae/symfony-php/blob/master/7.2/Dockerfile)
* 7.1 [(Dockerfile)](https://github.com/kariae/symfony-php/blob/master/7.1/Dockerfile)
* 7.0 [(Dockerfile)](https://github.com/kariae/symfony-php/blob/master/7.0/Dockerfile)

## Contributing
First, **many thanks** for your contributions, please note that this repository is for a PHP Docker image to run Symfony projects respecting their [requirements](http://symfony.com/doc/current/reference/requirements.html) . if you find any typo/misconfiguration, or just want to optimize more the workflow, please

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## TODO
- [x] Support other distributions and variants of PHP.
- [ ] Add environment variables to customize the image.
