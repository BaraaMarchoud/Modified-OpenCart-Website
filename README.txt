This repository contains my implementation of the required OpenCart admin modifications based on the provided assessment tasks.

Environment Details:
   PHP version: 5.4.7
   XAMPP version: 1.8.1
   OS: Windows

After downloading the repository as ZIP, OpenCart absolute paths may break.

Setup Instructions

   Please update the following files to match your local directory:
     - config.php
     - admin/config.php


Update all DIR_* constants to point to your local OpenCart folder.

Task 1 — Product Page Modifications (Admin → Catalog → Products)
   Modified Files:
	Admin -> Controller -> Catalog -> product.php
	Admin -> Model -> Catalog -> product.php && category.php
	Admin -> View -> Template -> Catalog -> product_list.tpl && product_form.tpl

   Brief Description:
	Added a Cost field to products and calculated Profit dynamically (Price − Cost) without storing it in the 	database.
	Both Cost and Profit support inequality filtering and sorting in the product list.

	Enhanced category assignment logic so when a product is assigned to a category, it is automatically assigned to 	all parent categories recursively.
	Displayed product categories using full category paths with filtering and sorting support.

   Challenges Faced:
	As a first time working with an OpenCart project, at the beginning I have faced some difficulties to understand 	the database and code structure for it.
	Ensuring dropdown category data loads and filter is passed correctly to URL/query.
 

TASK 2 — CATEGORY PAGE MODIFICATIONS (ADMIN)
   Modified Files: 
	Admin -> Controller -> Catalog -> category.php
	Admin -> Model -> Catalog -> category.php
	Admin -> View -> Template -> Catalog -> category_list.tpl

   Brief Description:
	For this task I have added a new column which is Product count which count for each category how many product 	assigned to it, support sorting and filtering. Also added parent category column which display the parent category 	for each one.

   Challenges Faced: 
	Filtering required HAVING logic because count is aggregated.
	Building correct full parent path format.

TASK 3 — ORDER PAGE MODIFICATION (ADMIN) 
   Modified Files: 
	Admin -> Controller -> Sale -> order.php
	Admin -> Model -> Sale -> order.php
	Admin -> View -> Template -> Sale -> sale_list.tpl

   Brief Description:
	This task was about to add a new action button which is view product, Products are loaded dynamically via AJAX and 	displayed in a modal using OpenCart’s jQuery UI dialog.

   Challenges Faced:
	Making sure the AJAX route returns correct JSON format.
	Ensuring the modal displays using OpenCart’s included jQuery UI setup.

How to Run:
Place this folder inside XAMPP -> htdocs
Import the provided database into phpMyAdmin
Admin Login:
   URL: http://localhost/Modified-OpenCart-Website-main/admin
   Username: admin
   Password: Baraa123$$
	

