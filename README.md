# 🛍️ Salesforce E-Commerce Order Tracking System

### 📌 Overview
A Salesforce project to track **orders, payments, and delivery statuses** for e-commerce businesses.  
This system helps monitor customer orders, assign delivery agents, calculate total sales, and automate email notifications when an order is shipped.

---

## 🚀 Features Implemented
✔ Custom Object – `Order__c`  
✔ Track Order Status (`Pending / Shipped / Delivered / Cancelled`)  
✔ Track Payment Status (`Paid / Not Paid`)  
✔ Assign Delivery Agent (Lookup to User)  
✔ Dashboard for Order Summary  
✔ Sales Report with Total Amount  
✔ **Automation** – Email when status = *Shipped*  
✔ Validation Rules (optional)

---

## 🧱 Salesforce Object & Fields

### Custom Object: `Order__c`

| Field Name | Type | Description |
|------------|------|-------------|
| Customer_Name__c | Text | Name of customer |
| Product_Name__c | Text | Product ordered |
| Quantity__c | Number | Number of items |
| Amount__c | Currency | Total price |
| Payment_Status__c | Picklist | Paid / Not Paid |
| Order_Status__c | Picklist | Pending / Shipped / Delivered / Cancelled |
| Order_Date__c | Date | Order placed on |
| Delivery_Agent__c | Lookup(User) | Assigned delivery agent |

---

## 📊 Dashboard Components
| Component | Purpose |
|-----------|---------|
| Bar Chart | Order status distribution |
| Donut Chart | Payment status statistics |
| Metric | Total sales (SUM of Amount__c) |

---

## 🧠 Automation (Flow)
**Trigger:** When `Order_Status__c = 'Shipped'`  
**Action:** Send email to customer + delivery agent  
Used: **Record-Triggered Flow**

---

## 📁 Sample CSV Data
`salesforce-ecommerce-order-tracking-system/sample_orders.csv`

```csv
Customer_Name,Product_Name,Quantity,Amount,Payment_Status,Order_Status,Order_Date
Rahul Sharma,Wireless Earbuds,2,4200,Paid,Shipped,2025-01-15
Sneha Patel,Smartwatch,1,6500,Not Paid,Pending,2025-01-16
Amit Verma,Laptop Stand,1,1200,Paid,Delivered,2025-01-17
