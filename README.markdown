# ruby-boost-regex

Wraps the Boost.Regex library to provide Boost regexes. Why? Why not!
(Plus, it's worth seeing if it's faster.)

I'm trying to match the API to be at least completely compatible with
normal `Regexp`s, and then add Boost features. So far...

## Features

* Matches set global special variables like $`, $1-$9, $&, and so on
* Supports `=~` operator, `===` operator (for `case...when`)
* Supports `#match` method as in normal Regexps, returning the same
  type of object (`MatchData`).
  
## Ideas down the line

Add a #boost! method to normal Regexps, so you can use syntax like:

    reg = /\d{3}-\d{3}-\d{4}/.boost!(optional_boost_only_flags)
    
Allowing you to enjoy literal Regexp syntax with any benefits that Boost
might provide.

## Usage

Don't have it as a gem yet. Sorry! But you could do this in theory:

    r = Boost::Regexp.new("(\\d{3})-(\\d{3})-(\\d{4})")
    r =~ "555-123-4567"
    p $1 # ==> "555"
    matches = r.match("123-456-7890")
    p matches[2] # ==> "456"


## Note on Patches/Pull Requests
 
* Fork the project.
* Make your feature addition or bug fix.
* Add tests for it. This is important so I don't break it in a
  future version unintentionally.
* Commit, do not mess with rakefile, version, or history.
  (if you want to have your own version, that is fine but
   bump version in a commit by itself I can ignore when I pull)
* Send me a pull request. Bonus points for topic branches.

## Copyright

Copyright (c) 2010 Michael Edgar. See LICENSE for details.