SkinScope API
=============

The SkinScope API was created to help consumers quickly and easily research skincare products before puchasing. It was designed to be consumed by the [SkinScope native iOS app](https://github.com/CarlaCrandall/SkinScope_iOS_App_Prototype).

## Documentation

### Products

|Function|URL|Notes|
|---|---|---|
|Get all product|GET api/products|   |
|Get products by category|GET api/products?category={category}|**Possible Values:** Cleanser, Toner, Makeup Remover, Exfoliant, Moisturizer, Sunscreen, Serum, Mask, Eye Care, Lip Care, Body Care|
|Get products by rating|GET api/products?rating={rating}|**Possible Values:** Good, Average, Poor, Unknown|
|Get products by brand|GET api/products?brand={brand}|Accepts partial values|
|Get products by name|GET api/products?name={name}|Accepts partial values|
|Get product by UPC|GET api/products?upc={upc}|   |
|Get product by ID|GET api/products/{id}|ID refers to the product ID|
|Create new product|POST api/products/create|User must be authenticated using basic auth. 

Form Data:

* name - required, must be at least 2 characters, combination of name and brand must be unique
* brand - required, must be at least 2 characters, combination of name and brand must be unique
* category - required; value must be either Cleanser, Toner, Makeup Remover, Exfoliant, Moisturizer, Sunscreen, Serum, Mask, Eye Care, Lip Care, or Body Care
* ingredients - required, must be an array
* upc - optional, must be 12 digits long, must be unique|



SkinScope API was built using the Laravel PHP framework.