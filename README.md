# Address Book System

A menu-driven command-line address book written in **C**. It lets you create, search, edit, delete and list contacts, and keeps them saved in a CSV file so your data is still there the next time you run the program.

## Features

- **Create contact** – add a new contact with name, phone number and email
- **Search contact** – find a contact by name, phone number or email
- **Edit contact** – update the name, phone or email of an existing contact
- **Delete contact** – remove a contact from the address book
- **List all contacts** – display every saved contact
- **Persistent storage** – contacts are loaded from `Addressbook.csv` at startup and written back on *Save and Exit*
- **Dummy data support** – optional sample contacts via `populate.c`

## Project Structure

```
address-book-system/
├── main.c          # Entry point and main menu loop
├── contact.c       # Contact operations (create, search, edit, delete, list)
├── contact.h       # Contact / AddressBook structures and function declarations
├── file.c          # Save and load contacts to/from CSV
├── file.h          # File handling declarations
├── populate.c      # Sample (dummy) contact data
├── populate.h      # Populate declarations
├── Addressbook.csv # Contact data file
└── README.md
```

## Data Structures

```c
#define MAX_CONTACTS 100

typedef struct Contact {
    char name[50];
    char phone[20];
    char email[50];
} Contact;

typedef struct {
    Contact contacts[MAX_CONTACTS];
    int contactCount;
} AddressBook;
```

## Getting Started

### Prerequisites

- A C compiler such as `gcc`

### Clone the repository

```bash
git clone https://github.com/narendra8010/address-book-system.git
cd address-book-system
```

### Compile

```bash
gcc main.c contact.c file.c populate.c -o address
```

### Run

```bash
./address
```

## Usage

When the program starts, the following menu is displayed:

```
Address Book Menu:
1. Create contact
2. Search contact
3. Edit contact
4. Delete contact
5. List all contacts
6. Save and Exit
Enter your choice:
```

| Option | Action |
|--------|--------|
| 1 | Enter a name, phone and email to add a new contact |
| 2 | Choose to search by name, phone or email, then enter the search key |
| 3 | Enter a contact's name, then choose which field to edit |
| 4 | Enter the name of the contact to delete |
| 5 | Print all contacts |
| 6 | Save all contacts to `Addressbook.csv` and exit |

> **Note:** Choose option **6** to exit so your changes are saved to the file.

### Sample Session

```
Enter your choice: 1
Enter Name : John Doe
Enter Phone : 9876543210
Enter Email : john@example.com
Contact Added Successfully
```

## Data Storage

Contacts are stored in `Addressbook.csv`, one contact per line in the format:

```
name,phone,email
```

Example:

```
John Doe,9876543210,john@example.com
Jane Smith,9123456780,jane@example.com
```

The file is read automatically when the program starts and overwritten when you choose **Save and Exit**.

## Using Sample Data

To start with sample contacts, open `contact.c` and uncomment this line inside the `initialize()` function:

```c
// populateAddressBook(addressBook);
```

Then recompile and run the program.

## Concepts Used

- Structures and arrays
- Pointers and passing structures by reference
- Modular programming with multiple source and header files
- File handling (`fopen`, `fprintf`, `fscanf`, `fclose`)
- String handling (`strcmp`)
- Menu-driven programs using `switch` and `do-while`

## Author

**narendra8010** – [GitHub Profile](https://github.com/narendra8010)
