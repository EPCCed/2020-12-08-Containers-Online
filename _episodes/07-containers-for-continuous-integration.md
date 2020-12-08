---
title: "Containers used in generating this lesson"
teaching: 20
exercises: 0
questions:
- "How can containers be useful to me for building websites?"
objectives:
- "Demonstrate how to construct a website using containers to transform a specification into a fully-presented website."
keypoints:
- "The generation of this lesson website can be effected using a container."
---
The website for this lesson is generated mechanically, based on a set of files that specify the configuration of the site, its presentation template, and the content to go on this page. This is far more manageable than editing each webpage of the lesson separately, for example, if the page header needs to change, this change can be made in one place, and all the pages regenerated. The alternative would be needing to edit each page to repeat the change: this is not productive or suitable work for humans to do!

In your shell window, move to your `docker-intro` directory. We will be expanding a ZIP file into this directory later.

Now open a web browser window and:
1. Navigate to the GitHub repository that contains the files for this session, at <https://github.com/carpentries-incubator/docker-introduction/>;
2. Click the green "Clone or download" button on the right-hand side of the page;
3. Click "Download ZIP".
4. The downloaded ZIP file should contain one directory named `docker-introduction-gh-pages`.
5. Move the `docker-introduction-gh-pages` folder into the `docker-intro` folder.

> ## There are many ways to work with ZIP files
> Note that the last two steps can be achieved using a Mac or Windows graphical user interface. There are also ways to effect expanding the ZIP archive on the command line, for example, on my Mac I can achieve the effect of those last two steps through running the command `unzip ~/Downloads/docker-introduction-gh-pages.zip`.
{: .callout}

In your shell window, if you `cd` into the `docker-introduction-gh-pages` folder and list the files, you should see something similar to what I see:
~~~
$ cd docker-introduction-gh-pages
$ ls
~~~
{: .language-bash}
~~~
AUTHORS			_episodes		code
CITATION		_episodes_rmd		data
CODE_OF_CONDUCT.md	_extras			fig
CONTRIBUTING.md		_includes		files
LICENSE.md		_layouts		index.md
Makefile		aio.md			reference.md
README.md		assets			setup.md
_config.yml		bin
~~~
{: .output}

You can now request that a container is created that will compile the files in this set into the lesson website, and will run a simple webserver to allow you to view your version of the website locally. Note that this command will be long and fiddly to type, so you probably want to copy-and-paste it into your shell window. This command will continue to (re-)generate and serve up your version of the lesson website, so you will not get your shell prompt back until you type <kbd>control</kbd>+<kbd>c</kbd>. This will stop the webserver, since it cleans away the container.

For macOS, Linux and PowerShell:
~~~
$ docker run --rm -it -v ${PWD}:/srv/jekyll -p 127.0.0.1:4000:4000 jekyll/jekyll:latest jekyll serve
~~~
{: .language-bash}

When I ran the macOS command, the output was as follows:
~~~
Unable to find image 'jekyll/jekyll:latest' locally
latest: Pulling from jekyll/jekyll
cbdbe7a5bc2a: Pull complete 
aa8ae8202b42: Pull complete 
b21786fe7c0d: Pull complete 
68296e6645b2: Pull complete 
6b1c37303e2d: Pull complete 
0fb11dc849c1: Pull complete 
Digest: sha256:bb45414c3fefa80a75c5001f30baf1dff48ae31dc961b8b51003b93b60675334
Status: Downloaded newer image for jekyll/jekyll:latest

jekyll serve
Fetching gem metadata from https://rubygems.org/...........
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies.....
Using concurrent-ruby 1.1.7
Using i18n 0.9.5
Fetching minitest 5.14.2
Installing minitest 5.14.2
Using thread_safe 0.3.6
Fetching tzinfo 1.2.8
Installing tzinfo 1.2.8
Fetching zeitwerk 2.4.2
Installing zeitwerk 2.4.2
Fetching activesupport 6.0.3.4
Installing activesupport 6.0.3.4
Fetching public_suffix 3.1.1
Installing public_suffix 3.1.1
Using addressable 2.7.0
Using bundler 2.1.4
Fetching coffee-script-source 1.11.1
Installing coffee-script-source 1.11.1
Using execjs 2.7.0
Using coffee-script 2.4.1
Using colorator 1.1.0
Using ruby-enum 0.8.0
Fetching commonmarker 0.17.13
Installing commonmarker 0.17.13 with native extensions
Fetching unf_ext 0.0.7.7
Installing unf_ext 0.0.7.7 with native extensions
Fetching unf 0.1.4
Installing unf 0.1.4
Fetching simpleidn 0.1.1
Installing simpleidn 0.1.1
Fetching dnsruby 1.61.5
Installing dnsruby 1.61.5
Using eventmachine 1.2.7
Using http_parser.rb 0.6.0
Fetching em-websocket 0.5.2
Installing em-websocket 0.5.2
Using ffi 1.13.1
Using ethon 0.12.0
Fetching multipart-post 2.1.1
Installing multipart-post 2.1.1
Fetching ruby2_keywords 0.0.2
Installing ruby2_keywords 0.0.2
Fetching faraday 1.1.0
Installing faraday 1.1.0
Using forwardable-extended 2.6.0
Using gemoji 3.0.1
Fetching sawyer 0.8.2
Installing sawyer 0.8.2
Fetching octokit 4.19.0
Installing octokit 4.19.0
Using typhoeus 1.4.0
Fetching github-pages-health-check 1.16.1
Installing github-pages-health-check 1.16.1
Using rb-fsevent 0.10.4
Using rb-inotify 0.10.1
Using sass-listen 4.0.0
Using sass 3.7.4
Using jekyll-sass-converter 1.5.2
Fetching listen 3.3.3
Installing listen 3.3.3
Using jekyll-watch 2.2.1
Fetching rexml 3.2.4
Installing rexml 3.2.4
Using kramdown 2.3.0
Using liquid 4.0.3
Using mercenary 0.3.6
Using pathutil 0.16.2
Fetching rouge 3.23.0
Installing rouge 3.23.0
Using safe_yaml 1.0.5
Using jekyll 3.9.0
Fetching jekyll-avatar 0.7.0
Installing jekyll-avatar 0.7.0
Fetching jekyll-coffeescript 1.1.1
Installing jekyll-coffeescript 1.1.1
Using jekyll-commonmark 1.3.1
Fetching jekyll-commonmark-ghpages 0.1.6
Installing jekyll-commonmark-ghpages 0.1.6
Fetching jekyll-default-layout 0.1.4
Installing jekyll-default-layout 0.1.4
Fetching jekyll-feed 0.15.1
Installing jekyll-feed 0.15.1
Fetching jekyll-gist 1.5.0
Installing jekyll-gist 1.5.0
Fetching jekyll-github-metadata 2.13.0
Installing jekyll-github-metadata 2.13.0
Using mini_portile2 2.4.0
Using nokogiri 1.10.10
Using html-pipeline 2.14.0
Using jekyll-mentions 1.6.0
Fetching jekyll-optional-front-matter 0.3.2
Installing jekyll-optional-front-matter 0.3.2
Using jekyll-paginate 1.1.0
Fetching jekyll-readme-index 0.3.0
Installing jekyll-readme-index 0.3.0
Using jekyll-redirect-from 0.16.0
Fetching jekyll-relative-links 0.6.1
Installing jekyll-relative-links 0.6.1
Fetching rubyzip 2.3.0
Installing rubyzip 2.3.0
Fetching jekyll-remote-theme 0.4.2
Installing jekyll-remote-theme 0.4.2
Using jekyll-seo-tag 2.6.1
Using jekyll-sitemap 1.4.0
Fetching jekyll-swiss 1.0.0
Installing jekyll-swiss 1.0.0
Fetching jekyll-theme-architect 0.1.1
Installing jekyll-theme-architect 0.1.1
Fetching jekyll-theme-cayman 0.1.1
Installing jekyll-theme-cayman 0.1.1
Fetching jekyll-theme-dinky 0.1.1
Installing jekyll-theme-dinky 0.1.1
Fetching jekyll-theme-hacker 0.1.2
Installing jekyll-theme-hacker 0.1.2
Fetching jekyll-theme-leap-day 0.1.1
Installing jekyll-theme-leap-day 0.1.1
Fetching jekyll-theme-merlot 0.1.1
Installing jekyll-theme-merlot 0.1.1
Fetching jekyll-theme-midnight 0.1.1
Installing jekyll-theme-midnight 0.1.1
Fetching jekyll-theme-minimal 0.1.1
Installing jekyll-theme-minimal 0.1.1
Fetching jekyll-theme-modernist 0.1.1
Installing jekyll-theme-modernist 0.1.1
Fetching jekyll-theme-primer 0.5.4
Installing jekyll-theme-primer 0.5.4
Fetching jekyll-theme-slate 0.1.1
Installing jekyll-theme-slate 0.1.1
Fetching jekyll-theme-tactile 0.1.1
Installing jekyll-theme-tactile 0.1.1
Fetching jekyll-theme-time-machine 0.1.1
Installing jekyll-theme-time-machine 0.1.1
Fetching jekyll-titles-from-headings 0.5.3
Installing jekyll-titles-from-headings 0.5.3
Using jemoji 0.12.0
Using kramdown-parser-gfm 1.1.0
Using minima 2.5.1
Using unicode-display_width 1.7.0
Using terminal-table 1.8.0
Fetching github-pages 209
Installing github-pages 209
Bundle complete! 1 Gemfile dependency, 91 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
ruby 2.7.1p83 (2020-03-31 revision a0c7c23c9c) [x86_64-linux-musl]
Configuration file: /srv/jekyll/_config.yml
            Source: /srv/jekyll
       Destination: /srv/jekyll/_site
 Incremental build: disabled. Enable with --incremental
      Generating... 
      Remote Theme: Using theme carpentries/carpentries-theme
                    done in 7.46 seconds.
 Auto-regeneration: enabled for '/srv/jekyll'
    Server address: http://0.0.0.0:4000
  Server running... press ctrl-c to stop
~~~
{: .output}

In the preceding output, you see Docker downloading the image for Jekyll, which is a tool for building websites from specification files such as those used for this lesson. The line `jekyll serve` indicates a command that runs within the Docker container instance. The output below that is from the Jekyll tool itself, highlighting that the website has been built, and indicating that there is a server running.

Open a web browser window and visit the address <http://localhost:4000/>. You should see a site that looks very similar to that at <https://carpentries-incubator.github.io/docker-introduction/>.

Using a new shell window, or using your laptop's GUI, locate the file `index.md` within the `docker-introduction-gh-pages` directory, and open it in your preferred editor program.

Near the top of this file you should see the description starting "This session aims to introduce the use of Docker containers with the goal of using them to effect reproducible computational environments." Make a change to this message, and save the file.

If you reload your web browser, the change that you just made should be visible. This is because the Jekyll container saw that you changed the `index.md` file, and regenerated the website.

You can stop the Jekyll container by clicking in its terminal window and typing <kbd>control</kbd>+<kbd>c</kbd>.

You have now achieved using a reproducible computational environment to reproduce a lesson about reproducible computing environments.

{% include links.md %}

{% comment %}
<!--  LocalWords:  keypoints _episodes_rmd CODE_OF_CONDUCT.md aio.md
 -->
<!--  LocalWords:  CONTRIBUTING.md LICENSE.md index.md reference.md
 -->
<!--  LocalWords:  README.md setup.md _config.yml webserver srv
 -->
<!--  LocalWords:  jekyll x86_64-linux-musl favicons github.io
 -->
<!--  LocalWords:  links.md _episodes_rmd _config.yml endcomment
 -->
{% endcomment %}
