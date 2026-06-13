# 🚗 Pink Ride - Premium Women's Carpooling Platform

<p align="center">
  <img src="uploads/logo.png" alt="Pink Ride Logo" width="160" style="border-radius: 50%; box-shadow: 0 10px 20px rgba(216, 27, 96, 0.2);">
</p>

<p align="center">
  <strong>A secure, production-ready, full-stack web ecosystem built for exclusive female ride-sharing and optimized capacity distribution.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/PHP-8.x-777BB4?style=for-the-badge&logo=php&logoColor=white" alt="PHP Shield">
  <img src="https://img.shields.io/badge/MySQL-Database-4479A1?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL Shield">
  <img src="https://img.shields.io/badge/Bootstrap-5.3-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white" alt="Bootstrap Shield">
  <img src="https://img.shields.io/badge/Security-Sessions%20%26%20Cookies-success?style=for-the-badge" alt="Security Shield">
</p>

---

## 📌 Project Architecture & Vision

**Pink Ride** is a high-quality web platform engineered with **PHP** and **MySQL** to address daily transit and commuting security challenges for women and university students. By using an advanced multi-role paradigm, the platform facilitates safe, economical, and decentralized ride-pooling. 

### 💡 Core Operations Flow
* **The Drivers:** Create customized routes, define pricing schedules, and dynamically scale ride availability up to a maximum **4-seat threshold** per vehicle.
* **The Passengers:** Intuitively browse paths via responsive multi-tier queries, leverage real-time cost-efficiency filters, and instantly lock seats.

---

## 🔥 Key Technical Superpowers

### 1. 👥 Multi-Role Authorization & Dashboard Matrix
Separate user execution spaces dynamically generated via PHP variables.
* **Driver View (`driver_dashboard.php`):** Full autonomous control over current trip distribution. Integrated with instant database updates (`INSERT`, `SELECT`, `UPDATE`).
* **Interactive Modals:** Backed by **SweetAlert2** injection for clean, seamless asynchronous user validation prompts (e.g., delete confirmation hooks).

### 2. 🔐 Industrial-Grade Security Best Practices
* **SQL Injection Blockers:** Strict usage of Native Prepared Statements (`$conn->prepare()`) combined with parameter binding (`bind_param()`) for all crucial operational actions like `delete_ride.php` and `edit_ride.php`.
* **Cross-Account Session Protection:** Hard-token checking prevents malicious parameter manipulation. Drivers can *only* alter or delete rows that uniquely mismatch their active encrypted `$_SESSION['user_id']`.
* **Password Hashing:** Implements full cryptographic salting verification via `password_verify()` during login stages.
* **XSS Mitigation & UI Validation:** All textual readouts utilize `htmlspecialchars()` escaping. Client-side state engines freeze inputs instantly if regular expressions (Regex) spot invalid structured input formatting (e.g., modern immediate mail triggers).

### 3. 🌐 Native Hybrid Dual-Language Localizer
* A completely built-in localization mechanism (`lang.php`) capable of hot-swapping global translation matrices dynamically on-the-fly.
* Features automatic memory persistence across standard user lifecycles using structured combinations of persistent browser `setcookie()` tracking and short-lived `$_SESSION` storage arrays.

---

## 📁 Repository Blueprint

```text
pink_ride/
├── lang.php               # Complete system-wide translation dictionary matrix
├── db_connect.php          # Core system backend MySQL initialization configurations
├── index.php              # Modern landing hub & fast system onboarding panel
├── about.php              # Corporate team overview, course credits, and identity module
├── login.php              # Highly responsive login form with real-time UI data validation
├── logout.php             # Full cookie clearings and structured session state destructions
├── driver_dashboard.php   # Driver operations engine with full programmatic control
├── edit_ride.php          # Interface designed for real-time ride detail transformations
├── delete_ride.php        # Secure backend script enforcing validation logic before item removal
├── book.php               # Capacity depletion algorithm ensuring single seat reductions
└── pink_rides_db.sql      # Raw logical database migrations script
