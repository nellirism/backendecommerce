# backendecommerce Version 1.06192021
# Object-Relational Mapping (ORM) Challenge: E-commerce Back-end

The goal of this project is to *build the back end for an e-commerce site. Take a working Express.js API and configure it to use Sequelize to interact with a MySQL database.*

1. [ backendecommerce Demo. ](#demo)
2. [ User Story. ](#story)
3. [ User Acceptance Criteria. ](#uac)
4. [ Database Model. ](#mod)
5. [ Association. ](#ass)
6. [ Special Instructions. ](#how)

<a name="demo"></a>

# *backendecommerce* Demo

Walkthrough Videos:

1. Create the schema from the MYSQL shell. 

https://user-images.githubusercontent.com/71202250/122661818-3bba2100-d143-11eb-851c-e4578e51d1a0.mp4

2. Seed the database from the command line.

https://user-images.githubusercontent.com/71202250/122661811-23e29d00-d143-11eb-93b7-4ab57783701f.mp4

3. Start the Application's server. 

https://user-images.githubusercontent.com/71202250/122661889-bdaa4a00-d143-11eb-8414-3015d3e81cff.mp4

4. GET routes for all categories, all products, and all tags being tested in Insomnia Core.

https://user-images.githubusercontent.com/71202250/122661115-e2022880-d13b-11eb-87a5-896bee27d491.mp4

5. GET routes for a single category, a single product, and a single tag being tested in Insomnia Core.

https://user-images.githubusercontent.com/71202250/122661241-f85cb400-d13c-11eb-9d0f-d2973ba1e9d9.mp4

6. POST, PUT, and DELETE routes for categories, products, and tags being tested in Insomnia Core.

https://user-images.githubusercontent.com/71202250/122661387-8e450e80-d13e-11eb-89c4-dfdc5830bcdf.mp4


https://user-images.githubusercontent.com/71202250/122662189-dd427200-d145-11eb-95fb-9257999aa5fe.mp4


https://user-images.githubusercontent.com/71202250/122662281-8c7f4900-d146-11eb-8cfd-25156707a248.mp4

<a name="story"></a>
## User Story

AS A manager at an internet retail company
I WANT a back end for my e-commerce website that uses the latest technologies
SO THAT my company can compete with other e-commerce companies

<a name="uac"></a>
## Acceptance Criteria

GIVEN a functional Express.js API

WHEN I add my database name, MySQL username, and MySQL password to an environment variable file
THEN I am able to connect to a database using Sequelize

WHEN I enter schema and seed commands
THEN a development database is created and is seeded with test data

WHEN I enter the command to invoke the application
THEN my server is started and the Sequelize models are synced to the MySQL database

WHEN I open API GET routes in Insomnia Core for categories, products, or tags
THEN the data for each of these routes is displayed in a formatted JSON

WHEN I test API POST, PUT, and DELETE routes in Insomnia Core
THEN I am able to successfully create, update, and delete data in my database

<a name="mod"></a>
## Database Models

- `Category`

    - `id`
        - Integer
        - Doesn't allow null values
        - Set as primary key
        - Uses auto increment

    - `category_name`
        - String
        - Doesn't allow null values

- `Product`

    - `id`
        - Integer
        - Doesn't allow null values
        - Set as primary key
        - Uses auto increment

    - `product_name`
        - String
        - Doesn't allow null values

    - `price`
        - Decimal
        - Doesn't allow null values
        - Validates that the value is a decimal

    - `stock`
        - Integer
        - Doesn't allow null values
        - Set a default value of 10
        - Validates that the value is numeric

    - `category_id`
        - Integer
        - References the category model's id

- `Tag`

    - `id`
        - Integer
        - Doesn't allow null values
        - Set as primary key
        - Uses auto increment

    - `tag_name`
        - String

- `ProductTag`

    - `id`
        - Integer
        - Doesn't allow null values
        - Set as primary key
        - Uses auto increment

    - `product_id`
        - Integer
        - References the product model's id

    - `tag_id`
        - Integer
        - References the tag model's id

<a name="ass"></a>
## Associations

*Execute association methods on your Sequelize models to create the following relationships between them:*

- Product belongs to Category, as a category can have multiple products but a product can only belong to one category.

- Category has many Product models.

- Product belongs to many Tag models. Using the ProductTag through model, allow products to have multiple tags and tags to have many products.

- Tag belongs to many Product models.

<a name="how"></a>
## Special Instructions

- Add a .env file to the root of the app with the following details

```text
DB_NAME='ecomm_db'
DB_USER='xxx'
DB_PW='xxx'
```
