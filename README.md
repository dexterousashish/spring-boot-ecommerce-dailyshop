# JEE Project - eCommerce
####### Update: 6/11/2016

###IDE
		Spring Tool Suite (Eclipse)

###Dependencies
		Spring Boot
		Spring Security
		Spring Web Flow
		Spring Data JPA
		Spring Cloud AWS
		JavaMail
		Hibernate
		AngularJS
		Bootstrap
		JSP view layer
		MySQL-connector

###Roles
		* ROLE_UNAUTH - user registered but not yet confirm email
		* ROLE_USER - user already confirm email
		* ROLE_ADMIN - full authority to controller the whole web

###Authority
		* /admin/** - [ROLE_ADMIN] required
		* /checkout - [ROLE_USER] required
		* /customer/** - [ROLE_UNAUTH] or [ROLE_USER] required

###Link
##### Admin Page Links
		/admin/pd/m - product management page
		/admin/pd/s (?id=) - save product, (create or update)
		/admin/pd/d?id=	- delete product
		
		/admin/ca/m s (?id=) (d?id=) - category management
		/admin/hs/m s (?id=) (d?id=) - home slider management
		/admin/cu/m (d?id=) (e?id=) (ds?id=) - customer management, remove, enable, disable
##### Login,Logout,Register Links
		/login - login page
		/logout - redirect to login page
		/register - register page
		/register {user} - POST - add new user (default: 'ROLE_UNAUTH', enabled)
##### Home page Links
		/ - home page
		/version - history version information
		/contact - contact page
##### Product Page Links
		/pd/s - show all products
		/pd/s?na=, ?mc, ?st, ?sc, ?t, ?lp , ?hp 
							- name, mainCategory, sortType, subCategory, tag, lowerPrice, higherPrice
		/pd/p?id - specific item page (id required)
		/pd/p?id {productComment} - POST - add product comment - [ROLE_USER] required
##### Customer Page Links
		/customer/cart - get customer cartId, redirect to cart page
		/customer/account - customer account page
##### Shopping cart Links
		/rest - restful API
		/rest/cart - cart API (GET: return cart object)
		/rest/cart/{productId}?q= - POST - (quantity), add cartItem
		/rest/cart/{cartItemId}?q= - PUT - (quantity required) update cartItem
		/rest/cart/{cartItemId} - Delete - delete cartItem

###Function lists
##### Login/Register
		* Login/Register validate
		* Login/register page(POST) forbidden when already login
		* Password Encoder Bcrypt
		* Auto login after registering and reset password
		* Confirm Email address (Through link with Active code)
		* Retrieve password (Through link with Reset Password code)
##### Home Page
		* Home slider
##### Product Page
		* Product filter by name, mainCategory, subCategory, tag, Price(Custom), Date
		* Product sort by product price	(BackEnd Side)
		* The number of products shows	(FrontEnd Side)
##### Project Details Page
		* Product reviews section, user post reviews.
		* Related Product section
		* Quantity: disable keyboard input
##### Admin Page
		* CRUD, Validate: Product,Category,HomeSlider
		* Disable/Enable user, delete user. 
##### Shopping Cart
		* CRUD
##### Order
		* Spring WebFlow

###BUGS
		* CartItem Update Button can't handle the number of quantity over 100
		* The controller in cart page can't synchronized update with header cart Controller 
		* The function of product Tags not finished, billing not finished.
		* Need to logout and login again to change the user authority.
		
###Further Function
		* Coupon System
		* Payment System (+Billing Address)
		* Recently Views
		* Recommendation System - Hadoop