### Konacha
---
https://github.com/jfirebaugh/konacha

```ruby
group :test, :development do
  gem 'konacha'
end

Rails.application.routes.draw do
  mount Konacha::Engine, at: "/konacha" if defined?(Konacha)
end

# config/initializers/konacha.rb

Konacha.configure do |config|
  config.spec_dir = "spec/javascripts"
  config.spec_matcher = /_spec\.|_test\./
  config.stylesheets = %w(application)
  config.driver = :selenium
end if defined?(Konacha)

Konacha.configure do |config|
  require 'capybara/poltergeist'
  config.driver = :poltergist
end if defined?(Konacha)

group :development, :test do
  gem "ejs"
end

```

```js
//=require array_sum
describe("Array#sum", function(){
  it("returns 0 when the Array is empty", function(){
    [].sum().should.equal(0);
  });
  it("returns the sum of numeric elements", function(){
    [1,2,3].sum().should.equal(6);
  });
});

//= require spec_helper
//= require array_sum
describe("Array#sum", function(){
});

mocha.ui('bdd');
mocha.globals(['YUI']);
mocha.ignoreLeaks();
mocha.timeout(5);
chai.config.includeStack = true;

//= require_tree ./templates

//= require spec_helper
descibe("templating", function(){
  it("is built in to Sprockets", function(){
    $('body').html(JST['templates/hello']());
    $('body h1').text().should.equal('Hello');
  });
});
```

```coffee
#= require array_sum
describe "Array#sum", ->
  it "returns 0 when the Array is empty", ->
    [].sum().should.equal(0)
  it "returns the sum of numeric elements", ->
    [1,2,3].sum().should.equal(6)


```

```
bundle exec rake konacha:serve

bundle exec rake konacha:run
bundle exec rake konacha:run SPEC=foo_spec
bundle exec rake konacha:run SPEC=foo_spec,bar_spec,etc_spec

bundle exec rake ci:setup:rspec spec konacha:run FORMAT=CI::Reporter::RSpec

git clone git://github.com/jfirebaugh/kanacha.git
bundle exec rake
cd mocah
git checkout master
bundle exec rake assets
```

```ejs
<h1>Hello Konacha!</hq>
```


