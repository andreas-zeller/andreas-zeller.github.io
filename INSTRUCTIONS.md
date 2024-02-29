# My website

This is a website based on Andreas Zeller's website.

## Software requirements

You may need the following softwares:
- Ruby
- RubyGems
- Make (__optional__)

### How to install?

Run the following commands:

```bash
$ sudo apt-get install ruby-full build-essential zlib1g-dev
$ echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
$ echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
$ source ~/.bashrc
$ gem install jekyll bundler
Fetching gem metadata from https://rubygems.org/.............
Resolving dependencies...
Fetching rake 13.1.0
Installing rake 13.1.0
Fetching rexml 3.2.6
Fetching webrick 1.8.1
Installing rexml 3.2.6
Installing webrick 1.8.1
Fetching jekyll-optional-front-matter 0.3.2
Fetching jekyll-feed 0.17.0
Fetching jekyll-redirect-from 0.16.0
Fetching jekyll-seo-tag 2.8.0
Installing jekyll-optional-front-matter 0.3.2
Installing jekyll-feed 0.17.0
Installing jekyll-redirect-from 0.16.0
Installing jekyll-seo-tag 2.8.0
Fetching jekyll-theme-minimal 0.2.0
Installing jekyll-theme-minimal 0.2.0
Bundle complete! 5 Gemfile dependencies, 36 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
```

### How to check?

Run the following commands:

```bash
$ ruby -v
ruby 3.0.2p107 (2021-07-07 revision 0db68f0233) [x86_64-linux-gnu]
$ bundle -v
Bundler version 2.5.6
```

## How to Run?

First, it requires install the required packages using `make install`. Then, run the following command to see a preview:

```bash
$ make preview
(sleep 3; open http://localhost:4000/) &
bundle exec jekyll serve --watch --trace
Configuration file: /home/samuel/Music/samuellucas97.github.io/_config.yml
            Source: /home/samuel/Music/samuellucas97.github.io
       Destination: /home/samuel/Music/samuellucas97.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating... 
       Jekyll Feed: Generating feed for posts
                    done in 1.041 seconds.
 Auto-regeneration: enabled for '/home/samuel/Music/samuellucas97.github.io'
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
/snap/core20/current/lib/x86_64-linux-gnu/libstdc++.so.6: version `GLIBCXX_3.4.29' not found (required by /lib/x86_64-linux-gnu/libproxy.so.1)
Failed to load module: /home/samuel/snap/code/common/.cache/gio-modules/libgiolibproxy.so
Opening in existing browser session
```

This will start a server, available at [http://127.0.0.1:4000](http://127.0.0.1:4000).
