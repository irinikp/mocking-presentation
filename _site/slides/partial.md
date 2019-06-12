Partial Mocking 

<img data-src="img/angel_devil.png" style="background:none; border:none; box-shadow:none; width: 150px"/>

Note:
Any method on a partially mocked class that has expectations set up will be mocked, but calls to any other methods will pass through the real class.

If you need partial mocking, probably you don't follow the Single Responsibility Principle

You may need it in case refactoring is not an option for whatever reason (p.ex. if you autogenerate a class from a third party API)

A class with dependency injection is much easier to test.
 
