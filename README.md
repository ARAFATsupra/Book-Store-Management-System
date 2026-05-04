# Book Store Management System

A fully functional, console-based Book Store Management System built in Python using core Object-Oriented Programming (OOP) principles. This project was developed as part of the Object Oriented Programming course (ITM 213) at Daffodil International University.

---

## Table of Contents

- [Project Summary](#project-summary)
- [Technical Skills Demonstrated](#technical-skills-demonstrated)
- [OOP Concepts Applied](#oop-concepts-applied)
- [System Architecture](#system-architecture)
- [Features](#features)
- [How to Run](#how-to-run)
- [Project Structure](#project-structure)
- [Sample Output](#sample-output)
- [Team](#team)
- [Course Details](#course-details)

---

## Project Summary

This project simulates a real-world bookstore system where customers can browse books, manage a shopping cart, maintain a wishlist, and request unavailable titles. A separate admin panel allows store managers to add, remove, and update book details securely using password authentication.

The system is designed with clean separation of responsibilities, making it easy to read, extend, and maintain. Each feature is handled by a dedicated class, reflecting real software engineering practices used in industry.

---

## Technical Skills Demonstrated

| Skill | Details |
|---|---|
| Language | Python 3 |
| Paradigm | Object-Oriented Programming (OOP) |
| Concepts | Classes, Inheritance, Encapsulation, Abstraction |
| Error Handling | try-except blocks for invalid inputs |
| Data Structures | Lists for managing cart, wishlist, and book inventory |
| Access Control | Private attributes using Python name mangling (`__`) |
| Authentication | Password-protected admin login |
| User Interface | Interactive text-based menu system |
| Code Organization | Modular design with single-responsibility classes |

---

## OOP Concepts Applied

### 1. Classes and Objects
Every core entity in the system is represented as a class. For example, `Book`, `Cart`, `Wishlist`, `BookStore`, and `BookRequest` are all independent classes, each with their own data and behaviour.

### 2. Inheritance
A base class `User` holds shared attributes like `name`. Both `Customer` and `Admin` inherit from `User`, meaning they automatically get the `name` attribute without repeating code. This follows the DRY (Do Not Repeat Yourself) principle.

```
User (Base Class)
├── Customer (inherits name, adds cart and wishlist)
└── Admin (inherits name, adds password and verification)
```

### 3. Encapsulation
Sensitive data is kept private using Python's double underscore convention. For example:

- `Cart.__items` — the list of cart items is private and can only be accessed through defined methods like `add_book()`, `view_cart()`, and `checkout()`.
- `Admin.__password` — the admin password is hidden from outside the class. It can only be verified through the `verify_password()` method, not accessed directly.

This mirrors how real applications protect sensitive information.

### 4. Abstraction
Each class exposes only what is necessary. A `Customer` object does not need to know how the `Cart` internally stores items. It simply calls `cart.add_book(book)` and the `Cart` class handles the rest.

---

## System Architecture

The project is divided into 8 classes, each with a specific responsibility:

```
BookStore (main hub)
├── Book             — Stores title, category, price
├── User             — Base class for all users
│   ├── Customer     — Has a Cart and Wishlist
│   └── Admin        — Has password, can manage store
├── Cart             — Add, view, checkout books
├── Wishlist         — Save books for later
└── BookRequest      — Record and display book requests
```

This modular structure means that any part of the system can be updated independently without breaking the rest.

---

## Features

### Customer Features
- View the full list of available books with category and price
- Add any book to a personal shopping cart
- View cart contents with a calculated total price
- Checkout and clear the cart after purchase
- Add books to a personal wishlist for future reference
- View wishlist at any time
- Request a book that is not currently in the store

### Admin Features (Password Protected)
- Secure login with password authentication
- Change the price of any existing book
- Add a new book to the store inventory
- Remove a book from the store inventory
- View all book requests submitted by customers
- Logout safely back to the customer menu

### System Features
- Input validation throughout — the system handles letters entered where numbers are expected
- Duplicate prevention — the wishlist will not add the same book twice
- Clear error messages for all invalid inputs
- Session persistence — cart and wishlist data is maintained throughout the session

---

## How to Run

**Requirements:** Python 3.x installed on your computer. No additional libraries or packages are needed.

**Step 1:** Download or clone this repository.

**Step 2:** Open your terminal or command prompt and navigate to the project folder.

**Step 3:** Run the following command:

```bash
python bookstore.py
```

**Step 4:** Follow the on-screen menu to use the system.

**Admin Login Details for Testing:**
```
Password: admin123
```

---

## Project Structure

```
Book-Store-Management-System/
│
├── bookstore.py               # Main Python source code
├── README.md                  # Project documentation
```

---

## Sample Output

**Customer Menu:**
```
###--- Welcome to the BOOK MANAGEMENT SYSTEM ---###

1) See available books
2) Add book to cart
3) View your cart
4) Checkout
5) Add book to wishlist
6) View your wishlist
7) Request a book
8) Admin login
9) Exit
```

**Viewing Cart:**
```
Your cart:
- The Fault in Our Stars (Romantic): BDT 400
Total Price: BDT 400
```

**Admin Panel:**
```
###--- Admin Panel ---###

Admin Options:
1) Change book price
2) Add book
3) Remove book
4) View requested books
5) Logout
```

---

## Team

This project was developed collaboratively by Team Insight.

---

## Course Details

| Field | Details |
|---|---|
| Course Title | Object Oriented Programming |
| Course Code | ITM 213 |
| Instructor | Moni Akter, Lecturer |
| Department | Information Technology and Management (ITM) |
| Faculty | Science and Information Technology |
| University | Daffodil International University |
| Batch | 8th |
| Section | A |
| Semester | Fall 2024 |
| Submission Date | 11th December 2024 |

---

## Future Improvements

This project was built as a console application and can be extended in several ways:

- Adding a graphical user interface (GUI) using Tkinter or PyQt
- Connecting to a database such as SQLite or MySQL to persist data across sessions
- Implementing a user registration and login system for multiple customers
- Adding a payment gateway for real checkout processing
- Building a web version using Flask or Django
- Adding search and filter functionality for books by category or price range

---

## License

This project is open for academic and learning purposes. Feel free to fork and build upon it.
