Dependency injection into the Controller
```php
class ImageController extends Controller
{
  protected $service;
  
  public function __construct(CatApiIntegrator $service)
  {
    $this->service = $service;
  }
  
  public function show($id)
  {
    $cat_json = $this->service->get($id);
    return CatImage::populate($cat_json);
  }
}
```
