# Ecommerce Website Backend
 ## Description
This project is a back end for an e-commerce website that utilizes the latest technologies. The back-end API is built using Express.js and Sequelize ORM, connected to a PostgreSQL database. The application provides CRUD (Create, Read, Update, Delete) operations for products, categories, and tags in an e-commerce platform.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Database Models](#database-models)
- [API Routes](#api-routes)
- [Technologies Used](#technologies-used)
- [Walkthrough Video](#walkthrough-video)
- [License](#license)

## Installation
1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up your PostgreSQL database and add the database credentials to a `.env` file in the root of your project:
   ```bash
   DB_NAME=ecommerce_db
   DB_USER=your_db_user
   DB_PASSWORD=your_db_password
   ```

4. Create the database schema by executing the `schema.sql` file using PostgreSQL commands:
   ```bash
   psql -U your_db_user -d your_db_name -f ./db/schema.sql
   ```

5. Seed the database (if applicable):
   ```bash
   npm run seed
   ```

## Usage
To start the server, run the following command:
```bash
npm start
```

The API will be hosted on `http://localhost:3001`.

### API Endpoints:
- **Categories**:
  - `GET /api/categories` - Get all categories.
  - `GET /api/categories/:id` - Get a single category by its `id`.
  - `POST /api/categories` - Create a new category.
  - `PUT /api/categories/:id` - Update a category by its `id`.
  - `DELETE /api/categories/:id` - Delete a category by its `id`.

- **Products**:
  - `GET /api/products` - Get all products.
  - `GET /api/products/:id` - Get a single product by its `id`.
  - `POST /api/products` - Create a new product.
  - `PUT /api/products/:id` - Update a product by its `id`.
  - `DELETE /api/products/:id` - Delete a product by its `id`.

- **Tags**:
  - `GET /api/tags` - Get all tags.
  - `GET /api/tags/:id` - Get a single tag by its `id`.
  - `POST /api/tags` - Create a new tag.
  - `PUT /api/tags/:id` - Update a tag's name by its `id`.
  - `DELETE /api/tags/:id` - Delete a tag by its `id`.

## Database Models
The database contains the following models:

- **Category**
  - `id`: Integer, primary key, auto increment.
  - `category_name`: String, non-nullable.
  
- **Product**
  - `id`: Integer, primary key, auto increment.
  - `product_name`: String, non-nullable.
  - `price`: Decimal, non-nullable.
  - `stock`: Integer, non-nullable, default value of 10.
  - `category_id`: Integer, foreign key referencing `Category`.

- **Tag**
  - `id`: Integer, primary key, auto increment.
  - `tag_name`: String.

- **ProductTag**
  - `id`: Integer, primary key, auto increment.
  - `product_id`: Integer, foreign key referencing `Product`.
  - `tag_id`: Integer, foreign key referencing `Tag`.

## Technologies Used
- Node.js
- Express.js
- PostgreSQL
- Sequelize ORM
- dotenv (for environment variables)

## Walkthrough Video
https://youtu.be/deOH4D9rt6s

## License
This project is licensed under the MIT License. See the LICENSE file for more information.
