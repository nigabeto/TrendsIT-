
-- create
CREATE TABLE products (
    id numeric PRIMARY KEY,
    name varchar(255),
    amount numeric,
    price numeric
);

-- insert
INSERT INTO products (id, name, amount, price) VALUES
(1, 'Two-doors wardrobe', 100, 800),
(2, 'Dining table', 1000, 560),
(3, 'Towel holder', 10000, 25.50),
(4, 'Computer desk', 350, 320.50),
(5, 'Chair', 3000, 210.64),
(6, 'Single bed', 750, 460);

-- fetch 
SELECT ROUND(AVG(price), 2) AS price
FROM products;
