# 🔐 System ยืมคืน — Equipment Borrow & Return System

A modern **desktop application** for managing equipment borrowing and returning, built with Python and CustomTkinter. Features a sleek dark-themed UI with role-based access for **Users** and **Administrators**.

---

## ✨ Features

### 👤 User Portal
- **Browse Equipment** — View all available equipment with status, type, and condition
- **Reserve Equipment** — Submit reservation requests for available items
- **My Activities** — Track reservation and borrowing history
- **My Borrows** — View currently borrowed items with due dates
- **Notifications** — Receive real-time updates on reservation approvals, returns, and fines
- **Fine Management** — View and pay overdue fines

### 👨‍💼 Admin Portal
- **Dashboard Overview** — Statistics for total equipment, active borrows, pending reservations, overdue items, and unpaid fines
- **Manage Equipment** — Add, edit, and delete equipment (CRUD operations)
- **Pending Reservations** — Approve or reject user reservation requests
- **Active Borrows** — Monitor all currently borrowed equipment
- **Process Returns** — Handle equipment returns with condition assessment
- **Fine Management** — View and manage overdue fines with payment processing

### 🎨 UI/UX
- Dark mode with vibrant indigo/purple accent colors
- Card-based layout with rounded corners and status badges
- Color-coded statuses: 🟢 Available · 🔵 Reserved · 🟡 Borrowed · 🔴 Overdue
- Toast notifications for user feedback

---

## 🏗️ Architecture

The project follows the **MVC (Model-View-Controller)** pattern with a service layer:

```
asd123/
├── main.py                  # Application entry point
├── config.py                # System-wide configuration & constants
├── requirements.txt         # Python dependencies
│
├── models/                  # Data Models
│   ├── borrower.py          # Borrower (user) model
│   ├── staff.py             # Staff (admin) model
│   ├── equipment.py         # Equipment model with status enum
│   ├── activity.py          # Borrow/return activity model
│   ├── fine.py              # Fine model with payment status
│   └── notification.py      # Notification model
│
├── services/                # Business Logic Layer
│   ├── reservation_service.py   # Equipment reservation logic
│   ├── borrow_service.py        # Borrowing & approval logic
│   ├── return_service.py        # Return processing logic
│   ├── fine_service.py          # Fine calculation & payment
│   └── notification_service.py  # Notification management
│
├── gui/                     # GUI Layer (CustomTkinter)
│   ├── login_window.py      # Login screen (User/Admin tabs)
│   ├── user_dashboard.py    # User dashboard interface
│   ├── admin_dashboard.py   # Admin dashboard interface
│   ├── styles.py            # Centralized theme & style definitions
│   └── components/
│       └── notification_toast.py  # Toast notification component
│
└── database/                # Data Access Layer
    └── db_manager.py        # SQLite database manager
```

---

## 🛠️ Tech Stack

| Component      | Technology                                   |
| -------------- | -------------------------------------------- |
| Language        | Python 3                                    |
| GUI Framework   | [CustomTkinter](https://github.com/TomSchimansky/CustomTkinter) |
| Database        | SQLite 3                                    |
| Image Handling  | Pillow                                      |
| Date Utilities  | python-dateutil                             |
| QR Code         | qrcode                                     |

---

## 🚀 Getting Started

### Prerequisites

- **Python 3.10+** installed on your system

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd asd123
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the application**
   ```bash
   python main.py
   ```

The database is automatically created and seeded with sample data on first launch.

---

## 🔑 Demo Credentials

| Role  | Email               | Password  |
| ----- | ------------------- | --------- |
| User  | john@example.com    | user123   |
| User  | jane@example.com    | user123   |
| Admin | admin@example.com   | admin123  |

---

## ⚙️ Configuration

Key settings in `config.py`:

| Setting                        | Default | Description                              |
| ------------------------------ | ------- | ---------------------------------------- |
| `FINE_RATE_PER_DAY`            | 10 THB  | Fine charged per overdue day             |
| `DEFAULT_BORROW_PERIOD_DAYS`   | 7 days  | Default loan period                      |
| `MAX_ACTIVE_BORROWS_PER_USER`  | 3       | Maximum concurrent borrows per user      |
| `MAX_RESERVATION_ADVANCE_DAYS` | 30 days | How far in advance users can reserve     |

---

## 📦 Sample Equipment

The system comes pre-loaded with sample equipment for testing:

- 💻 Laptop Dell XPS 15 · MacBook Pro 16"
- 📷 Canon EOS R5 Camera · GoPro Hero 11
- 📱 iPad Pro 12.9"
- 🎤 Rode NT1-A Microphone
- 🎧 Sony WH-1000XM4 Headphones
- ✏️ Wacom Intuos Pro

---

## 📄 License

This project is for educational purposes.
