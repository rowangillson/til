Ruby array shortcuts - "&:" and "&method"

## Call a method on every items with `&:`

So this:

```ruby
[:foo, :bar].each do |item|
  item.to_s
end
```

Can be reduced to:

```
[:foo, :bar].each(&:to_s)
```

But, what if you want to call a method for each item in an array, and this item should be a parameter for this method?

## Call a method with every items as a parameter with `&method`

So this:

```ruby
[:foo, :bar].each do |item|
  puts(item)
end
```

Can be reduced to:

```ruby
[:foo, :bar].each(&method(:puts))
```

viniciusnegrisolo
March 11, 2016
