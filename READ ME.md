# Gate Pass System

## Overview

The Gate Pass System is an application developed to efficiently track and manage the movement of members with their belongings, such as laptops, cars, and other properties. This system aims to eliminate the need for manual paperwork by securely recording and tracking the details of all items and their owners electronically. The system is designed for use by security officers who need a portable and user-friendly solution to track items as they enter or exit the premises.

## Key Features

1. **Registration of Items**:
   - Laptops, cars, and other properties can be registered by entering member details such as member ID, serial number (for laptops), number plate (for cars), and a secure password.
   - Each item will be associated with a unique identifier (QR code or number plate) for easy tracking.
   - QR codes are generated and displayed for laptops, linking the member with the item for easy verification.

2. **Authentication at Gate**:
   - Members can authenticate their exit by either scanning their generated QR code (for laptops) or entering the number plate (for cars) along with a password.
   - The system verifies if the details entered match the stored data and ensures that the member is authorized to take the item out.

3. **Password Protection**:
   - Passwords are used to secure both the registration and authentication processes, ensuring that only authorized individuals can access or take items.

4. **User Interface**:
   - A simple and intuitive graphical user interface (GUI) built with PyQt5 allows security officers to interact with the system efficiently.

5. **Portable and User-Friendly**:
   - The system is designed to be portable, meaning it can be deployed on devices such as tablets or laptops for use at the gate.
   - The interface is straightforward, with options for registering items, authenticating exits, and generating QR codes.

6. **Database Storage**:
   - SQLite is used for local database management, storing member data, item details (laptops, cars), and passwords securely.
   - The database supports the addition and querying of items, ensuring efficient management of records.

## System Components

### 1. **Database Interaction (`database.py`)**:
   - This module handles all interactions with the SQLite database, such as setting up tables, registering new items, and authenticating members.
   - The database stores information like member IDs, serial numbers (for laptops), number plates (for cars), QR code data, and passwords.
   
### 2. **User Interface (`ui.py`)**:
   - The user interface (UI) is built using PyQt5 and consists of several windows for registering laptops and cars, authenticating members at the gate, and generating QR codes.
   - The UI includes input fields for member IDs, serial numbers, number plates, and passwords, along with buttons to trigger registration and authentication actions.
   - It also supports generating and displaying QR codes for laptops.
   
### 3. **QR Code Generation (`qr_code.py`)**:
   - QR codes are generated dynamically for laptops based on the member ID, serial number, and password.
   - These QR codes are displayed in the UI for scanning during authentication.

### 4. **Main Program (`main.py`)**:
   - This serves as the entry point for the application, initializing the database and launching the PyQt5 application.
   - It controls the flow between different UI windows (registration, authentication, etc.).

### 5. **Authentication (`authenticate.py`)**:
   - The authentication logic checks if the entered details (QR code or number plate and password) match the records in the database.
   - If the authentication is successful, the item is marked as "authenticated," allowing the member to exit the premises.

## Installation

### Dependencies

This system is built with the following Python packages:

- **PyQt5**: For creating the graphical user interface (GUI).
- **qrcode**: For generating QR codes.
- **SQLite3**: For managing local databases.

To install the necessary dependencies, run the following command:

```bash
pip install -r requirements.txt
