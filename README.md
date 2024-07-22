# Farm Connect

Farm Connect is a web application designed to facilitate the posting and browsing of agricultural products. Users can register, log in, and post their products with details such as name, description, price, and images. This README provides an overview of the application, setup instructions, and usage guidelines.

## Features

- User authentication (login/register).
- Product posting with name, description, price, and image.
- Dynamic display of available products.
- Contact seller and delete product functionalities.
- Client-side form validation and error handling.
- Product loading and error indicators.

## Technologies Used

- HTML, CSS, JavaScript for front-end.
- PHP for back-end.
- Local Storage for temporary data storage.
- JSON for data interchange.

## Setup Instructions

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/your-username/farm-connect.git
   cd farm-connect
   ```

2. **Set Up the Database:**

   Create a MySQL database and import the required tables. Example SQL to create a `products` table:

   ```sql
   CREATE TABLE products (
       id INT AUTO_INCREMENT PRIMARY KEY,
       name VARCHAR(255) NOT NULL,
       description TEXT NOT NULL,
       price DECIMAL(10, 2) NOT NULL,
       image VARCHAR(255) NOT NULL
   );
   ```

3. **Configure the Back-End:**

   Modify the database configuration in `post_product.php` and `get_products.php` to connect to your MySQL database.

   ```php
   // Example: db_config.php
   $host = 'localhost';
   $db = 'farm_connect';
   $user = 'root';
   $pass = 'password';

   $dsn = "mysql:host=$host;dbname=$db;charset=utf8mb4";
   $options = [
       PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
       PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
   ];
   ```

4. **Start the PHP Server:**

   ```bash
   php -S localhost:8000
   ```

   Open your web browser and navigate to `http://localhost:8000`.

## File Structure

- `index.php`: The main entry point of the application.
- `home.php`, `products.php`, `purchases.php`, `about.php`: Static pages for navigation.
- `post_product.php`: Handles product posting to the database.
- `get_products.php`: Retrieves products from the database.
- `delete_product.php`: Deletes a product from the database.
- `login.php`, `register.php`, `logout.php`: Handles user authentication.
- `db_config.php`: Database configuration (not included, create based on your setup).

## Usage

1. **User Registration and Login:**

   - Navigate to the `Register` page to create a new account.
   - Log in with your credentials.

2. **Post a Product:**

   - Fill out the form with the product name, description, price, and image.
   - Submit the form to post the product.

3. **View Available Products:**

   - Browse the list of products dynamically displayed on the `Products` page.

4. **Contact Seller and Delete Product:**

   - Use the `Contact Seller` button to initiate contact (implementation required).
   - Use the `Delete` button to remove a product from the database.

## Scripts

- **JavaScript:**

  - `postProduct()`: Handles product posting and updates the product list dynamically.
  - `fetchProducts()`: Fetches and displays products from the database.
  - `addProductToList(product, isNew)`: Adds a product to the product list.
  - `updateProductStatus(id, statusText)`: Updates the status of a product.
  - `deleteProduct(id, productElement)`: Deletes a product from the database and the view.

## License

This project is licensed under the MIT License.

## Acknowledgements

- Icons by [FontAwesome](https://fontawesome.com/).
- Design inspired by modern web applications.

---

Feel free to modify and extend this project as needed. If you encounter any issues, please open an issue on the GitHub repository or contact the project maintainers.
