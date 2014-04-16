Annyeonghaseyo!
---------------
Annyeonghaseyo is a simple ruby gem aimed at spotlighting gem dependency management with Bundler.

Development
-----------
With the cited goal, development to the gem is limited to the example of adding or removing dependencies. In this context, you would follow these steps

* update annyeonghaseyo.gemspec with the dependency changes you wish to demonstrate
* run `bundle package` to 'freeze' those new dependencies in `vendor/cache`
* commit your changes
* distribute your project for building
  * `git clone` works ok
  * `git archive` works ok

Building
--------
To build Annyeonghaseyo and its dependencies, get the code (by a git archive or a clone) and try some different techniques.

h5. `bundle install --deployment`

This method installs the gems locally to your project. They would show up in `vendor/bundle` where you unpacked Annyeonghaseyo. Don't forget to update GEM_PATH if you're not running a system that automatically detects vendored gems.

Sample:

```
git clone https://github.com/vickleford/annyeonghaseyo
cd annyeonghaseyo
bundle install --deployment
gem list
GEM_PATH="$(pwd)/vendor/bundle/ruby/VERS:$GEM_PATH"
gem list
gem build annyeonghaseyo.spec
gem install annyeonghaseyo-0.0.1.gem
gem list
```

h5. `bundle install --system`

This method installs the gems to normal gem path installation directories. Don't run this as root or with sudo--bundle will ask for that on its own.

Sample:

```
git clone https://github.com/vickleford/annyeonghaseyo
cd annyeonghaseyo
bundle install --system
gem list
gem build annyeonghaseyo.spec
gem install annyeonghaseyo-0.0.1.gem
gem list
```

Um, what...?
------------
"Annyeonghaseyo" is "hello" in Korean. I wanted a very basic hello-world type gem to illusrate bundler usage, but "Hello World" was old and tired, so I called it Annyeonghaseyo!!
