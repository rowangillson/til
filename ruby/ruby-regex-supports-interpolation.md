#Ruby Regex Supports Interpolation

Today we built a Ruby regex that included an interpolated string. It looked like this:

```ruby
# app/models/developer.rb
validates :email, format: { with: /\A.+@(#{ENV['permitted_domains']})\z/ }
```

This allows `permitted_domains` to be customized as an environmental variable:

```yml
# config/application.yml
permitted_domains: 'hashrocket.com|hshrckt.com'
```

The parens and pipe allow us to white-list multiple domains in a single environmental variable.

jakeworth
January 28, 2016
