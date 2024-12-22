# Category-Product Management System

This project is a Spring Boot application designed to manage categories and products with CRUD operations. It uses RESTful APIs, JPA, and Hibernate for database interactions. The application includes pagination and showcases a one-to-many relationship between categories and products.

---

## Features
- **Category Management**: Create, read, update, and delete categories.
- **Product Management**: Create, read, update, and delete products.
- **One-to-Many Relationship**: A category can have multiple products.
- **Server-Side Pagination**: Paginated results for categories and products.
- **Detailed Product View**: Fetch a single product with its associated category details.

---

## DB Design

### Tables

#### 1. **Category Table**
   - **Table Name**: `categories`
   - **Columns**:
     | Column Name    | Data Type    | Constraints                     |
     |----------------|--------------|----------------------------------|
     | `id`           | BIGINT       | PRIMARY KEY, AUTO_INCREMENT     |
     | `name`         | VARCHAR(255) | NOT NULL                        |
     | `description`  | TEXT         | NULLABLE                        |

#### 2. **Product Table**
   - **Table Name**: `products`
   - **Columns**:
     | Column Name    | Data Type     | Constraints                     |
     |----------------|---------------|----------------------------------|
     | `id`           | BIGINT        | PRIMARY KEY, AUTO_INCREMENT     |
     | `name`         | VARCHAR(255)  | NOT NULL                        |
     | `price`        | DECIMAL(10,2) | NOT NULL                        |
     | `category_id`  | BIGINT        | FOREIGN KEY REFERENCES `categories(id)` |

---

## APIs

### Category APIs
1. **GET All Categories**  
   `GET http://localhost:8080/api/categories?page={page_number}`

2. **Create a New Category**  
   `POST http://localhost:8080/api/categories`  
   - Request Body (JSON):  
     ```json
     {
       "name": "Category Name",
       "description": "Category Description"
     }
     ```

3. **Get Category by ID**  
   `GET http://localhost:8080/api/categories/{id}`

4. **Update Category by ID**  
   `PUT http://localhost:8080/api/categories/{id}`  
   - Request Body (JSON):  
     ```json
     {
       "name": "Updated Name",
       "description": "Updated Description"
     }
     ```

5. **Delete Category by ID**  
   `DELETE http://localhost:8080/api/categories/{id}`

---

### Product APIs
1. **GET All Products**  
   `GET http://localhost:8080/api/products?page={page_number}`

2. **Create a New Product**  
   `POST http://localhost:8080/api/products`  
   - Request Body (JSON):  
     ```json
     {
       "name": "Product Name",
       "price": 100.0,
       "categoryId": 1
     }
     ```

3. **Get Product by ID**  
   `GET http://localhost:8080/api/products/{id}`

4. **Update Product by ID**  
   `PUT http://localhost:8080/api/products/{id}`  
   - Request Body (JSON):  
     ```json
     {
       "name": "Updated Product Name",
       "price": 120.0,
       "categoryId": 1
     }
     ```

5. **Delete Product by ID**  
   `DELETE http://localhost:8080/api/products/{id}`

---

## Let's Run the Project

### Prerequisites
1. Install **Java 17** or later.
2. Install **Maven**.
3. Install and configure an **RDBMS** (e.g., MySQL, PostgreSQL).
4. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_name>
