# Libsass Rails

**Update:** Use [sassc-rails](https://github.com/bolandrm/sassc-rails) instead which works properly!

An experiment in rails project using libsass instead of ruby sass with the asset pipeline.

Milage may vary, only works on Mac right now (due to hardcoded binary)

# Setup

    git clone git@github.com:andrew/libsass-rails.git
    cd libsass-rails
    bundle install
    rails s

# Usage

It *should* work like a regular rails app, add Sass to `application.scss` and view at `http://localhost:3000/assets/application.css`

# What's different?

The only app specific change is in the Gemfile, where we require sassc and a fork of sass-rails that uses it:

    gem 'sassc', github: 'andrew/sassruby'
    gem 'sass-rails', github: 'andrew/sass-rails'

This fork of sass-rails swaps out `Sass::Engine` for `SassC::Engine` which, in theory, have the same API.

# Limitations

Libsass does not have all the features of the latest version of ruby sass, some features may not work.
