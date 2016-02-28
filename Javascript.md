#### property attributes
* writable
* enumerable
* configurable

#### object attributes
* prototype
* class
* extensible

#### three categories of objects and two types of properties
* native object
* host object
* user-defined
* own property
* inheerited property

#### array methods
* forEach
* map
* filter
* every & some
* reduce & reduceRight
* indexOf & lastIndexOf

#### invoking functions
* function invocation
* method invocation
* constructor invocation
* indirect invocation

If a nested function is invoked as a function then its this value will be either the global object (non-strict mode) or undefined (strict mode). 

But if a constructor has no parameters, then JavaScript constructor invocation syntax allows the argument list and parentheses to be omitted entirely.

If, however, a constructor explicitly used the return statement to return an object, then that object becomes the value of the invocation expression. If the constructor uses return with no value, or if it returns a primitive value, that return value is ignored and the new object is used as the value of the invocation.

This kind of dynamic alteration of existing methods is sometimes called “monkey-patching.”

``` javascript
// Return a memoized version of f.
// It only works if arguments to f all have distinct string representations.
function memoize(f) {
    var cache = {}; // Value cache stored in the closure.
    return function () {
// Create a string version of the arguments to use as a cache key.
        var key = arguments.length + Array.prototype.join.call(arguments, ",");
        if (key in cache) return cache[key];
        else return cache[key] = f.apply(this, arguments);
    };
}
// Return the Greatest Common Divisor of two integers, using the Euclidian // algorithm: http://en.wikipedia.org/wiki/Euclidean_algorithm
function gcd(a, b) { // Type checking for a and b has been omitted
    var t; // Temporary variable for swapping values if (a < b) t=b, b=a, a=t; // Ensure that a >= b
    while (b != 0) t = b, b = a % b, a = t; // This is Euclid's algorithm for GCD return a;
}
var gcdmemo = memoize(gcd);
gcdmemo(85, 187) // => 17
// Note that when we write a recursive function that we will be memoizing, // we typically want to recurse to the memoized version, not the original.
var factorial = memoize(function (n) {
    return (n <= 1) ? 1 : n * factorial(n - 1);
});
factorial(5) // => 120. Also caches values for 4, 3, 2 and 1.
```

``` javascrit
function Range(from, to) {
    this.from = from;
    this.to = to;
}

Range.prototype = {
    includes: function (x) {
        return this.from <= x && x <= this.to;
    },

    foreach: function (f) {
        for (var x = Math.ceil(this.from); x <= this.to; x++) f(x);
    },

    toString: function () {
        return "(" + this.from + "..." + this.to + ")";
    }
};
```
