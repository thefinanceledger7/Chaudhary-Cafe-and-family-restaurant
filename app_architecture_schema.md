# Technical Architecture: Chaudhary Cafe & Family Restaurant

## 1. Tech Stack Recommendation
- **Frontend:** Flutter (for high-performance cross-platform Android/iOS)
- **Backend:** Node.js with Express.js
- **Database:** MongoDB (for flexible menu and order schemas)
- **Real-time:** Socket.io (for live order tracking)
- **Authentication:** Firebase Auth (OTP/Google/Email)
- **Storage:** Cloudinary or AWS S3 (for high-quality food images)

## 2. Database Schema (MongoDB)

### Users Collection
```json
{
  "_id": "uuid",
  "name": "string",
  "phone": "string",
  "email": "string",
  "address": [{ "type": "Home/Work", "details": "string" }],
  "favorites": ["food_id"]
}
```

### Menu Collection
```json
{
  "_id": "uuid",
  "name": "string",
  "description": "string",
  "price": "number",
  "category": "Veg/Non-Veg/Snacks/Lunch/Dinner/Beverages",
  "image_url": "string",
  "is_available": "boolean",
  "rating": "number"
}
```

### Orders Collection
```json
{
  "_id": "uuid",
  "user_id": "uuid",
  "items": [{ "food_id": "uuid", "quantity": "number", "price": "number" }],
  "total_amount": "number",
  "status": "Received/Preparing/Cooking/Out for Delivery/Delivered",
  "payment_method": "COD/Online",
  "delivery_address": "string",
  "timestamp": "ISO Date"
}
```

### Table Bookings Collection
```json
{
  "_id": "uuid",
  "user_id": "uuid",
  "date": "string",
  "time": "string",
  "guests": "number",
  "status": "Pending/Confirmed/Cancelled"
}
```

## 3. Key API Endpoints

### User & Auth
- `POST /api/auth/login` (OTP Verification)
- `GET /api/user/profile`

### Menu
- `GET /api/menu` (With filters for category/veg-status)
- `GET /api/menu/:id` (Details)

### Orders
- `POST /api/orders/create`
- `GET /api/orders/track/:id` (Socket-enabled)
- `GET /api/orders/history`

### Admin
- `POST /api/admin/menu/add`
- `PATCH /api/admin/orders/:id/status`
- `GET /api/admin/analytics`
