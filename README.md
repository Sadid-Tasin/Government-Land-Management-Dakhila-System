# Government Land Management & Dakhila System

## Project Overview

**Government Land Management & Dakhila System** is a console-based C++ application designed to manage land records, Khotiyan information, tax calculations, payment processing, system logs, and official reports.

The project demonstrates the practical use of multiple data structures in a single application.

The main data structures used are:

* Doubly Linked List
* Queue
* Stack

The system also uses file handling to save and load land records.

---

## Main Objectives

* Manage Khotiyan/land records.
* Store land owner/reference information.
* Search land records by ID.
* Calculate land tax.
* Track paid and due amounts.
* Process Dakhila payments using a queue.
* Maintain system activity logs using a stack.
* Maintain deleted records through a recycle-bin structure.
* Generate official text reports.
* Save records to a file.
* Load previously saved records when the program starts.
* Provide admin authentication.

---

## Data Structures Used

### 1. Doubly Linked List

Land records are stored using a doubly linked list.

Each land node contains:

```text
Khotiyan ID
Reference Name
Place Name
Area Type
Area
Paid Amount
Previous Node
Next Node
```

The `prev` and `next` pointers allow the system to maintain connections between neighboring land records.

---

### 2. Queue

A queue is used for **Dakhila payment processing**.

Each queue node stores:

```text
Land ID
Payment Amount
Next Node
```

The queue follows the **FIFO (First In, First Out)** principle.

Therefore, payments are processed in the same order in which they were added to the queue.

---

### 3. Stack

A stack is used to maintain system logs.

Whenever important operations occur, a log entry is pushed into the stack.

Examples include:

```text
New Khotiyan Node Added
Node Deleted
Payments Processed
```

The most recent log appears first because the stack follows the **LIFO (Last In, First Out)** principle.

---

## Land Record Management

The Khotiyan Management section allows the user to:

* Insert a new land record.
* Delete an existing land record.
* View the current linked-list sequence.
* Prevent duplicate Khotiyan IDs.

When a new record is inserted, the system calculates the estimated tax and determines the land category.

---

## Land Tax Calculation

The system calculates tax based on land area and location.

The land category and base rate depend on the area.

### Land Categories

```text
Area ≤ 10
→ Residential (Bastu)

Area ≤ 50
→ Agricultural Land

Area ≤ 100
→ Commercial Land

Area > 100
→ Industrial / Large Land
```

The rate is then adjusted according to whether the location is **Urban** or **Rural**.

### Tax Formula

```text
Tax = Area × Adjusted Rate
```

---

## Search by Khotiyan ID

The user can search for a land record using its Khotiyan ID.

If the record exists, the system displays:

* ID
* Name
* Place
* Area Type
* Total Tax
* Paid Amount
* Due Amount

The remaining due is calculated as:

```text
Due = Total Tax - Paid Amount
```

---

## Delete & Recycle Bin System

When a land record is deleted, the system does not simply discard its information.

A copy of the deleted record is stored separately as a **recycle-bin record**.

The system then removes the original node from the active doubly linked list and fixes the neighboring nodes.

This demonstrates practical linked-list deletion and record preservation.

---

## Dakhila Payment Queue

The system supports multiple payment requests.

The user can enter several payments into a queue.

Each payment contains:

```text
Khotiyan ID
Payment Amount
```

The system validates the ID and payment amount before placing the payment into the queue.

After the queue is created, payments are processed sequentially.

The paid amount is updated and the remaining due is recalculated after each payment.

---

## File Handling

The project uses file handling to preserve land records.

The active records are saved into:

```text
records.txt
```

Each record is stored using a delimiter-based format:

```text
ID | Reference Name | Place | Area Type | Area | Paid Amount
```

When the program starts, it loads the saved records from the file.

This allows data to remain available even after the program is closed.

---

## System Logs

The project maintains an internal history of important operations.

The logging system uses a stack.

Operations such as:

```text
New Khotiyan Node Added
Node Deleted
Payments Processed
```

are pushed into the history stack.

The system provides a dedicated **System Logs** menu for viewing these records.

---

## Report Generation

The system can generate an official land report in `.txt` format.

The user provides:

* Report name
* Report date

The system creates a file using the format:

```text
ReportName_Date.txt
```

The report contains active records with:

* ID
* Name
* Paid amount
* Due amount

It also includes deleted records.

---

## Admin Security

The application contains an admin login system.

The login requires:

```text
Username
Password
```

The password is entered using hidden character input.

The system allows a maximum of **3 login attempts**.

Successful authentication provides access to the main menu.

---

## Main Menu

After successful login, the user gets access to:

```text
1. Khotiyan Management
2. Process Dakhila Queue
3. View System Logs
4. Print All Records
5. Search by ID
6. Generate Full Report
7. Save & Exit
```

The main program first loads existing records and then opens the admin-controlled menu.

---

## Complete System Flow

```text
Program Start
      ↓
Load Saved Records
      ↓
Admin Login
      ↓
Main Menu
      │
      ├── Khotiyan Management
      │      ├── Add Record
      │      └── Delete Record
      │
      ├── Dakhila Payment Queue
      │
      ├── System Logs
      │
      ├── Print All Records
      │
      ├── Search by ID
      │
      ├── Generate Report
      │
      └── Save & Exit
```

---

## Programming Concepts Used

### Data Structures

* Doubly Linked List
* Queue
* Stack

### Algorithms / Logic

* Linear search through linked records
* Tax calculation
* Queue-based payment processing
* Stack-based logging
* Linked-list insertion
* Linked-list deletion

### Other C++ Concepts

* Structures
* Pointers
* Dynamic memory allocation
* Classes/struct-like data organization
* File input/output
* String processing
* Functions
* Loops
* Conditional statements
* Menu-driven programming

---

## Technologies

**Language:** C++

**Application Type:** Console-based Land Management System

**Core Concepts:** Data Structures, Pointers, Linked List, Queue, Stack, File Handling

---

## Learning Outcomes

This project demonstrates how multiple data structures can work together inside one practical application.

The main concepts practiced include:

* Dynamic memory management.
* Doubly linked-list operations.
* Queue implementation.
* Stack implementation.
* File persistence.
* Search and record management.
* Financial calculations.
* Report generation.
* Authentication.
* Designing a multi-feature console application.

---

## Project Type

**Academic C++ / Data Structures Project**

The project demonstrates the practical application of fundamental data structures in a land-record and payment-management scenario.
