# 🧩 Data Model – SmartBuy Agent

## 📌 Entity: User
- `user_id` (UUID, PK)
- `email` (String)
- `full_name` (String)
- `phone_number` (String)
- `preferred_currency` (String)
- `created_at` (Timestamp)
- `updated_at` (Timestamp)

## 📌 Entity: UserPreference
- `preference_id` (UUID, PK)
- `user_id` (UUID, FK → User)
- `preferred_brands` (Array[String])
- `max_price` (Decimal)
- `min_rating` (Decimal)
- `delivery_window_days` (Integer)
- `default_shipping_address_id` (UUID, FK → Address)
- `default_payment_method_id` (UUID, FK → PaymentMethod)

## 📌 Entity: Address
- `address_id` (UUID, PK)
- `user_id` (UUID, FK → User)
- `recipient_name` (String)
- `street_address` (String)
- `city` (String)
- `state` (String)
- `zip_code` (String)
- `country` (String)
- `is_default` (Boolean)

## 📌 Entity: PaymentMethod
- `payment_id` (UUID, PK)
- `user_id` (UUID, FK → User)
- `card_type` (String)
- `last4` (String)
- `expiry_date` (Date)
- `tokenized_reference` (String)
- `is_default` (Boolean)

## 📌 Entity: PurchaseRequest
- `request_id` (UUID, PK)
- `user_id` (UUID, FK → User)
- `input_text` (Text)
- `product_url` (String, optional)
- `status` (Enum: pending, searching, purchasing, completed, failed)
- `created_at` (Timestamp)

## 📌 Entity: ProductMatch
- `match_id` (UUID, PK)
- `request_id` (UUID, FK → PurchaseRequest)
- `platform` (Enum: amazon, walmart, target, etc.)
- `product_title` (String)
- `product_url` (String)
- `price` (Decimal)
- `rating` (Decimal)
- `availability` (Boolean)
- `estimated_delivery_days` (Integer)
- `selected_for_purchase` (Boolean)

## 📌 Entity: Order
- `order_id` (UUID, PK)
- `request_id` (UUID, FK → PurchaseRequest)
- `platform` (String)
- `order_reference` (String)
- `order_status` (Enum: ordered, shipped, delivered, canceled)
- `shipping_tracking_number` (String)
- `delivery_estimate` (Date)
- `order_date` (Timestamp)

## 📌 Entity: NotificationLog
- `notification_id` (UUID, PK)
- `user_id` (UUID, FK → User)
- `order_id` (UUID, FK → Order, nullable)
- `type` (Enum: status_update, alert, exception)
- `message` (Text)
- `sent_via` (Enum: email, sms, in_app)
- `sent_at` (Timestamp)
