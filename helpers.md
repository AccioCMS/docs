# Helpers

- [Introduction](../The%20Basics/helpers.md#introduction)
- [Available Methods](../The%20Basics/helpers.md#available-methods)

## Introduction
Accio includes a variety of global "helper" PHP functions and also uses a lot of laravel framework "helpers". To learn 
more about laravel helper please visit [Laravel Official Website](https://laravel.com). You are free to use them in your
own applications if you find them convenient.


## Available Methods

<style>
    .collection-method-list > p {
        column-count: 3; -moz-column-count: 3; -webkit-column-count: 3;
        column-gap: 2em; -moz-column-gap: 2em; -webkit-column-gap: 2em;
    }

    .collection-method-list a {
        display: block;
    }
</style>

### [URLs](#urls-methods)

<div class="collection-method-list" markdown="1">

[assetUrl](#asseturl)
[cssUrl](#cssurl)
[imageUrl](#imageurl)
[jsUrl](#jsurl)
[fontUrl](#fonturl)
[shareUrl](#shareurl)
[uploadsURL](#uploadsurl)

</div>


### Paths
<div class="collection-method-list" markdown="1">

[pluginsPath](#pluginspath)
[tmpPath](#tmppath)
[accioPath](#acciopath)
[stubPath](#stubpath)
[uploadsPath](#uploadspath)
[projectDirectory](#projectdirectory)

</div>

### Post
<div class="collection-method-list" markdown="1">

[findPostByID](#findpostbyid)
[findPostBySlug](#findpostbyslug)
[homepage](#homepage)

</div>

### Post Type

<div class="collection-method-list" markdown="1">

[cleanPostTypeSlug](#cleanposttypeslug)
[getPostType](#getposttype)
[isPostType](#isposttype)

</div>

### Miscellaneous

<div class="collection-method-list" markdown="1">

[css](#css)
[js](#js)
[menu](#menu)
[languages](#languages)
[searchForm](#searchForm)
[getLocale](#getLocale)
[noImage](#noImage)
[searchKeyword](#searchKeyword)
[settings](#settings)
[googleAnalytics](#googleAnalytics)
[googleTagManager](#googleTagManager)
[googleTagManagerBody](#googleTagManagerBody)
[metaTags](#metaTags)
[permalink](#permalink)
[authControllerExist](#authControllerExist)
[error404](#error404)
[isSecure](#isSecure)
[adminURL](#adminURL)
[isInAdmin](#isInAdmin)
[currentMenuLink](#currentMenuLink)
[isMobile](#isMobile)
[isTablet](#isTablet)
[themeNamespace](#themeNamespace)
[categoriesRelationTable](#categoriesRelationTable)
[tagsRelationTable](#tagsRelationTable)
[mediaRelationTable](#mediaRelationTable)

</div>

## Method Listing

### URLs Methods

<a name="asseturl"></a>
#### `assetURL`
The `assetURL` function returns the full qualified path to the active theme asset directory. You might want to use this 
function to link specific assets of the theme. Returns FileNotFound exception if file does not exit:
```php
$assetUrl = assetURL('css/style.css');

// http://yoursite.com/themes/DefaultTheme/assets/css/style.css
````
If no parameter value is given, assets' full url will be returned.

<a name="cssurl"></a>
#### `cssUrl`
The `cssUrl` function returns the full qualified path to the active theme css directory. You might want to use this function
to link custom css of your theme. Returns FileNotFound exception if file does not exit:
```php
$cssUrl = cssUrl('customStyle.css');
```

<a name="imageurl"></a>
#### `imageUrl`
The `imageUrl` function returns the full qualified path to the active theme image directory. You might want to use this 
function to get the path of a custom static image located in themes image directory. . Returns FileNotFound exception 
if file does not exit:
```php
$imageUrl = imageUrl('logo.jpg');
```

<a name="jsurl"></a>
#### `jsUrl`
The `jsUrl` function returns the full qualified path to the active theme js directory. You might want to use this function
to link custom js of your theme. Returns FileNotFound exception if file does not exit:
```php
$jsUrl = jsUrl('customJS.js');
```

<a name="fonturl"></a>
#### `fontUrl`
The `fontUrl` function returns the full qualified path to the active theme font directory. You might want to use this function
to link custom fonts of your theme. Returns FileNotFound exception if file does not exit:
```php
$fontUrl = fontUrl('Times New Roman.woff2');
```

<a name="shareurl"></a>
#### `shareUrl`
The `shareUrl` function returns array urls used for sharing specific link to each social media. It has two parameter the
url you want to share in social nedia and a title (optional) if you want to specify one. Currently supports share url for 
`Twitter`, `Facebook`, `LinkedIn` `Viber` and `WhatsApp`
```php
$shareUrl = shareUrl('link-to-post');

print_r($shareUrl);

echo $shareUrl['facebook'];
```

<a name="uploadsurl"></a>
#### `uploadsURL`
The `uploadsURL` function returns the full qualified path to the application upload directory. You might want to use 
`uploadsURL` to get access to a dynamic uploaded item `/public/uploads/~`. Returns FileNotFound exception if file does 
not exit: 
```php
$uploadsPath = uploadsURL('2019/01/01/file-name');
```


### Path Methods

<a name="pluginspath"></a>
#### `pluginsPath`
The `pluginsPath` function returns the full qualified path to the plugin directory. You might want to use `pluginsPath` 
to use a specific plugins files. Returns FileNotFound exception if file does not exit:
```php
$file = pluginsPath('MyPlugin/myPluginFile');
```

<a name="tmppath"></a>
#### `tmpPath`
The `pluginsPath` function returns the full qualified path to the tmp directory. You might want to use `tmpPath` 
to use a specific tmp files. Returns FileNotFound exception if file does not exit:
```php
$tmpFile = tmpPath('tmpFile');
```

<a name="acciopath"></a>
#### `accioPath`
The `accioPath` function returns the full qualified path to the cms core directory. This function is used by the cms 
itself however you might want to use `accioPath` to use a specific tmp files. Returns FileNotFound exception if file 
does not exit:
```php
$tmpFile = tmpPath('tmpFile');
```

<a name="stubpath"></a>
#### `stubPath`
The `stubPath` function returns the full qualified path to the cms stub directory. This function is used by the cms 
itself however you might want to use `stubPath` to make use of cms stub files. Returns FileNotFound exception if file 
does not exit:
```php
$stubPath = stubPath('stub-file');
```

<a name="uploadspath"></a>
#### `uploadsPath`
The `uploadsPath` function returns the full qualified path to the upload directory. This function is used by the cms 
itself however you might want to use `uploadsPath` to make use of dynamic uploaded files. Returns FileNotFound exception
if file does not exit:
```php
$file = uploadsPath('2019/01/01/original/file-name');
```

<a name="projectdirectory"></a>
#### `projectDirectory`
The `projectDirectory` function returns the base path of your project. Returns FileNotFound exception if file does not 
exit:
```php
$projectDirectory = projectDirectory();

echo $projectDirectory;
```

### Post Methods


<a name="findpostbyid"></a>
#### `findPostByID`
The `findPostByID` function is use to find a post using it's ID. Accepts two parameters, the `post id` and the 
`post type slug` (optional). If the post slug parameter is not provided the default one is used (`post_articles`):
```php
$article = findPostByID(5);

$page = findPostByID(5, 'post_pages');
```


<a name="findpostbyslug"></a>
#### `findPostBySlug`
The `findPostBySlug` function is use to find a post using it's slug. Accepts two parameters, the `post slug` and the 
`post type slug` (optional). If the post slug parameter is not provided the default one is used (`post_articles`):
```php
$article = findPostBySlug('my-post');

$page = findPostBySlug('my-page', 'post_pages');
```

<a name="homepage"></a>
#### `homepage`
The `homepage` function is use to find the configured `home page`. Accepts one parameter, the `columnName`. If the column 
name is defined return the value of the required field (column) of the homepage, otherwise will return the homepage as 
post object:
```php
$homepageObject = homepage();

$homepageTitle = homepage('title');
```


<a name="cleanposttypeslug"></a>
#### `cleanPostTypeSlug`
The `cleanPostTypeSlug` is function use to remove the `post_` prefix in a string and replace it with something else, 
default with empty string. Accepts two parameter, the `postTypeSlug` and the replace string (optional):
```php
$postTypeSlug = cleanPostTypeSlug('post_articles');

$postTypeSlug = cleanPostTypeSlug('post_articles', '');
```


<a name="getposttype"></a>
#### `getPostType`
The `getPostType` function is use to find the post type by using it's slug. Accepts one parameter, the `postTypeSlug`. 
Returns post type object. You might want to use `getPostType` to get the specific post type in your project:
```php
$postType = getPostType('post_articles');
```


### Miscellaneous Methods


<a name="css"></a>
#### `css`
The `css` function is use to print theme css as configured on /public/{ACTIVE THEME NAME}/config/theme.php. Accepts four 
parameters, `header` (boolean) if css will be printed in header (true is the default), `defaultAttributes` (array) 
attributes to be assigned to every link tag, `files` (array) which css files to be printed default uses array configured
in `theme/{ACTIVE THEME NAME}/config.json`, `noScript` (boolean) if css should be printed within `<noscript></noscript>`
tag.
```php
css();
    
// print on footer
css(false);

// add extra attributes
css(true, ['rel' => 'stylesheet']);

// print only specific style
css(true, [], ['custom-style.css']);

// print css within noscript 
css(true, [], ['custom-style.css'], true);
// prints: "<noscript>...<noscript>"
```

<a name="js"></a>
#### `js`
The `js` function is use to print theme js scripts as configured on /public/{ACTIVE THEME NAME}/config/theme.php. Accepts 
three parameters, `header` (boolean) if css will be printed in header (true is the default), `defaultAttributes` (array) 
attributes to be assigned to every script tag, `files` (array) which css files to be printed default uses array configured
in `theme/{ACTIVE THEME NAME}/config.json`.
```php
js();
    
// print on footer
js(false);

// add extra attributes
js(true, ['async']);

// print only specific script
js(true, [], ['custom-script.js']);
```


<a name="menu"></a>
#### `menu`
The `menu` function is use to print a menu. Accepts three parameters, `menuSlug` default "primary", `customView` to use 
a custom view for the menu, default `vendor.menulinks.bootstrap-4`, `ulClass` add extra class to menus ul tag.
```php
menu('primary');

// with custom view
menu('primary', 'vendor.menulinks.custom-menu-view');
```

<a name="languages"></a>
#### `languages`
The `menu` function is use to print all languages. Accepts two parameters, `customView` to use a custom view default 
`vendor.languages.default`, `ulClass` add extra class to menus ul tag.
```php
languages();

// with custom view
languages('vendor.languages.custom-languages-view');
```

<a name="searchForm"></a>
#### `searchForm`
The `searchForm` function generates a default search form.  Accepts two parameters, `customView` to use a custom view 
default `vendor.search.default`, `formClass` add extra class to menus ul tag.
```php
searchForm();

// with custom view
searchForm('vendor.search.custom-search-view');
```

<a name="getLocale"></a>
#### `getLocale`
The `getLocale` function returns the current language slug. Shortcut for `App::getLocale()`.
```php
$currentLanguageSlug = getLocale();
```

<a name="noImage"></a>
#### `noImage`
The `noImage` function generates a placeholder image. You might want to use a custom image placeholder by settings the 
`imagePath` to your custom image path.

```php
echo noImage();

// use custom placeholder
echo noImage('my-placeholder.jpg');
```

<a name="searchKeyword"></a>
#### `searchKeyword`
You can use `searchKeyword` function on search pages when you want to retrive the search keyword. 
```php
$keyword = searchKeyword();
```

<a name="settings"></a>
#### `settings`
Use `settings` function to get settings data by using the settings key.   
```php
$siteTitle = settings('siteTitle');
```

<a name="googleAnalytics"></a>
#### `googleAnalytics`
The `googleAnalytics` function generates google analytics script. If no trackingID is provided the default one is used.
The default trackingID is configured in admin panel settings.
```php
echo googleAnalytics('GA_TRACKING_ID');
```

<a name="googleTagManager"></a>
#### `googleTagManager`
The `googleTagManager` function generates google tag manager head script. If no containerID is provided the default one 
is used.
The default containerID is configured in admin panel settings. 
```php
echo googleTagManager('CONTAINER_ID');
```

<a name="googleTagManagerBody"></a>
#### `googleTagManagerBody`
The `googleTagManagerBody` function generates google tag manager head script. If no containerID is provided the default 
one is used.
The default containerID is configured in admin panel settings. 
```php
echo googleTagManagerBody('CONTAINER_ID');
```

<a name="metaTags"></a>
#### `metaTags`
The `metaTags` function generates all meta tags for the current page. It accepts two optional parameters, `model` custom
model object and `customData` to change meta tags values.
```php
metaTags();

// with custom model
metaTags(new Post());

// with custom data
metaTags(null, ['title' => 'My site title']);
```

<a name="permalink"></a>
#### `permalink`
Use `permalink` function to retrive permalinks. Accepts three parameters, `belongsTo` the app of the permalink, `name`
the name of the permalink and `defaultURL` (optional) return this default url if the permalink doesn't exist.
```php
permalink("base","homepage");
```

<a name="authControllerExist"></a>
#### `authControllerExist`
Use `authControllerExist` function to check if the active theme has auth controllers.
```php
authControllerExist();
```

<a name="error404"></a>
#### `error404`
Returns 404 page.
```php
error404();
```

<a name="isSecure"></a>
#### `isSecure`
`isSecure` check if the connection is secured and returns a boolean.
```php
$isSecured = isSecure();

if ($isSecured) { ... }
```

<a name="adminURL"></a>
#### `adminURL`
The `adminURL` function returns the full qualified url to the admin panel. 
```php
$adminUrl = adminURL();
```

<a name="isInAdmin"></a>
#### `isInAdmin`
Use `isInAdmin` to check if the current url belongs to the admin routes.  
```php
if (isInAdmin()) { ... }
```

<a name="currentMenuLink"></a>
#### `currentMenuLink`
The `currentMenuLink` function returns the object of the menu-link if the current url is part of a menu. Accepts one 
parameter, `columnName` (optional) default null, return only a specific field instead of the full MenuLink object. 
```php
currentMenuLink();
```

<a name="isMobile"></a>
#### `isMobile`
Use `isMobile` to check if site is access via mobile.
```php
if (isMobile()) { ... }
```

<a name="isMobile"></a>
#### `isTablet`
Use `isTablet` to check if site is access via tablet.
```php
if (isTablet()) { ... }
```

<a name="themeNamespace"></a>
#### `themeNamespace`
The `themeNamespace` function return the namespace of the active theme.
```php
$themeNamespace =  themeNamespace();
```

<a name="categoriesRelationTable"></a>
#### `categoriesRelationTable`
Use `categoriesRelationTable` function to get the category relation pivot table for a specific post type. 
```php
$pivotTable =  categoriesRelationTable('post_articles');
```

<a name="tagsRelationTable"></a>
#### `tagsRelationTable`
Use `tagsRelationTable` function to get the tag relation pivot table for a specific post type. 
```php
$pivotTable =  tagsRelationTable('post_articles');
```

<a name="mediaRelationTable"></a>
#### `mediaRelationTable`
Use `mediaRelationTable` function to get the media relation pivot table for a specific post type. 
```php
$pivotTable =  mediaRelationTable('post_articles');
```