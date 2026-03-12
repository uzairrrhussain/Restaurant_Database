# Restaurant Database

My first ever SQL project! 🤩
A MySQL database for managing orders, sales, and employees for a small fast food restaurant🍔

## Tables 

### customers
| Column | Type | Description |
|--------|------|-------------|
| customer_id | int | Primary key |
| customer_name | varchar(100) | Full name |
| phone | varchar(20) | Phone number |
| email | varchar(100) | Email address |

### employees
| Column | Type | Description |
|--------|------|-------------|
| employee_id | int | Primary key |
| employee_name | varchar(100) | Full name |
| role | varchar(50) | Job role |
| hire_date | date | Date hired |
| wage | decimal(8,2) | Monthly wage |

### menu
| Column | Type | Description |
|--------|------|-------------|
| item_id | int | Primary key |
| item_name | varchar(100) | Name of item |
| price | decimal(6,2) | Item price |
| category | varchar(50) | e.g. Fast Food, Side, Drink, Dessert |
| available | tinyint(1) | 1 = available, 0 = unavailable |

### orders
| Column | Type | Description |
|--------|------|-------------|
| order_id | int | Primary key |
| customer_id | int | Foreign key → customers |
| employee_id | int | Foreign key → employees |
| order_time | datetime | When the order was placed |

### order_items
| Column | Type | Description |
|--------|------|-------------|
| order_item_id | int | Primary key |
| order_id | int | Foreign key → orders |
| item_id | int | Foreign key → menu |
| quantity | int | Number of items ordered |

### sales
| Column | Type | Description |
|--------|------|-------------|
| sale_id | int | Primary key (auto increment) |
| order_id | int | Foreign key → orders |
| total_amount | decimal(8,2) | Auto-calculated total |
| payment_method | varchar(20) | Payment method |
| sale_time | datetime | Time of sale |

### inventory
| Column | Type | Description |
|--------|------|-------------|
| item_id | int | Primary key, Foreign key → menu |
| quantity_available | int | Current stock level |

### restock
| Column | Type | Description |
|--------|------|-------------|
| restock_id | int | Primary key |
| item_id | int | Foreign key → inventory |
| quantity_added | int | Amount restocked |
| restock_time | datetime | When restock occurred |

## Features ⭐️

- Automatic sales tracking via trigger — when an order item is added, the `sales` table is updated automatically with the total calculated from `order_items × menu.price`
- `profit_summary` view for a quick snapshot of total sales

## Setup 💻

1. Import the SQL dump files into MySQL
2. Or run `mydb.sql` to recreate the schema from scratch

## Requirements

- MySQL 8.0+
