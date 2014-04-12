SkinScope API
=============

The SkinScope API was created to help consumers quickly and easily research skincare products before puchasing. It was designed to be consumed by the [SkinScope native iOS app](https://github.com/CarlaCrandall/SkinScope_iOS_App_Prototype).

## Documentation

### Products

|Function|URL|Notes|
|---|---|---|
|**Get all products**|GET api/products|   |
|**Get products by category**|GET api/products?category={category}|**Possible Values for Category:** Cleanser, Toner, Makeup Remover, Exfoliant, Moisturizer, Sunscreen, Serum, Mask, Eye Care, Lip Care, Body Care|
|**Get products by rating**|GET api/products?rating={rating}|**Possible Values for Rating:** Good, Average, Poor, Unknown|
|**Get products by brand**|GET api/products?brand={brand}|Accepts partial values|
|**Get products by name**|GET api/products?name={name}|Accepts partial values|
|**Get product by UPC**|GET api/products?upc={upc}|   |
|**Get product by ID**|GET api/products/{id}|ID refers to the product ID|
|**Create new product**|POST api/products/create|User must be authenticated using basic auth. **Form Data:** **name** - required, must be at least 2 characters, combination of name and brand must be unique; **brand** - required, must be at least 2 characters, combination of name and brand must be unique; **category** - required; value must be either Cleanser, Toner, Makeup Remover, Exfoliant, Moisturizer, Sunscreen, Serum, Mask, Eye Care, Lip Care, or Body Care; **ingredients** - required, must be an array; **upc** - optional, must be 12 digits long, must be unique|

### Reviews

|Function|URL|Notes|
|---|---|---|
|**Get all reviews for specified product**|GET api/products/{id}/reviews|ID refers to the product ID|
|**Get all reviews for specified product based on user's skin type**|GET api/products/{id}/reviews?skin_type={skin_type}|ID refers to the product ID. **Possible Values for Skin Type:** Normal, Oily, Dry, Sensitive, Combination.|
|**Add a review for the specified product**|POST api/products/{id}/reviews/create|ID refers to the product ID. User must be authenticated using basic auth. **Form Data:** **review** - required, must be between 25 and 1000 characters|

### Ingredients

|Function|URL|Notes|
|---|---|---|
|**Get all ingredients**|GET api/ingredients||
|**Get an ingredient by ID**|GET api/ingredients/{id}|ID refers to the ingredient ID|
|**Get all ingredients for specified product**|GET api/products/{id}/ingredients|ID refers to the product ID|
|**Get all ingredients for specified product based on rating**|GET api/products/{id}/ingredients?rating={rating}|ID refers to the product ID. **Possible Values for Rating:** Good, Average, Poor, Unknown|

### Users

|Function|URL|Notes|
|---|---|---|
|**Create a new user**|POST api/users/create|**Form Data:** **first_name** - required, letters only, must be at least 2 characters; **last_name** - required, letters only, must be at least 2 characters; **email** - required, must be a valid email address, must be unique; **password** - required, must be between 6 and 12 characters; **password_confirmation** - required, must match password; **skin_type** - required, must be either Normal, Oily, Dry, Sensitive, or Combination; **photo_src** - optional, file extension must be jpg, jpeg, or png, must be less than 2MB|

SkinScope API was built using the Laravel PHP framework.