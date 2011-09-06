# gmd

A script for easily making and releasing gems with minimal fuss.

Assumptions it makes:
- you use Github
- you use `rake` to start tests


## Install

    curl -s https://raw.github.com/hawx/gmd/master/gmd -o /usr/local/bin/gmd
    chmod +x /usr/local/bin/gmd

Will download the script to `/usr/local/bin` (obviously you can change this
to anywhere on your $PATH) and then makes it executable.


## Usage

### `gmd <GEMNAME>`

    gmd my_gem
    # Using this:
    # - assumes the main namespace is called MyGem
    # - and creates my_gem.gemspec and Rakefile

The Rakefile contains two tasks, one is a simple test task (`rake test`), 
the other to generate man pages (`rake man`). There is also a commented out 
test task for rspec.

You will want to edit the gemspec immediately as there is just filler 
descriptions and summaries.

  
### `gmd install`

Builds the gem to `./pkg` and installs it locally.


### `gmd release`

Runs the tests (calls `rake`), then asks if it is ok to publish so you don't
push a gem which fails it's tests accidentally.
Then asks if you want the last commit tagging with the new version number.
Then builds the new gem to `./pkg` and pushes it to rubygems.

  

   
 