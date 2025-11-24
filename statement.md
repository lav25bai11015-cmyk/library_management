Problem Statement
In many small libraries or schools, records are still maintained manually in physical registers. This traditional method is prone to errors—pages get torn, handwriting can be illegible, and it is very time-consuming to flip through pages just to find out if a specific book is available. Furthermore, calculating fines for late returns manually is tedious and often leads to mistakes or favoritism. There was a need for a digital solution to automate these tasks, making the process faster, fairer, and more organized.

Scope of the Project
This project is a functional, console-based application developed using Python. It is designed to handle the core operations of a library management cycle.

What it does: It manages book inventory, tracks issued books, and automates the fine calculation process.

Technology: It uses Python's Object-Oriented Programming (Classes and Objects) and data structures like Dictionaries for fast data retrieval.

Limitations: Currently, it stores data in temporary memory (RAM) while the program is running, making it a perfect prototype or logic demonstration for a Class 12 Computer Science practical. It can be expanded later to use SQL or file handling for permanent storage.

Target Users
Librarians: The primary users who need a hassle-free way to issue books and check stock without counting physical copies on shelves.

School Administrators: To oversee the library's efficiency and ensure fines are collected systematically.

Students: While they don't operate the code directly, they are the end-users who benefit from a transparent system where they know exactly when to return a book to avoid penalties.

High-level Features
Smart Stock Management: Unlike simple lists, this system tracks the exact quantity of each book. It automatically decreases the count when a book is issued and increases it when returned.

Automated Fine Calculation: The system captures the exact date and time of issuance. If a book is returned after the 7-day limit, it automatically calculates and displays a fine of Rs 50, removing manual calculation errors.

Availability Check: Before issuing a book, the code intelligently checks two things: does the library own the book, and are there any copies currently on the shelf? It prevents issuing a book that isn't physically there.

Duplicate Prevention: It ensures that one student cannot borrow multiple copies of the same book simultaneously, ensuring fair distribution of resources.
