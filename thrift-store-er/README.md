# Thrift Store - ER Diagram

ER diagram for an Instagram-based thrift and handmade products store.

---

## Link
```
https://ishan-parnami.github.io/DB-ER/thrift-store-er/index.html
```
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