# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
● Members register with details like name, membership type, and start date.
● Each member can join multiple programs (Yoga, Zumba, Weight Training).
● Trainers are assigned to programs, and a program may have multiple trainers.
● Members may book personal training sessions with trainers.
● Attendance is recorded for each session.
● Payments are tracked for memberships and sessions

### ER Diagram:

<img width="850" height="570" alt="image" src="https://github.com/user-attachments/assets/85cd3ad5-fc97-4085-842b-395032f0732e" />

### Entities and Attributes
1. Members
○ Name
○ Contact Number
○ Address
2. Programs
○ Type
○ Fees
○ Duration
3. Trainers
○ Name
○ Contact Number
○ Specialization
4. Payments
○ Amount
○ Payment Type
○ Due Date
### Relationships and Constraints
 ● Members ↔ Programs
A Member can join multiple Programs.
A Program can have many Members (M:N, resolved via "Joins").
● Programs ↔ Trainers
A Program can have many Trainers.
A Trainer can conduct multiple Programs (M:N, resolved via "Conducts").
● Members ↔ Trainers (Personal Sessions)
A Member can book personal sessions with multiple Trainers.
A Trainer can train multiple Members (M:N).
● Trainers ↔ Payments
A Trainer can have many Payments for sessions.
Each Payment is linked to one Trainer (1:M).
● Members ↔ Payments
A Member can make many Payments for memberships and sessions.
Each Payment is linked to one Member (1:M).


# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
● Members borrow books, with loan dates and return dates tracked.
● Each book has details such as title, author, and category.
● The library organizes events; members can register for them.
● Each event has one or more speakers/authors.
● Rooms in the library are booked for events and study purposes.
● Overdue fines apply for late book returns

### ER Diagram:

<img width="840" height="556" alt="image" src="https://github.com/user-attachments/assets/a2da7465-be27-45e8-8b60-faae2bf54542" />

### Entities and Attributes

1.Member
● Member ID
● Name
● Date
● Contact No
2.Loan
● Member ID
● Due Date
● Book ID
● Fine
● Loan ID
● Loan Date
● Return Date
3.Book
● Category
● Book ID
● Title
● Author
4.Event
● Room ID
● Event Date
● Event Name
● Event ID
5.Room
● Room ID
● Capacity
● Room Name
6.Speaker
● Name
● Speaker ID
### Relationships and Constraints

● Member ↔ Loan ↔ Book
A Member can borrow many Books (M:N, resolved via Loan).
Each Loan links one Member to one Book.
● Member ↔ Event
A Member can register for many Events.
An Event can have many Members (M:N, resolved via Event_Registration).
● Event ↔ Room
Each Event occurs in one Room (1:N).
● Room ↔ Speaker
A Room can have many Speakers (M:N).
● Event ↔ Speaker
An Event can have multiple Speakers (1:N).


# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
● Customers can reserve tables in advance or walk in.
● Each reservation includes date, time, and number of guests.
● Customers place food orders linked to their reservation.
● Each order contains multiple dishes; dishes belong to categories (starter, main,
dessert).
● Bills are generated per reservation, including food and service charges.
● Waiters are assigned to serve reservations.

### ER Diagram:

<img width="792" height="480" alt="image" src="https://github.com/user-attachments/assets/d6231b65-77fe-423c-bc53-36b77495ac26" />

### Entities and Attributes
1. Customer
○ Customer ID
○ Name
○ Phone No
2. Reservation
○ Reservation ID
○ Customer ID
○ Reservation Date and Time
○ Table ID
3. Table
○ Table No
○ Capacity
4. Waiter
○ Waiter ID
○ Name
○ Phone No
5. Order
○ Order ID
○ Reservation ID
○ Order Time
6. Dish
○ Dish ID
○ Name
○ Price
7. Bill
○ Bill ID
○ Total Amount

### Relationships and Constraints

● Customer ↔ Reservation
A Customer can make many Reservations.
Each Reservation is made by one Customer (1:M).
● Reservation ↔ Table
Each Reservation is assigned to one Table.
A Table can be reserved many times (1:M).
● Reservation ↔ Order
A Reservation can have many Orders.
Each Order is linked to one Reservation (1:M).
● Order ↔ Dish
An Order can contain many Dishes.
A Dish can be in many Orders (M:N, resolved via an Order_Dish relationship).
● Reservation ↔ Bill
Each Reservation generates one Bill (1:1).
● Waiter ↔ Reservation
A Waiter can serve many Reservations.
Each Reservation is served by one Waiter (1:M).


