# Ecommerce

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 13.3.3.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.

# Java + Angular Exit Test 2 - Product Catalogue

## Description

This project consists of two applications: a backend REST API built with Spring Boot and a frontend application developed using Angular 11. The purpose of this project is to create a product catalogue system with user authentication, registration, product search, and product details functionality.

### Backend (REST API - Spring Boot)

The backend application focuses on providing the necessary APIs to support user authentication, user registration, and product-related operations.

#### User Authentication API

- Endpoint: `/authentication`
- Method: POST
- Description: This API validates user credentials for successful authentication.

#### User Login API

- Endpoint: `/authentication/login`
- Method: POST
- Description: This API validates user credentials for successful authentication.

#### User Registration API

- Endpoint: `/authentication/registerUser`
- Method: POST
- Description: This API allows users to register and create a new account.

#### To get User LoggedIn API

- Endpoint: `/authentication/LoggedInUser`
- Method: GET
- Description: This API validates user credentials for successful authentication.

#### Search Product API

- Endpoint: `/products`
- Method: GET
- Description: This API enables users to search for products based on name, product code, or brand.

#### Product Details API (for id)

- Endpoint: `/products/id/{Id}`  
- Method: GET
- Description: This API retrieves detailed information about a specific product.

#### Product Details API (for pincode)

- Endpoint: `/products/code/{code}`  
- Method: GET
- Description: This API retrieves detailed information about a specific product.

#### Product Details API (for name)

- Endpoint: `/products/name/{name}`  
- Method: GET
- Description: This API retrieves detailed information about a specific product.

#### Product Details API (for brand)

- Endpoint: `/products/brand/{brand}`  
- Method: GET
- Description: This API retrieves detailed information about a specific product.

#### Product Details API (for price)

- Endpoint: `/products/price/{price}`  
- Method: GET
- Description: This API retrieves detailed information about a specific product.




#### Get Serviceability API

- Endpoint: `/serviceability/{id}/{code}`
- Method: GET
- Description: This API checks if a product is serviceable or deliverable to a specific pincode and provides the expected delivery time.

### Frontend (Angular)

The frontend application is built using Angular 11 and provides a user-friendly interface for interacting with the product catalogue system.

#### Homepage

- URL: ``
- Description: The landing page contains links for user registration and login. It also features a search box where customers can search for products.

#### Login Page

- URL: `/login`
- Description: This page allows users to log in to the application. Proper error messages are displayed in case of invalid authentication.

#### Registration Page

- URL: `/registration`
- Description: This page enables users to register and create a new account. It includes validation for email address, password policy, and mandatory fields.

#### Product Search Page

- URL: `/search`
- Description: The search screen allows users to search for products by specifying various parameters. The results are obtained using the backend API mentioned above.


#### Product Details Page

- URL: `/productDetails/{id}`
- Description: This page shows detailed information about a specific product, including images, name, description, brand, and price. Logged-in users can enter their pincode to check serviceability and receive information on whether the product can be delivered and the expected delivery time.

#### Logout

- URL: `/logout`
- Description: This option allows users to log out of the application.

#### Important Thing to know


## for serviceability entity
 * Here, ID & Pid should have same value Then only Serviceability api will work 
 * for example, suppose for product 1 we have to insert manually data into table in database
 * then: 
 *  Id  pincodes  pid  estimateddays
 *  1   211010     1      4 
 *  if user search availability for product 1 then he/she will get 4 days as estimateddays
 *  suppose another example,suppose for product 2 we have to insert manually data into table in database
 * then: 
 *  
 *   Id  pincodes  pid  estimateddays
 *  2  211010       1    4 
 *  in this 2 example, Id is 2 and pid is 1 both are different so it will show not available
 *  for serviceability to work fine it should be Id and Pid should have same value
 *  

## for product & users entity
 * we have to insert manually data into tables.

 ## dummy database :
 * create database ecommerce2; (application.properties )
 * use ecommerce2;
 ## product table in ecommerce2 database:
* create table products(ID int primary key, Name varchar(255),brand varchar(255), description varchar(255),code * varchar(255),image longblob,price double );
* id name brand description  code  image                  price         
* 1	car	 abc	this is car	 123 (upload image by right click and select image by clicking load values by files)	12455

## users table in ecommerce2 database:
* create table users( id int primary key,email varchar(255) , username varchar(255),fullname varchar(255),password varchar(255));
* insert into users values(1,'lakshmi@23oct','lakshmi','lakshmisabharwal','lakshmi');

## serviceability table in ecommerce2 database:	
* create table serviceability(ID  int, pincodes int ,pid int, estimateddays int);
* insert into serviceability values(3,221133,3,8);
* select * from serviceability;
		