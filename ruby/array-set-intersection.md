Ruby Array Set Intersection

Ruby's Array class has a method `&` which returns a new array containing elements common to two arrays, excluding duplicates.

I used this on a project today to compare a random number (17) to a set of numbers with special meaning to the program.

```ruby
2.2.2 :001 > (5..32).step(3).to_a & [17]
 => [17]
2.2.2 :002 > ((5..32).step(3).to_a & [17]).size > 0
 => true
```

The order is preserved from the original array:

```ruby
2.2.2 :003 > [2,3,1] & [1,2,3]
 => [2, 3, 1]
```

h/t Chris Erin

jakeworth
June 30, 2015
