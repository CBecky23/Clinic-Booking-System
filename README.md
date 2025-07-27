# Clinic Booking System

## 🩺 Project Overview

This project is a **Clinic Booking System**, designed to help a medical clinic manage its **appointments**, **patients**, **doctors**, and **prescriptions** efficiently. The system uses **MySQL** and includes a fully normalized schema with essential relationships, constraints, and data integrity features.



## 🧰 Features

- Manage doctors and their specialties
- Register and update patient information
- Book appointments and avoid scheduling conflicts
- Track prescriptions issued during appointments



## 🛠️ How to Run / Import

1. Make sure you have MySQL installed (e.g., via MySQL Workbench).
2. Clone this repository to your local machine.
3. Open MySQL Workbench or any SQL client.
4. Import and run the `clinic_booking_system.sql` file to create the database schema.



## 🔗 Entity Relationship Diagram (ERD)

+----------------+       +----------------+       +----------------+
|   Specialties  |       |    Doctors     |       |    Patients    |
+----------------+       +----------------+       +----------------+
| specialty_id PK|◄──────| doctor_id  PK  |       | patient_id  PK |
| name  UNIQUE   |       | full_name      |       | full_name      |
+----------------+       | email  UNIQUE  |       | gender         |
                         | phone  UNIQUE  |       | date_of_birth  |
                         | specialty_id FK|─────► | phone  UNIQUE  |
                         +----------------+       | email  UNIQUE  |
                                                  +----------------+

            +--------------------------+
            |       Appointments       |
            +--------------------------+
            | appointment_id     PK    |
            | doctor_id          FK    |───┐
            | patient_id         FK    |───┘
            | appointment_date         |
            | status (ENUM)           |
            | notes                   |
            +--------------------------+

                    +----------------------+
                    |     Prescriptions    |
                    +----------------------+
                    | prescription_id PK   |
                    | appointment_id  FK   |───► Appointments
                    | medication           |
                    | dosage               |
                    | instructions         |
                    +----------------------+





