Mock the API Integrator to test the Controller
```php
public function test_show_creates_a_cat_image_with_breed_based()
{
  // Arrange
  $id = 'kiLo4r';
  $service = Mockery::mock(CatApiIntegrator::class);
  $json_output = File::get(base_path("tests/data/sample_$id.json"));
  $service->shouldReceive('get')->once()
      ->withArgs([$id])->andReturn(json_decode($json_output));
      
  // Act
  $cat = (new ImageController($service))->show($id);
  
  // Assert
  $this->assertEquals($cat->id, $id);
  $this->assertEquals($cat->url, "https://cdn2.thecatapi.com/images/$id.jpg");
}
```
