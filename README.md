# spring tips and tricks

* You can wrapping request params to object in controller method as below;
```
public ResponseEntity<List<ProductDto>> search(ProductSearchRequest productSearchRequest) {
    return ResponseEntity.ok(productSearchManager.retrieveProduct(productSearchRequest));
}
```

You can access this method via url : http://{host}:{ip}/search?name=nike&category=clothes

* You can inject model entity on controller method as below;
```
public ResponseEntity<Product> retrieve(@PathVariable("id") Product product) {
    return ResponseEntity.ok(product);
}
```

Spring data will be able to convert path/request param to entity. Id should be primary key.
Retrieve product with this : http://{host}:{ip}/product/1
