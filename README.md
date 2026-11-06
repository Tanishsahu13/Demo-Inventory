# 📦 Demo Inventory — Inventory & Rental Management System

A **full-stack inventory and rental management web app** — manage items, bookings, payments and availability in real time, with a public catalogue anyone can browse without logging in.

### 🔗 Live Demo: [demo-inventory-five.vercel.app](https://demo-inventory-five.vercel.app)

> ⚠️ The demo **wipes itself clean every day at midnight (IST)** — items, bookings and staff accounts reset daily, so feel free to try everything.

### 🔑 Demo Login

| | |
|---|---|
| **Username** | `demo@gmail.com` |
| **Password** | `demo@123` |

Log in as staff/owner to try the full system — inventory, bookings, payments and staff management. Everything you change is wiped at midnight IST.

![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

## ✨ Features

- 📋 **Item inventory** — add items with photos, code, price-per-day and status
- 🌐 **Public catalogue** — customers browse items at `/collection` with no login, updated in real time
- 📅 **Smart bookings** — date-conflict blocking at the database level, no double bookings
  - Past-date bookings are blocked in the UI *and* in the database
  - 1-day return buffer for single-day bookings
  - Negotiated pricing — booking total can be adjusted at booking time
- 💰 **Payments tracking** — total / paid / remaining per booking, with a payment history
- 📸 **Google Drive photo storage** — one photo file per item, served at multiple sizes
- 📊 **Live bookings CSV** — a single spreadsheet in Drive that rewrites itself in real time on every booking or payment change (database triggers + serverless API)
- 🔐 **Staff accounts & security**
  - Owner / staff roles, owner-only staff management
  - Login lockout — 5 failed attempts → 15-minute lock
  - Removed staff are signed out immediately and cannot log in again
  - Self-service password change for staff
- 🗑️ **Delete-everything** — deleting an item removes its photos, bookings, payments, blocks and locks in one confirmed action
- ⏰ **Daily self-wipe (demo only)** — a scheduled cron resets the whole demo store at midnight IST

## 🏭 The Production Story Behind It

This demo is the public, generic version of a **real production system I built and deployed for Poonam Lehenga Bhandar, a lehenga rental shop in Sagar, Madhya Pradesh** — the **Lehenga Inventory & Rental System**.

That production deployment runs daily on the shop's own accounts with real staff users, real bookings and payments, a public customer catalogue, Drive photo storage and the live bookings CSV. The Demo Inventory is the same system, rebranded, stripped of all shop details, and set to wipe itself daily — so anyone can explore it safely without touching real business data.

| | Production — Lehenga Inventory | This Demo |
|---|---|---|
| Users | Real shop staff (owner + staff roles) | Anyone — resets daily |
| Data | Real inventory, bookings & payments | Sample / test data only |
| Branding | Poonam Lehenga Bhandar | Generic "Demo Inventory" |
| Extra behaviour | — | Daily midnight self-wipe |

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React, Vite, CSS |
| Backend / DB | Supabase — PostgreSQL, Auth, Row-Level Security, RPCs, realtime |
| Serverless APIs | Vercel Functions (Node.js) |
| Storage | Google Drive API (photos + live CSV backups) |
| Hosting | Vercel, with cron jobs |
| Integrity | DB triggers, date locks, exclusion rules against double booking |

## 👨‍💻 Author

**Tanish Sahu** — Software Developer · Java, DSA & Full-Stack Web
[GitHub](https://github.com/Tanishsahu13) · [LinkedIn](https://www.linkedin.com/in/tanish-sahu-818021256) · [LeetCode](https://leetcode.com/u/4YFQSEyn2Q/)
