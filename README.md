Project Title

Student Library Management System

Overview of the Project

This project is a console-based software designed to simplify the daily work of a librarian. In many schools, library records are still kept in big registers, which makes finding a book or calculating fines very slow and error-prone. My project solves this by automating the entire process. It allows the librarian to digitally track which books are in stock, who has borrowed them, and when they are due. It acts as a central system to ensure books are returned on time and inventory is always up to date.

Features

Live Stock Tracking: The system doesn't just list books; it counts them. If there are 5 copies of "Python Programming" and one is issued, the system instantly updates the available count to 4.

Issue System: It records the student's name and the exact date and time when a book is borrowed. It also prevents a single student from borrowing multiple copies of the same book.

Automatic Fine Calculation: This is the key feature. When a book is returned, the system compares the return date with the issue date. If the duration exceeds 7 days, it automatically shows a fine of Rs 50.

Dynamic Database: We can add new books to the library at any time without restarting the program.

Validation: It stops users from doing invalid actions, like trying to borrow a book that isn't in stock or returning a book that was never issued.

Technologies/Tools Used

Language: Python (Version 3.x) because it is easy to read and has powerful libraries.

Concepts Used: Object-Oriented Programming (Classes & Objects) for structure, and Dictionaries for efficient data storage.

Modules: The datetime module is used to handle real-time date and time tracking for issuing and returning.

IDE: The code was written and tested on VS Code (Visual Studio Code), but it runs on any standard Python IDLE.

Steps to Install & Run the Project

Install Python: Ensure Python is installed on your computer. You can check this by typing python --version in your command prompt.

Save the Code: Copy the source code and save it as a Python file, for example: Library_management.py.

Open Terminal: Open your command prompt (cmd) or terminal and navigate to the folder where you saved the file.

Run the Command: Type python Library_management.py and hit Enter.

Interact: The menu will appear on the screen, and you can start using the system by entering numbers (1-5).
<img width="916" height="872" alt="image" src="https://github.com/user-attachments/assets/d1eaf9f5-aa7b-453f-b927-7519f83d72ef" />
<img width="868" height="826" alt="image" src="https://github.com/user-attachments/assets/63392897-b0d1-43f9-b318-efee38a94a95" />
<img width="983" height="797" alt="image" src="https://github.com/user-attachments/assets/fe3ab02c-4040-412b-bcc5-5fb3426ed785" />
<img width="789" height="883" alt="image" src="https://github.com/user-attachments/assets/c3898356-fef0-4ec0-8097-cbada47c76ae" />
<img width="775" height="721" alt="image" src="https://github.com/user-attachments/assets/7a8a7119-27a3-4179-99f9-1d3ac0df81e6" />



Instructions for Testing

To verify that the project works perfectly, follow these test cases:

Test Availability: Select Option 1 to see the list of books. Note the quantity of "Harry Potter".

Test Issuing: Select Option 2. Enter your name and "Harry Potter". You will see a success message. Check the list again (Option 1)—the quantity should be one less.

Test Out-of-Stock: Try to issue a book that has 0 quantity. The system should politely refuse.

Test Returning & Fine: Select Option 3. Enter the same name and book title.

Note: Since we can't wait 7 days in real-time during a demo, you can verify the logic by temporarily changing the code limit from > 7 to > 0 seconds/days to see the fine message appear immediately.

Test Adding Stock: Select Option 4, add a new book name and quantity, and check Option 1 to see if it appears in the list.
