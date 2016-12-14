# Rutrack

YouTrack REST API Client written in Ruby

[![Gem Version](https://badge.fury.io/rb/rutrack.svg)](http://badge.fury.io/rb/rutrack)

## New in this release 

##### Max issues option & Filter support

- Pass  **max issues** &  **filter** in `get_issues_for` request

Example:

```ruby
filter = "Username: -{No username}" # youtrack-style filter
max = 5000 # max issues to grab
client.projects.get_issues_for(project_name, max, filter)
```

> Note: Default max value for issues to load via API - 500. You can go to Settings page in Admin menu > "Max Issues to Export" and change that value.


## Installation

Add this line to your application's Gemfile:

    gem 'youtrack', :git => "git://github.com/jesusinyourtown1/youtrack.git", :branch => "dev-new"

And then execute:

    $ bundle

## Usage

```ruby

client = Youtrack::Client.new do |c|
  c.url = "https://example.com"
  c.login = "root"
  c.password = "root"

  # Hook into the Net::HTTP set_debug_output method for debugging HTTP Request/Response Cycles
  c.debug = true
end

# Now connect to the server
# It sets the Cookies and returns the Connection response status code
client.connect!

```

## Examples

To get a feel for the API browse the [examples directory](https://github.com/jwaterfaucett/youtrack/tree/master/examples).

## Issues

Any issues or bugs should be well documented submit as many details as possible.
The best issues have the following characteristics:

1. Detail description with a title that conveys the problem well.
2. Gists and/or failing tests that show under what conditions the problem occurs.
3. Environment information, platform, gem version, etc.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Write your feature in Cucumber.
4. Commit your changes (`git commit -am 'Add some feature'`)
5. Make sure your feature and (optional) Rspec test are green.
6. Rebase from master.
7. Push to the branch (`git push origin my-new-feature`)
8. Create new Pull Request.
