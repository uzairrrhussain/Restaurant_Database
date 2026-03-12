# Restaurant Database

My first ever SQL project! 🤩
A MySQL database for managing orders, sales, and employees for a small fast food restaurant🍔

## Tables 

- **customers** - Customer information
- **employees** - Employee records
- **menu** - Menu items and prices
- **orders** - Customer orders
- **order_items** - Individual items within each order
- **sales** - Sales records auto-generated from orders
- **inventory** - Stock levels
- **restock** - Restock records

## Features ⭐️

- Automatic sales tracking via trigger — when an order item is added, the `sales` table is updated automatically with the total calculated from `order_items × menu.price`
- `profit_summary` view for a quick snapshot of total sales

## Setup 💻

1. Import the SQL dump files into MySQL
2. Or run `mydb.sql` to recreate the schema from scratch

## Requirements

- MySQL 8.0+
