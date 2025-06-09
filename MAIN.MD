Here's your updated **stylish documentation** with your Facebook and Instagram links added to the **Developer Info** section:

---

# 🛒 Amazon Product & Keyword Research Tool

A powerful Laravel-based application for researching Amazon products and keywords using the Amazon Product Advertising API (PA-API). Built with Laravel 10 and Bootstrap 5, this tool features a clean UI and insightful keyword metrics to assist Amazon affiliates in making data-driven decisions.

---

## ✨ Features

* 🔍 **Product Research**
  Search Amazon products by keyword and view:

  * Title
  * Price
  * Rating
  * Reviews
  * Image preview

* 🔑 **Keyword Research**
  Analyze a keyword’s performance:

  * Total results
  * Average price
  * Average rating
  * List of related products

* 💻 **Responsive UI**
  Built with **Bootstrap 5** with:

  * Custom navbar and branding
  * Seamless navigation between pages

* ⚠️ **Error Handling**
  Graceful error messages for invalid credentials or no results.

* 🐛 **Debugging Logs**
  All API responses are logged in `storage/logs/laravel.log` for easy troubleshooting.

---

## 🧰 Requirements

* PHP >= 8.1
* Laravel >= 10.x
* Composer
* Amazon PA-API credentials (requires 3 qualifying sales)
* Internet connection (for API & Bootstrap CDN)

---

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/vpsrent/Amazon-Product-Research-Tool.git
cd amazon-research
```

### 2. Install Dependencies

```bash
composer install
npm install && npm run build
```

### 3. Set Up Environment

```bash
cp .env.example .env
php artisan key:generate
```

### 4. Configure API Credentials in `.env`

```env
AMAZON_ACCESS_KEY=your_access_key
AMAZON_SECRET_KEY=your_secret_key
AMAZON_ASSOCIATE_TAG=your_associate_tag
```

> Get these from: [affiliate-program.amazon.com](https://affiliate-program.amazon.com)
> *Go to: Tools → Product Advertising API → Manage Your Credentials*

---

## 🎨 Customization

### Add a Logo

* Place a logo (e.g., `amazon-logo.png`) in `public/images/`,
  **OR**
* Update Blade templates with a direct image URL:

```html
<img src="https://upload.wikimedia.org/wikipedia/commons/a/a9/Amazon_logo.svg" alt="Amazon Logo" class="navbar-logo">
```

---

## 🧪 Usage

### Run the App

```bash
php artisan serve
```

Visit: [http://localhost:8000](http://localhost:8000)

### Navigation

* 🏠 **Home/Product Research:** `/search`
* 📊 **Keyword Research:** `/keyword-research`
  Use the navbar to switch between sections.

---

## 🛠️ Troubleshooting

### 🔐 Invalid Credentials

* Check `.env` values
* Ensure your Amazon Associate account is active and eligible
* Regenerate credentials if needed

### 🕵️‍♂️ Debug Logs

```bash
tail -f storage/logs/laravel.log
```

Check for:

* `{"SearchResult":{"Items":[]}}` → No products for keyword
* `{"Errors":[{"Code":"InvalidSignature"}]}` → Wrong credentials
* `RequestThrottled` → Wait and retry (API rate limits)

### 🧪 Try These Keywords

```text
toaster, blender, coffee maker
```

---

## 🗂️ Project Structure

```
amazon-research/
├── app/Http/Controllers/
│   ├── ProductResearchController.php
│   └── KeywordResearchController.php
├── public/images/
│   └── amazon-logo.png
├── resources/views/
│   ├── search.blade.php
│   └── keyword-research.blade.php
├── routes/web.php
└── .env
```

---

## 👤 Developer Info

**👨‍💻 Developed by:** MD Amir Hossain
📧 Email: [vpsrent@gmail.com](mailto:vpsrent@gmail.com)
🌐 Websites:

* [habibsoft.com](https://habibsoft.com)
* [sbload.com](https://sbload.com)

📱 Social Media:

* 📘 [Facebook](https://www.facebook.com/vpsrentpro)
* 📸 [Instagram](https://www.instagram.com/vpsrent/)

---

## 📜 License

**MIT License** – See `LICENSE` file for details.

---

Let me know if you want this turned into a beautiful GitHub README.md file or converted into a PDF or HTML landing page!
