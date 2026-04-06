# Thrift Store - ER Diagram

ER diagram for an Instagram-based thrift and handmade products store.

---

## What this covers

- Products (thrifted and handmade, handled separately)
- Customer info and order history
- Order items, payment status, and shipping status

---

## Entities

| Entity | Purpose |
|---|---|
| Customer | Stores buyer details |
| Product | All products being sold |
| ThriftedDetail | Extra info for thrifted items (condition, availability) |
| HandmadeDetail | Extra info for handmade items (stock, made-to-order) |
| Order | An order placed by a customer |
| OrderItem | Junction table linking orders and products |
| Payment | Payment status of each order |
| Shipping | Shipping and delivery status |

---

## Key Relationships

- Customer → Order : one to many
- Order → OrderItem : one to many
- Product → OrderItem : one to many
- Order → Payment : one to one
- Order → Shipping : one to one
- Product → ThriftedDetail : one to one
- Product → HandmadeDetail : one to one

---

## Files

- `er-diagram.eraser` or `er-diagram.png` — the actual diagram

---

## Notes for future use

- When building the DB, use `product_type` field in Product to know whether to join ThriftedDetail or HandmadeDetail
- OrderItem is the junction table for the many-to-many between Order and Product
- Payment and Shipping are separate tables, both linked to Order via `order_id`
- All PKs are named as `entity_id` (e.g. `customer_id`, `order_id`)