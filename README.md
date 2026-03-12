# Restaurant Database

- My first ever SQL project! 🤩
- A MySQL database for managing orders, sales, and employees for a small fast food restaurant🍔

## Tables 

- **customers** - Customer information
- **employees** - Employee records
- **menu** - Menu items and prices
- **orders** - Customer orders
- **order_items** - Individual items within each order
- **sales** - Sales records auto-generated from orders
- **inventory** - Stock levels
- **restock** - Restock records

## Views

### profit_summary
Returns the total sales amount across all orders.

## Features ⭐️

- **Automatic sales tracking** — when an item is added to `order_items`, a trigger automatically inserts or updates a row in `sales` with the total calculated from `order_items × menu.price`
- **Inventory management** — track stock levels and restock history per menu item

## Setup 💻

Import the individual SQL dump files into MySQL in this order:
   - `mydb_menu.sql`
   - `mydb_customers.sql`
   - `mydb_employees.sql`
   - `mydb_orders.sql`
   - `mydb_order_items.sql`
   - `mydb_sales.sql`
   - `mydb_inventory.sql`
   - `mydb_restock.sql`
   - `mydb_routines.sql`

## Requirements

- MySQL 8.0+
