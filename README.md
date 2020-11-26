# documenu npm package

Documenu is an that API provides access to a Database of over 600,000 US Restaurant Menus with over 50,000,000 individual menu items.
[https://documenu.com](https://documenu.com)

This package is intended to make it easier to interact with the API when using NodeJS

## Install
```shell
npm install -S documenu
```

## Configure

In order to use this API you need an API key. You can get it here: [Get API Key](https://documenu.com/register)

```js
const Documenu = require('documenu')
Documenu.configure('YOUR-API-KEY')
```

## API

### Restaurants

```js
let result = await Documenu.Restaurants.getByState('NY');
Documenu.Restaurants.getByState('NY')
.then(res=> {
	console.log(res);
});
```

### Menu Items

```js
const params = {
	"lat": "40.68919",
	"distance": "1",
	"lon": "-73.992378",
	"page": "1"
}
let result = await Documenu.MenuItems.searchGeo(params)
Documenu.Restaurants.MenuItems.searchGeo(params)
.then(res=> {
	console.log(res);
});
```

## Available resources and methods


### Restaurants
  - `get(restaurantid)`
    - `restaurantid : string`
  - `getMenuItems(restaurantid)`
    - `restaurantid : string`
    - `Params (Optional)`
      - `size | number | Data Size of Results	`
      - `page | number | Page Through Results	`
  - `searchFields(params)`
    - `Params (Optional)`
      - `exact | Boolean | Search for exact match to terms`
      - `restaurant_name | string | Data Size of Results `
      - `restaurant_phone  | string | Search By Phone Number `
      - `restaurant_website  | string | Search By Website `
      - `address  | string | Search By Address  `
      - `state  | string | Search By State Code `
      - `zip_code  | number | Search By Zip Code  `
      - `size | number | Data Size of Results `
      - `page | number | Page Through Results	`  
      - `fullmenu | Boolean | include full menus `  
  - `searchGeo(params)`
    - `Params (Required)`
      - `lat | number | Latitude of search area `  
      - `lon | number | Longitude of search area `  
      - `distance | number | Search Area radius (in miles)  `  
    - `Params (Optional)`
      - `size | number | Data Size of Results `
      - `page | number | Page Through Results `  
      - `fullmenu | Boolean | include full menus `  
  - `getByState(state,params)`
    - `state : string`
    - `Params (Optional)`
      - `size | number | Data Size of Results `
      - `page | number | Page Through Results `  
      - `fullmenu | Boolean | include full menus ` 
  - `getByZipCode(zip,params)`
    - `zip : string`  
    - `Params (Optional)`
      - `size | number | Data Size of Results `
      - `page | number | Page Through Results `  
      - `fullmenu | Boolean | include full menus `   
  - `geoBoundingBox(params)`
    - `Params (Required)`
      - `top_left | string | Top Left coordinates of Bounding Box in lat,lon `  
      - `bottom_right  | string | Bottom Right coordinates of Bounding Box in lat,lon` 
    - `Params (Optional)`
      - `size | number | Data Size of Results `
      - `page | number | Page Through Results `  
      - `fullmenu | Boolean | include full menus `   
  - `withinTravelRadius(state,params)`
    - `Params (Required)`
      - `lat | number | Latitude of search area `  
      - `lon | number | Longitude of search area `  
      - `minutes | number | Number of minutes `  
      - `mode | string | Mode of Transport (walking or driving) `  
    - `Params (Optional)`
      - `size | number | Data Size of Results `
      - `page | number | Page Through Results `  
      - `fullmenu | Boolean | include full menus `   
  - `withinGeoPolygon(points,params)`
    - `points: Array of points in [[lat,lon]] format` 
    - `Params (Optional)`
      - `size | number | Data Size of Results `
      - `page | number | Page Through Results `  
      - `fullmenu | Boolean | include full menus ` 

### MenuItems
  - `get(itemid)`
    - `itemid : string`
  - `searchGeo(params)`
    - `Params (Required)`
      - `lat | number | Latitude of search area `  
      - `lon | number | Longitude of search area `  
      - `distance | number | Search Area radius (in miles)  `  
    - `Params (Optional)`
      - `size | number | Data Size of Results `
      - `page | number | Page Through Results `  

## API Docs

View API Docs here: [https://documenu.com/docs](https://documenu.com/docs)

For Support Email support@documenu.com
