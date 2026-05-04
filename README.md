# 183. Customers Who Never Order

## 🟢 Problem
Find all customers who never placed an order.

### Tables

**Customers**
| Column | Type |
|--------|------|
| id     | int  |
| name   | varchar |

**Orders**
| Column     | Type |
|------------|------|
| id         | int  |
| customerId | int  |

---

## 💡 Approach

We use a **LEFT JOIN**:
- Include all customers
- Match orders if they exist
- Customers without orders will have `NULL` values
- Filter using `WHERE o.id IS NULL`

---

## ✅ SQL Solution

```sql
SELECT c.name AS Customers
FROM Customers c
LEFT JOIN Orders o
ON c.id = o.customerId
WHERE o.id IS NULL;
