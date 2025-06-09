Amazon Product & Keyword Research
A Laravel application for researching Amazon products and keywords using the Amazon Product Advertising API (PA-API). The app allows users to search for products by keyword, view product details (title, price, rating, reviews), and analyze keyword metrics (total results, average price, average rating). The UI is built with Bootstrap 5, featuring a responsive navbar with a custom logo and styling.
Features

Product Research: Search Amazon products by keyword and view details (title, price, rating, reviews, image).
Keyword Research: Analyze keywords with metrics (total results, average price, average rating) and a product list.
Responsive UI: Bootstrap 5 with a custom navbar (logo, Home, Product Research, Keyword Research links).
Error Handling: Displays user-friendly alerts for API errors or no results.
Debugging: Logs PA-API responses for troubleshooting.

Requirements

PHP >= 8.1
Laravel >= 10.x
Composer
Amazon Associates account with PA-API access (requires 3 qualifying sales)
Internet connection for Bootstrap CDN and PA-API requests

Installation

Clone the Repository
git clone https://github.com/vpsrent/Amazon-Product-Research-Tool.git
cd amazon-research


Install Dependencies
composer install
npm install && npm run build


Copy Environment File
cp .env.example .env


Generate Application Key
php artisan key:generate


Configure .envUpdate .env with your Amazon PA-API credentials:
AMAZON_ACCESS_KEY=your_access_key
AMAZON_SECRET_KEY=your_secret_key
AMAZON_ASSOCIATE_TAG=your_associate_tag


Get Credentials:
Log in to https://affiliate-program.amazon.com/.
Find your Associate Tag in the dashboard (e.g., techreviews-20 for US).
Go to Tools > Product Advertising API > Manage Your Credentials to generate Access Key ID and Secret Access Key.
Requires 3 qualifying sales within 180 days for PA-API access.




Add Logo

Place a logo (e.g., amazon-logo.png) in public/images/.
Alternatively, update search.blade.php and keyword-research.blade.php with a public logo URL:<img src="https://upload.wikimedia.org/wikipedia/commons/a/a9/Amazon_logo.svg" alt="Amazon Logo" class="navbar-logo">




Clear Cache
php artisan config:clear
php artisan cache:clear



Usage

Run the Application
php artisan serve

Visit http://localhost:8000 in your browser.

Navigate

Home/Product Research: http://localhost:8000 or /search
Enter a keyword (e.g., “toaster”) to search for products.
View product details in a responsive card grid.


Keyword Research: http://localhost:8000/keyword-research
Enter a keyword to view metrics (total results, average price, average rating) and products.


Use the navbar to switch between pages.


Check Logs

API responses are logged to storage/logs/laravel.log for debugging.
Look for PA-API Response or PA-API Keyword Research Response.



Troubleshooting
If you see Unable to fetch products: No items found for the keyword or similar errors:

Verify Credentials

Ensure .env contains valid AMAZON_ACCESS_KEY, AMAZON_SECRET_KEY, and AMAZON_ASSOCIATE_TAG.
Check https://affiliate-program.amazon.com/ for PA-API access (requires 3 sales).
Regenerate credentials if needed.


Inspect Logs

Open storage/logs/laravel.log.
Find PA-API Response or PA-API Keyword Research Response.
Common issues:
{"SearchResult":{"Items":[]}}: Keyword or SearchIndex (e.g., Kitchen) returned no results.
{"Errors":[{"Code":"InvalidSignature"}]}: Invalid credentials.
Status 401: Authentication failure.




Test Keywords/SearchIndex

Try keywords: “toaster,” “blender,” “coffee maker.”
Test SearchIndex: All, Electronics, Kitchen.
Update controllers (e.g., app/Http/Controllers/KeywordResearchController.php):'SearchIndex' => 'All',


Verify keywords on https://www.amazon.com.


Check Rate Limits

New PA-API accounts have low limits (e.g., 1 request/second).
If RequestThrottled in logs, wait 1–2 minutes.
Check Associates dashboard for limits.


Ensure PA-API Access

Log in to https://affiliate-program.amazon.com/.
Go to Tools > Product Advertising API. If missing, generate 3 sales.



Project Structure
├── app/Http/Controllers/
│   ├── ProductResearchController.php
│   ├── KeywordResearchController.php
├── public/images/
│   ├── amazon-logo.png
├── resources/views/
│   ├── search.blade.php
│   ├── keyword-research.blade.php
├── routes/web.php
├── .env

License
MIT License. See LICENSE for details.
