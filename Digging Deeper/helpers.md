# Helpers

- [Introduction](../The%20Basics/helpers.md#introduction)
- [Available Methods](../The%20Basics/helpers.md#available-methods)

## Introduction
çka jane pse jane.


## Available Methods

### [URLs](#urls-methods)
- [assetUrl](#asseturl)
- [cssUrl](#cssurl)
- [imageUrl](#imageurl)
- [jsUrl](#jsurl)
- [fontUrl](#fonturl)
- [shareUrl](#shareurl)
- [uploadsURL](#uploadsurl)

### Paths
- pluginsPath
- tmpPath
- accioPath
- stubPath
- uploadsPath
- projectDirectory

### Post
- findPostByID
- findPostBySlug
- findPost
- 
### Post Type
- noPostTypeSlug
- getPostType
- isPostType

### Miscellaneous
- css
- js
- menu
- languages
- searchForm
- getLocale
- noImage
- searchKeyword
- settings
- googleAnalytics
- googleTagManager
- googleTagManagerBody
- metaTags
- permalink
- routeIsActive
- authControllerExist
- error404
- isSecure
- adminURL
- isInAdmin
- currentMenuLink
- isMobile
- isTablet
- categoriesRelationTable
- tagsRelationTable
- mediaRelationTable

## Method Listing

### URLs Methods

#### `assetURL`
The `assetURL` prints the absolute url of an asset.
```php
print assetURL('css/style.css');

// http://yoursite.com/themes/DefaultTheme/assets/css/style.css
````
If no parameter value is given, assets' full url will be returned.

#### `cssUrl`
The `cssUrl` function

#### `imageUrl`
The `imageUrl` function

#### `jsUrl`
The `jsUrl` function

#### `fontUrl`
The `fontUrl` function

#### `shareUrl`
The `shareUrl` function

#### `uploadsURL`
The `uploadsURL` function
