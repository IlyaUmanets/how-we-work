How We Work
===========


## Formatting

As usual we use [bbatsov/ruby-style-guide](https://github.com/bbatsov/ruby-style-guide), 
but have some specific usage:

* Limit lines to 110 characters, in order to remove horizontal scrolling on GitHub when we are doing code review
* Align parameters like:

```ruby
# not so bad
def send_mail(source)
  Mailer.deliver(
    to: 'bob@example.com', from: 'us@example.com'
  )
end

# good
def send_mail(source)
  Mailer.deliver(to: 'bob@example.com',
                 from: 'us@example.com',
                 subject: 'Important message',
                 body: source.text)
end

# good (normal indent)
def send_mail(source)
  Mailer.deliver(
    to: 'bob@example.com',
    from: 'us@example.com',
    subject: 'Important message',
    body: source.text
  )
end
```

## Working with Bugs

* All bugs should be covered with tests and by TDD

## Simplify Views

* We use Decorators (in code we called them `Carrier`) as View and Form objects
* We do not use full Presenters (TODO: add link to first post about them) with tag generations

## Setup Development Environment

* `bin/setup` - cold setup
* `rake setup`
* `rake setup_sample_data`

## Delivery Flow

* create PR
* deploy PR to Heroku
* ask verify, to code review and to merge

## TODO/FIXME Notes

* add issue on GitHub per each note
* create TODO/FIXME note in the code
* add in code's note link to GitHub's issue