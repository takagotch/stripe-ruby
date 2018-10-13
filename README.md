### stripe-ruby
---

https://github.com/stripe/stripe-ruby

```ruby
source 'https://rubygems.org'
gem 'rails'
gem 'stripe'

require "stripe"
Stripe.api_key = "sk_test_..."
Stripe::Charge.list()
Stripe::Charge.retrieve(
  "ch_18aAXCdGbJFKhCuBAa4532Z",
)

require "stripe"
Stripe::Charge.list(
  {},
  {
    :api_key => "sk_test..."
    :stripe_account => "acct_...",
    :stripe_version => "2018-02-28"
  }
)
Stripe::Charge.retrive(
  "ch_18atAXCdGbJFKhCuBAa4532Z",
  {
    :api_key => "sk_test...",
    :stripe_account => "acct_...",
    :stripe_version => "2018-10-14"
  }
)

conn = Faraday.new
client = Stripe::StripeClient.new(conn)
charge, resp = client.request do
  Stripe::Charge.retrieve(
    "ch_18atAXCdGbJFKhCuBAa4532Z",
  )
end
puts resp.request_id

Stripe.api_version = "2018-10-13"

Stripe.ca_bundle_path = "path/to/ca/bundle"

Stripe.max_network_retries = 2

Stripe.open_timeout = 30
Stripe.read_timeout = 80

Stripe.log_level = Stripe::LEVEL_INFO
```

```
gem install stripe
gem build strpe.gemspec

export STRIPE_LOG=info

go get -u github.com/stripe/stripe-mock
stripe-mock
bundle exec rake test
bundle exec ruby -Ilib/ test/stripe/util_test.rb
bundle exec ruby -Ilib/ test/stripe/util_test.rb -n /should.covert.names.to.symbols/
bundle exec rake rubocop
bundle exec rake update_certs

```

