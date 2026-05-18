# Developer Handoff: Chaudhary Cafe & Family Restaurant

## 1. Project Overview
A three-app ecosystem (Customer, Admin, Rider) designed with a premium, high-contrast dark mode aesthetic (**Culinary Noir**).

## 2. Design System: Culinary Noir
- **Theme:** Dark Mode
- **Primary Color:** `#ff8c00` (Brand Orange)
- **Background:** `#131313` (Surface)
- **Typography:** Montserrat (San-serif)
- **Radius:** 8px (Round Eight)

## 3. Screen Inventory & Functional Logic

### A. Customer App (Mobile)
| Screen | Placeholder | Key Logic / Interaction |
| :--- | :--- | :--- |
| Splash Screen | {{DATA:SCREEN:SCREEN_5}} | Auto-transition to Home after 2-3 seconds. |
| Home Screen | {{DATA:SCREEN:SCREEN_4}} | Search functionality, category filtering, featured promotions. |
| Menu Explorer | {{DATA:SCREEN:SCREEN_24}} | Tabbed navigation (Veg/Non-Veg), Add-to-cart logic. |
| Food Details | {{DATA:SCREEN:SCREEN_30}} | Ingredient list, portion selection, price calculation. |
| Cart & Coupons | {{DATA:SCREEN:SCREEN_11}} | Quantity adjustment, coupon code validation, subtotal calculation. |
| Checkout & Address | {{DATA:SCREEN:SCREEN_7}} | Address selection, payment method toggle (COD/Online). |
| Order Tracking | {{DATA:SCREEN:SCREEN_31}} | Real-time status updates via Socket.io, Map integration. |
| Table Booking | {{DATA:SCREEN:SCREEN_10}} | Date/Time picker, guest count selection, availability check. |
| User Profile | {{DATA:SCREEN:SCREEN_18}} | Edit profile, access to order history. |
| Order History | {{DATA:SCREEN:SCREEN_17}} | List of past orders with "Reorder" functionality. |
| About & Contact | {{DATA:SCREEN:SCREEN_2}} / {{DATA:SCREEN:SCREEN_20}} | Static info, map embed, contact form validation. |

### B. Admin Dashboard (Mobile)
| Screen | Placeholder | Key Logic / Interaction |
| :--- | :--- | :--- |
| Admin Login | {{DATA:SCREEN:SCREEN_13}} | Secure authentication using credentials in `DOCUMENT_6`. |
| Admin Overview | {{DATA:SCREEN:SCREEN_8}} | High-level analytics (daily sales, active orders, bookings). |
| Order Management | {{DATA:SCREEN:SCREEN_22}} | Update order status (Preparing -> Out for Delivery). |
| Menu Management | {{DATA:SCREEN:SCREEN_27}} | CRUD operations for food items, toggle availability. |
| Booking Management | {{DATA:SCREEN:SCREEN_26}} | Confirm or cancel table reservations. |
| Admin Settings | {{DATA:SCREEN:SCREEN_16}} | Operating hours, location settings, dark mode toggle. |
| Change Password | {{DATA:SCREEN:SCREEN_25}} | Security flow with validation and success state (SCREEN_19). |

### C. Delivery Rider App (Mobile)
| Screen | Placeholder | Key Logic / Interaction |
| :--- | :--- | :--- |
| Rider Dashboard | {{DATA:SCREEN:SCREEN_14}} | Active task list, availability toggle (Online/Offline). |
| Delivery Details | {{DATA:SCREEN:SCREEN_23}} | Customer contact info, navigation to address, "Delivered" swipe. |
| Rider Profile | {{DATA:SCREEN:SCREEN_29}} | Personal stats, performance rating. |
| Earnings | {{DATA:SCREEN:SCREEN_28}} | Daily/Weekly payouts and task history. |

## 4. Technical Specifications
- **Frontend Recommendation:** Flutter (as per `DOCUMENT_15`).
- **Backend:** Node.js with Express.js.
- **Database:** MongoDB (Schema defined in `DOCUMENT_15`).
- **Real-time:** Socket.io for order status synchronization across all three apps.

## 5. Assets & Branding
- **Logo:** `{{DATA:IMAGE:IMAGE_1}}` (or equivalent brand mark).
- **Icons:** Standard Material Design icons used throughout for consistency.
- **Images:** High-quality food photography should be served via Cloudinary/AWS S3.
