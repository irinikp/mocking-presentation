```php
public function test_alpha_method()
{
  $beta = Mockery::mock(Beta::class);
  $beta->shouldReceive('doSomething')->twice()
      ->andReturn('I did it');

  $alpha = new Alpha($beta);
  $output = $alpha->myMethod();

  $this->assertEquals('I did it', $output);
}
```
```console
1) Demo\TestAlpha::test_alpha_method
Mockery\Exception\InvalidCountException: Method doSomething(<Any Arguments>)
from Mockery_0_Demo_Beta should be called exactly 2 times
but called 1 times.
```
