# Rush2U Admin — Delivery Operations & Dispatch Panel

> **Laravel** back-office panel for managing the [Rush2U](https://github.com/irfanf16/rush2u) on-demand delivery platform. Dispatchers assign orders to drivers, monitor active deliveries on a live map, manage driver accounts, and control payouts.

![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=flat-square&logo=laravel&logoColor=white)
![Pusher](https://img.shields.io/badge/Pusher-Real--time-300D4F?style=flat-square&logo=pusher&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)

---

## Overview

```
rush2u       — Customer-facing app
rush2uAdmin  — THIS REPO — Operations, dispatch, analytics
(shared MySQL DB)
```

---

## Features

### Live Delivery Monitoring Map
- Real-time map showing all active drivers' GPS positions via Pusher
- Color-coded markers: available drivers, drivers on delivery, drivers offline
- Click driver marker to see current order assignment and delivery progress

### Driver Management
- Driver onboarding: registration, document upload, vehicle assignment
- Status management: activate, suspend, or deactivate driver accounts
- Real-time availability toggle visibility

### Order Dispatch
- Incoming order queue with customer details and addresses
- Manual driver assignment or auto-dispatch based on proximity
- Order reassignment if driver unavailable

### Notification Control
- Send push notifications to customers (order updates, promotions)
- Send broadcast notifications to all active drivers (surge pricing, alerts)

### Earnings & Payout Management
- Driver earnings dashboard (per delivery, weekly totals)
- Payout processing and payment history
- Commission deduction configuration (platform % per delivery)

### Analytics Dashboard
- KPIs: total deliveries, average delivery time, completion rate, revenue
- Driver performance leaderboard
- Geographic heatmap of delivery density
- Customer retention and order frequency metrics

---

## Database

Shares the `rush2u` database. Full read/write access to:

| Table | Admin Operations |
|---|---|
| `orders` | Assign driver, update status, cancel |
| `drivers` | CRUD, document management, status |
| `order_tracking` | Read all tracking events |
| `payments` | View + manual reconciliation |
| `ratings` | Read + moderation |
| `notifications` | Create + send to user segments |

---

## Getting Started

```bash
composer install
cp .env.example .env
# Use same DB as rush2u
php artisan key:generate
php artisan serve
```

## Related Repositories

| Repo | Purpose |
|---|---|
| `rush2u` | Customer-facing delivery app (shared database) |
