```php
public function test_alpha_method()
{
  $beta = Mockery::mock(Beta::class);
  $beta->shouldReceive('doSomething')->once()
      ->andReturn('I did it');

  $alpha = new Alpha($beta);
  $output = $alpha->myMethod();

  $this->assertEquals('I did it', $output);
}
```
```console
OK (1 test, 1 assertion)
```
