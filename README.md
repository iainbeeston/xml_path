# XmlPatch

[![Build Status](https://travis-ci.org/iainbeeston/xml_patch.svg?branch=master)](https://travis-ci.org/iainbeeston/xml_patch)
[![Maintainability](https://api.codeclimate.com/v1/badges/048c9e7b3b129c80a2e0/maintainability)](https://codeclimate.com/github/iainbeeston/xml_patch/maintainability)

An implementation of [XML Patch (RFC5261)](https://tools.ietf.org/html/rfc5261) in ruby.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'xml_patch'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install xml_patch

## Usage

To apply an xml patch to an xml string:

``` ruby
require 'xml_patch'

patch = '<diff><remove sel="/foo" /></diff>'
xml = '<foo /><bar />'

XmlPatch.apply(patch).to(xml)
# => "<bar />"
```

## Limitations

So far this implementation supports:

* `<remove>` elements

But not:

* `<add>` elements
* `<replace>` elements

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/xml_patch. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the XmlPatch project’s codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/[USERNAME]/xml_patch/blob/master/CODE_OF_CONDUCT.md).
