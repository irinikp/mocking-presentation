```php
public function myMethod()
{
  return $this->beta->doSomething("hello", "world");
}
```
```php
public function test_alpha_method()
{
  $beta = Mockery::mock(Beta::class);
  $beta->shouldReceive('doSomething')->once()->withArgs([])
      ->andReturn('I did it');

  $alpha  = new Alpha($beta);
  $output = $alpha->myMethod();

  $this->assertEquals('I did it', $output);
}
```
```console
1) Demo\TestAlpha::test_alpha_method
Mockery\Exception\NoMatchingExpectationException:
No matching handler found for Mockery_0_Demo_Beta::doSomething('hello', 'world').
Either the method was unexpected or its arguments
matched no expected argument list for this method
```
Note: 
with arguments
