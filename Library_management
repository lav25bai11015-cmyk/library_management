import datetime

class Library:
    def __init__(self, books_dict):
        # We use a dictionary here so we can store the Book Name AND its Quantity
        # Example: {'Python Basics': 5, 'Harry Potter': 3}
        self.books = books_dict
        
        # This nested dictionary tracks who borrowed what and when
        # Structure: {'Book Name': {'User Name': issue_date}}
        self.issued_books = {}

    def display_available_books(self):
        print("\n------------------------------------")
        print("Current Library Stock:")
        print(f"{'Book Name':<30} | {'Sets Available'}")
        print("------------------------------------")
        # .items() gives us both key (book) and value (quantity) at once
        for book, quantity in self.books.items():
            print(f"{book:<30} | {quantity}")
        print("------------------------------------")

    def lend_book(self, user_name, book_name):
        # 1. Check if the book actually exists in our library list
        if book_name not in self.books:
            print(f"\nError: We don't have '{book_name}' in our library catalog.")
            return

        # 2. Check if we have physical copies (sets) available
        if self.books[book_name] > 0:
            
            # 3. Check if this specific user already has this specific book
            # We don't want one person hoarding all copies of the same book!
            if book_name in self.issued_books and user_name in self.issued_books[book_name]:
                print(f"\nSorry {user_name}, you already have a copy of this book issued.")
                return

            now = datetime.datetime.now()
            
            # If this is the first time this book is being borrowed by anyone, 
            # create a new dictionary entry for it in issued_books
            if book_name not in self.issued_books:
                self.issued_books[book_name] = {}
            
            # Record the user and time
            self.issued_books[book_name][user_name] = now
            
            # Decrease the available stock by 1
            self.books[book_name] -= 1
            
            print(f"\nSuccess! '{book_name}' has been issued to {user_name}.")
            print(f"Issued on: {now.strftime('%Y-%m-%d %H:%M:%S')}")
            print("NOTE: Please return within 7 days to avoid a fine of Rs 50.")
        
        else:
            print(f"\nSorry, all copies of '{book_name}' are currently out/borrowed.")

    def return_book(self, user_name, book_name):
        # We check if the book is in issued_books AND if this specific user has it
        if book_name in self.issued_books and user_name in self.issued_books[book_name]:
            
            issue_date = self.issued_books[book_name][user_name]
            return_date = datetime.datetime.now()

            # Calculate the difference in time
            delta = return_date - issue_date
            days_passed = delta.days

            print(f"\nProcessing return for: {book_name}")
            print(f"Returned by: {user_name}")
            print(f"Days kept: {days_passed}")

            # Calculate Fine (Rs 50 if kept for more than 7 days)
            fine = 0
            if days_passed > 7:
                print("Status: Overdue! (Limit is 7 days)")
                fine = 50
            else:
                print("Status: Returned on time.")
            
            print(f"Fine to Pay: Rs {fine}")

            # Remove the user from the issued record
            del self.issued_books[book_name][user_name]
            
            # If no one else has borrowed this book, we can remove the empty dictionary key
            if not self.issued_books[book_name]:
                del self.issued_books[book_name]

            # Increase the stock back by 1
            self.books[book_name] += 1
            print("Stock updated. Thank you!")

        else:
            print(f"\nError: No record found for {user_name} having borrowed '{book_name}'.")

    def add_book(self, book_name, quantity):
        # If book already exists, just add the new stock to old stock
        if book_name in self.books:
            self.books[book_name] += quantity
        else:
            # If it's a new book, create a new entry
            self.books[book_name] = quantity
            
        print(f"\nAdded {quantity} sets of '{book_name}'. Total available: {self.books[book_name]}")

# Main execution block
if __name__ == "__main__":
    # Pre-filling some data for testing
    initial_stock = {
        "Python Programming": 5,
        "Harry Potter": 3,
        "Cengage": 10,
        "Calculus": 2
    }
    
    my_library = Library(initial_stock)
    
    print("Welcome to the School Library System")

    while True:
        print("\n=== LIBRARY MENU ===")
        print("1. Display Available Books")
        print("2. Issue a Book")
        print("3. Return a Book")
        print("4. Add New Stock")
        print("5. Exit")
        
        choice = input("Enter choice (1-5): ")

        if choice == "1":
            my_library.display_available_books()
        
        elif choice == "2":
            my_library.display_available_books()
            book = input("Enter Book Name: ")
            user = input("Enter Student Name: ")
            my_library.lend_book(user, book)

        elif choice == "3":
            # We need the user name to ensure we return the right person's copy
            book = input("Enter Book Name to return: ")
            user = input("Enter Student Name: ")
            my_library.return_book(user, book)
        
        elif choice == "4":
            book = input("Enter Book Name: ")
            try:
                qty = int(input("Enter Quantity to add: "))
                my_library.add_book(book, qty)
            except ValueError:
                print("Invalid input. Quantity must be a number.")

        elif choice == "5":
            print("Exiting Library System. Have a nice day!")
            break
            
        else:
            print("Invalid selection. Please try again.")
