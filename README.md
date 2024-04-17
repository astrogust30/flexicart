# Introduction

Flexicart: your mini BAGisto  is an opensource framework built on some of the hottest technologies such as [Laravel](https://laravel.com/) (a [PHP](https://secure.php.net/) framework) and [Vue.js](https://vuejs.org/) a progressive Javascript framework.

It can help you cut down your time, cost, and workforce for building online stores or migrating from physical stores to the ever-demanding online world. Your business—whether small or huge—can benefit. The best part, it's straightforward to set it up!

Built on technologies such as PHP, Laravel, Vue.js and Tailwind CSS.

### We aim to target e-commerce businesses so it provides front and back end features to enable customer account and administrative control simultaneously.


![image](https://github.com/astrogust30/flexicart/assets/158575442/8ab85bd3-8c5a-4b4f-b2cd-dd42d6024433)

Image Source : excellentwebworld

Our project aims to be eCommerce Framework that offers Multi-Warehouse Inventory.

# Prerequisites

OS: Ubuntu 16.04 LTS or Higher / Windows 7 or Higher (WAMP / XAMPP).
Server: Apache 2 or NGINX
RAM: 4 GB or higher.
PHP: 7.4 or higher.
Processor: Clock Cycle 1Ghz or higher.
For MariaDB users – 10.2.7 or Higher.
MySQL: 5.7.23 or higher.
Node: 8.11.3 LTS or higher.
Composer: 1.6.5 or higher.

# Steps to Configure

### Navigate into the cloned directory and install the required dependencies using Composer:

 _ composer install_

### Open the .env file and fill in the necessary details. For example, you need to provide values for_ DB_DATABASE, DB_USERNAME, DB_PASSWORD, and APP_KEY._

### Generate Application Key: Generate the application key by running the following command:

_php artisan key:generate_

### Run the database migrations to create the necessary tables in your database:

_php artisan migrate_

### Seed the Database (Optional): If you want to populate the database with sample data, you can run the database seeder:

_php artisan db:seed_

### Start the Development Server: Once everything is set up, you can start the development server to run locally:

_php artisan serve_

**Open your web browser and navigate to http://localhost:8000 to access application running on your local server.**
_
_Configure your HTTP server to point to the public/ directory of the project.
_
_Run the following command:_ _php artisan serve_
_Open your browser and access the provided local server URL.__

## Login as an Admin
To log in as an admin, visit https://_localhost_/admin/. Intially after data seeding,  use the following credentials:

Email: khushiadmin@gmail.com
Password: root123

Or change 

![image](https://github.com/astrogust30/flexicart/assets/158575442/34eff85d-2f81-4ede-8818-e1005d05e582)


## Login as a Customer

To log in as a customer, you can directly register on https://_localhost_/customer/register. 

After registration, you can log in using your credentials on the domain.

# Architecture

Laravel packages are being used to separate each functionality such as Category, Product, Cart, Checkout, etc.

![image](https://github.com/astrogust30/flexicart/assets/158575442/5bfe283a-c9a3-497c-be01-65abe669a956)

## We developed and used built-in components of Vue.js

### Blade templates are used for server-side rendering of HTML content, while Vue.js components are used for client-side interactivity and dynamic rendering.

![image](https://github.com/astrogust30/flexicart/assets/158575442/c6bb2df3-d251-4564-ba09-9bee443d62c2)

### It registers useful events that are triggered on most of the pages which could enable to perform some custom operations in the application.

![image](https://github.com/astrogust30/flexicart/assets/158575442/99a5dcc5-814a-4762-915a-da81033ab4ba)
to control access to various resources and functionalities within an application based on user roles and permissions. 

![image](https://github.com/astrogust30/flexicart/assets/158575442/2c1a6094-21cb-4712-9c55-ed78932adfa5)
registers the EventServiceProvider class so that event listeners defined within it can be utilized in the application.

# Packages
Laravel packages are the primary way of adding functionality so the following features are distributed into packages to enhance the application and allow developers to follow the standard way of developing custom functionality.

Theme
Category
Product
Cart
Checkout
Payment

Service provider enables features such as loading routes, migrations, languages or publishing views, etc.

# Vue and Tailwind
Vue.js and Tailwind CSS handles the complete UI of Bagisto.

Vite is a tool that offers a fast and efficient development environment for building modern web applications. 
It replaces Laravel Mix, which was used for defining webpack and building steps in your Laravel application using various CSS and JavaScript pre-processors .

We are using Vue.js and Vite , vite compiles all of CSS and JavaScript assets that are placed into public directory.

In vite.config.js file, just define your Vue.js and path of build directory, Vite will be responsible to compile all the assets on defined location.

![image](https://github.com/astrogust30/flexicart/assets/158575442/f7688667-b515-4312-a84e-0e03e210d898)

In tailwind.config.js file, just define your blade file path along with .js file directory, Tailwind CSS will be responsible to compile all the css defined on the location

![image](https://github.com/astrogust30/flexicart/assets/158575442/a22794f7-5491-443c-a423-d5a6391ceecc)

# Webkul

Contracts: They are defining an interface for a Post model in their blog module. Contracts in Laravel are interfaces that define the core services provided by the framework or a package.

Model Proxies: They are creating a model proxy class PostProxy that extends Konekt\Concord\Proxies\ModelProxy. This is used for model inheritance without creating a new table in the database.

Models: They are defining a Post model that implements the Post contract. This model represents a blog post and is likely used to interact with the database table storing blog posts.

Module Service Provider: They are creating a service provider ModuleServiceProvider that extends BaseModuleServiceProvider. In this service provider, they are registering the Post model for their blog module.

# Creating a New Theme

To create a new theme, follow these steps:

Add a new theme entry to the themes array in the themes.php file:

![image](https://github.com/astrogust30/flexicart/assets/158575442/750a4f90-499e-42ae-a1be-dcfbb74b819e)

 'shop2' => [
            'name'        => 'Theme1',
            'assets_path' => 'public/themes/shop/theme1',
            'views_path'  => 'resources/themes/theme1/views',

            'vite'        => [
                'hot_file'                 => 'shop-theme1-vite.hot',
                'build_directory'          => 'themes/shop/theme1/build',
                'package_assets_directory' => 'src/Resources/assets',
            ],
        ],
Explanation of Parameters:

default: This parameter at the top of the file indicates the currently active or default theme . It is set to 'default', representing the name of the currently active theme.

themes: This parameter allows you to define the configurations for your custom themes. You can create and use multiple themes simultaneously.

Inside the 'themes' array, there is another array named 'default', which represents your currently active theme. It contains several key-value pairs that are explained below:

  _views_path: This parameter specifies the path to the views or blade files for your custom theme.

  assets_path: It determines the path to the assets such as images, CSS files, and JavaScript files for your theme.

  name: This parameter defines a global name for your theme.

  parent: This is an optional parameter that allows you to customize existing themes. By setting the 'parent' parameter to the value of the 'name' parameter listed above, you can inherit the configuration of the parent theme and make further customizations._
  
Once you have defined the paths and names for your custom theme in the themes.php file, you can start creating your view files.
Make sure to cover all the GET routes of the shop package that include a parameter called 'view'. 
You can find the route file of the shop package located at packages/Webkul/Shop/src/Http/routes.php.

Ensure that the name of your blade file matches the value passed in the GET route file. For example:

// Store front header nav-menu fetch
Route::get('/categories/{slug}', 'Webkul\Shop\Http\Controllers\CategoryController@index')
    ->name('shop.categories.index');
    
In this example, the view file should be named index.blade.php and placed in the appropriate directory within your custom theme.

![image](https://github.com/astrogust30/flexicart/assets/158575442/2fb149bd-489c-4195-83cf-350e001432e1)


For all the views, check all the GET routes as they include a 'view' parameter with the corresponding value to be used.


# Creating a New Admin Theme

Add a new theme entry to the admin-themes array in the themes.php file:

![image](https://github.com/astrogust30/flexicart/assets/158575442/21d78b40-c23a-43f7-a71c-8b77cdd7d601)


# Package Development 
Laravel includes Eloquent, an object-relational mapper (ORM) that makes it enjoyable to interact with your database. When using Eloquent, each database table has a corresponding "Model" that is used to interact with that table.
In addition to retrieving records from the database table, Eloquent models allow you to insert, update, and delete records from the table as well.

![image](https://github.com/astrogust30/flexicart/assets/158575442/2ba01c3f-af31-47f0-88b5-65d9230d16ea)
