# HTTP Requests and Sidekiq

__Created by @sjreich__

Many companies use a microservices architecture, in which many small parts of their system communicate with one another via HTTP requests.  Typically, we use Sidekiq or similar libraries like Delayed Job and Resque, to make those requests asynchronously and to handle retrying requests
if something goes wrong.

This exercise introduces the relevant concepts via Sidekiq.

## Setup

The setup for this exercise is a bit complicated.  Sorry.

1. Bring in this repo, and its dependencies.
  ```bash
  $ git clone <copy the address from github>
  $ cd sidekiq-and-http-exercise
  $ bundle install
  ```

2. You'll need a [Redis](http://redis.io) server running locally.  In a new terminal window, run:
  ```bash
    $ brew install redis
    $ redis-server
  ```

3. Start the web server you'll be interacting with.  In a new terminal window, run:
  ```bash
    $ ruby server/server.rb
  ```

4. Start the sidekiq background process(es).  In a new terminal window, run:
  ```bash
    $ bundle exec sidekiq -r ./client/sidekiq_workers.rb
  ```


## The Exercises

The main file to work on is 'client/main.rb'.  Read it, edit it, execute it.
  ```bash
    $ ruby client/main.rb
  ```

You'll also need to edit 'client/sidekiq_workers.rb'.  For your changes there to take effect,
you will need to kill off the existing sidekiq process(es) with `ctrl-C`, and then restart
them using the command above.

When you're done, kill off everything with `ctrl-C`.

## Resources
- [Homebrew: MacOS package manager](https://brew.sh/)
- [Redis Documentation](https://redis.io/)
- [Sidekiq])(https://github.com/mperham/sidekiq/wiki)
