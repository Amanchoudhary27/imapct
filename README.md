Shopify + Compass + Foundation 5
============
Template Credit: Shopify-Foundation-Theme
https://github.com/Cam/Shopify-Foundation-Theme

Live Demo: http://impact-theme.myshopify.com/

Requirements
---------------------
Foundation 5

SCSS & Foundation
---------------------
This project uses compass to compile locally and imports Foundation 5. The SCSS files are converted to scss.liquid files. We use a manifest to import all partials to one main file. 

*** NOTE: For Settings (Thanks to http://experts.shopify.com/graphika )
To compile {{ settings.some_setting }} through compass without 
having errors you can use a trick called unquote(""): 

    $theme-setting-variable-that-propagates-throughout-my-css:unquote("{{ settings.some_setting }}");

Or in SASS you can use interpolations to output plain CSS as-is. For example

    .test {
        background: url( #{'{{ settings.some_setting }}' )
    }


base.scss contains our config setting variables for the shopify admin section and we set the regular setting variables from foundation as !default, which allows us to overide these easily. 

Installation
---------------------

We will first want to make sure compass is installed.

In command line run 
    
    gem install compass

Foundation now uses bower to install the foundation dependancies. To keep dependacies outside of the shopify theme directory, make sure your theme directory is in na empty dir which will use as the "Project Root". 

Install the CLI
    
    $ gem install foundation
    $ foundation version #=> should say v1.0.3 or higher

In the "Project Root" create a file called bower.json with this content:

    {
      "name": "PROJECT_NAME",
      "dependencies": {
        "foundation": "~5.1.0"
      }
    }

In command line cd to your project root (not your theme root) & run 
    
    $ bower install


Run compass to compile locally
---------------------

When making changes, your SCSS files will be automatically compiled to css.liquid and all you config setting for the shopify admin controls will be left intact.

In command line, cd to your theme directory and run
    
    compass watch

Thats it!. 

The top of our config.rb file already has the correct import path

    add_import_path "../bower_components/foundation/scss"


If you have have been using Foundation 4 in the past, see http://foundation.zurb.com/docs/upgrading.html for documented changes.

Additional resources (Shopify)
---------------------
- <a href="http://meetup.shopify.com/">Free workshops</a>: Sign up for a free Shopify For Designers workshop in a city near you.
- <a href="http://docs.shopify.com/themes">Theme Documentation</a>: Learn more about Liquid and theme templates.
- <a href="http://apps.shopify.com/desktop-theme-editor">Desktop Theme Editor</a>: For Mac OS X users, we recommend our free app to sync theme files in development. 
- Need more help? Ask a question in our <a href="http://ecommerce.shopify.com/c/ecommerce-design"> Design Forums</a>.
