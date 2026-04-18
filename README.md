## Bookstore Web Application
This is a lightweight, PHP-based e-commerce platform for a bookstore. It allows users to browse a collection of books, manage a shopping cart, and complete a checkout process. The system supports both guest checkouts and registered user accounts with profile management.

## Features
User Authentication: Full registration and login system for customers.

Product Catalog: Dynamic book display pulled directly from a MySQL database, including titles, authors, ISBNs, and pricing.

Shopping Cart:

Add books to a cart with specified quantities.

Real-time "mini-cart" view on the main page.

Option to empty the cart at any time.

Checkout System:

Registered Users: Automatic retrieval of profile information for a faster checkout.

Guest Users: A manual form to capture shipping and contact details.

Profile Management: Registered users can update their personal information, username, and passwords.

## Project Structure

| File | Description |
| :--- | :--- |
| **index.php** | The main landing page; handles product display and the shopping cart. |
| **login.php / checklogin.php** | Handles user authentication and session initiation. |
| **register.php** | Facilitates new user account and customer profile creation. |
| **checkout.php** | Processes the final order, updates the database, and displays order summaries. |
| **edituser.php** | Allows authenticated users to modify their profile data. |
| **connectDB.php** | Centralized PDO database connection configuration. |
| **database.sql** | The SQL schema to initialize the BookStore database and sample data. |
| **style.css** | Global styling and layout for the application. |

## Database Schema
The application utilizes a relational database named BookStore with the following tables:

Book: Stores book metadata (Title, ISBN, Price, Author, Image path).

Users: Stores login credentials (Username, Password).

Customer: Stores detailed personal information linked to a User ID.

Cart: Temporary storage for items selected by the user.

Order: Records successful transactions, linking customers to specific books.

## Installation & Setup
Environment: Ensure you have a local server environment installed (e.g., XAMPP, WAMP, or MAMP).

Database Initialization:

Open PHPMyAdmin or your preferred MySQL client.

Import the contents of database.sql to create the database and populate the initial book list.

Configuration:

Verify the database credentials in connectDB.php. By default, it is set to root with no password.

Check individual files (like index.php and checkout.php) if your MySQL port differs from the default 3306.

Deployment:

Place the project folder in your server's root directory (e.g., htdocs/BOOK-STORE/).

Access the application via http://localhost/BOOK-STORE/index.php.

## Security Note
Warning: This application uses plain-text passwords and basic mysqli queries in several files. For a production environment, it is highly recommended to implement password hashing (e.g., password_hash()) and transition all queries to prepared statements to prevent SQL injection.
