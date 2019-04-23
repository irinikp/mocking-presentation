Class that interacts with external API
```php
class CatApiIntegrator
{
  protected $client;

  public function __construct()
  {
    $this->client = new Client(['base_url' => self::BASE_URL, 'timeout'  => 2.0]);
  }
  
  public function get($image_id)
  {
    return json_decode(($this->client->request('GET',
                self::CLASS_URL . $image_id, ['headers' => $this->headers]
    ))->getBody());
  }
}
```
