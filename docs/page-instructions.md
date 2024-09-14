---
title: Set up GitHub Pages
layout: default
date: 2024-09-14
nav_order: 3
last_modified_date: 2024-09-14
---

# Set up GitHub Pages
{: .no_toc }

This page describes how I set up this GitHub Pages site with [Just the Docs]{:target="_blank"}.

Table of contents
{: .text-delta }

1. TOC
{:toc}

## Install Ruby

[Just the docs]{:target="_blank"} and [Jekyll]{:target="_blank"} require [Ruby]{:target="_blank"}.

### Install Ruby on Windows

To install Ruby on windows, follow the instructions in the [Jekyll Windows installation guide]{:target="_blank"}.

### Install Ruby on MacOS

MacOS comes with an older version of Ruby installed on it. Upgrade Ruby to a newer version with [Homebrew]{:target="_blank"}.

1. Open a new terminal window.

1. Install `ruby` with Homebrew.

    ```bash
    brew install ruby
    ```

1. Add the path to the new `ruby` version to your `.bashrc` or `.bash_profile` file.

    ```bash
    echo 'export PATH="/usr/local/opt/ruby/bin:$PATH"' >> ~/.bashrc
    ```

1. Restart your terminal or run the following code snippet:

    ```bash
    source ~/.bashrc
    ```

## Create your GitHub pages site

Follow the instructions in GitHub's article on [creating a GitHub Pages site with Jekyll]{:target="_blank"}.

## Edit your Gemfile

We add the `just-the-docs` template to our Gemfile because we're using bundler.

```ruby
gem "just-the-docs", "0.10.0"
```

## Edit your GitHub Action workflow

If you followed the example in [Create your GitHub pages site](#create-your-github-pages-site), you'll need to update your
GitHub Action workflow to use Ruby.

1. Replace the auto-generated workflow file with the [Jekyll workflow template]{:target="_blank"}.

1. Follow the [Just the Doc instructions on hosting your docs from an existing project repo]{:target="_blank"}.

## Edit your `_config.yml` file

Edit your `_config.yml` file for extra features and callout formatting.

See [this project's configuration file]{:target="_blank"}.

## Test your site locally

Your GitHub Actions workflow updates your site when you push code to your `main` branch.
You should, however, test your site locally first for immediate feedback.

### Set up Jekyll and bundler

The initial set up depends on your operating system.

#### MacOS

MacOS has ruby installed by default, but it's most likely an older, out-of-date version. Install the newest version of
Ruby with Homebrew.

1. Go to the `docs` folder in your GitHub Pages project. Install `jekyll` and `bundler`.

    ```bash
    gem install jekyll bundler
    ```

    {: .note }
    If you get a permission error, run the command with `sudo`.

1. Set your `bundle` configuration path to a local folder.

    ```bash
    bundle config --local set path vendor/bundle
    ```

1. Install the gems from your `Gemfile`.

    ```bash
    bundle install
    ```

    {: .note }
    If you get a permission error, run the command with `sudo`.

    {: .warning }
    You should only run the command with `sudo` if you are the root and only user of the machine. Ruby warns that running
    with `sudo` can mess up the configuration for non-root users.

1. Run your site locally and start writing.

    ```bash
    bundle exec jekyll serve
    ```

[Just the docs]: https://just-the-docs.com/
[Jekyll]: https://jekyllrb.com/
[Ruby]: https://www.ruby-lang.org/en/
[Jekyll Windows installation guide]: https://jekyllrb.com/docs/installation/windows/
[Homebrew]: https://brew.sh/
[creating a GitHub Pages site with Jekyll]: https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll
[Jekyll workflow template]: https://github.com/just-the-docs/just-the-docs-template/blob/main/.github/workflows/pages.yml
[Just the Doc instructions on hosting your docs from an existing project repo]: https://github.com/just-the-docs/just-the-docs-template/blob/main/README.md#hosting-your-docs-from-an-existing-project-repo
[this project's configuration file]: https://github.com/greg-martinez44/greg-martinez44.github.io/blob/main/docs/_config.yml
