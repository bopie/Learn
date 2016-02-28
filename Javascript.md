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

> If a nested function is invoked as a function then its this value will be either the global object (non-strict mode) or undefined (strict mode). 

But if a constructor has no parameters, then JavaScript constructor invocation syntax allows the argument list and parentheses to be omitted entirely.

If, however, a constructor explicitly used the return statement to return an object, then that object becomes the value of the invocation expression. If the constructor uses return with no value, or if it returns a primitive value, that return value is ignored and the new object is used as the value of the invocation.

This kind of dynamic alteration of existing methods is sometimes called “monkey-patching.”
