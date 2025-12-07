# Student Record Management System (SRMS)

A comprehensive C-based student management application with both **GUI** and **CLI** interfaces for seamless student record management.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [System Requirements](#system-requirements)
- [Installation & Setup](#installation--setup)
- [Usage](#usage)
  - [GUI Version](#gui-version)
  - [CLI Version](#cli-version)
- [Project Structure](#project-structure)
- [Student Data Fields](#student-data-fields)
- [Features & Functionality](#features--functionality)
- [File Format](#file-format)

---

## 🎯 Overview

The **Student Record Management System (SRMS)** is a robust application designed to manage student information efficiently. It provides two distinct interfaces:

- **`student_gui.exe`** - Graphical User Interface (GUI) for an intuitive user experience
- **`srms.exe`** - Command Line Interface (CLI) for lightweight, scriptable operations

Both versions manage the same underlying student database, allowing you to switch between interfaces while maintaining data consistency.

---

## ✨ Features

- ✅ **Add Students** - Register new students with complete information
- ✅ **View Students** - Display all student records or search for specific students
- ✅ **Search Functionality** - Find students by ID, name, or other criteria
- ✅ **Update Records** - Modify existing student information and grades
- ✅ **Delete Records** - Remove student records from the system
- ✅ **Grade Calculation** - Automatic calculation of:
  - Total marks (sum of all 5 subjects)
  - Percentage
  - Letter grade (A, B, C, D, F)
- ✅ **Persistent Storage** - All data saved in binary format (`students.dat`)
- ✅ **Dual Interface** - Choose between GUI or CLI based on your needs

---

## 🖥️ System Requirements

- **Operating System:** Windows (XP SP3 or later)
- **Processor:** Intel Pentium or equivalent
- **RAM:** 512 MB minimum
- **Disk Space:** 10 MB free space
- **Libraries:** Windows API (for GUI version)

> **Note:** Both executables are compiled for Windows. Linux/macOS users will need to recompile the source files.

---

## 📦 Installation & Setup

### Step 1: Download/Extract Files
Extract all project files to a folder (e.g., `C:\SRMS` or `D:\CCC_Project`)

### Step 2: Verify Files
Ensure you have the following files:
```
student_gui.exe          (GUI executable)
srms.exe                 (CLI executable)
students.dat             (Database file - auto-created on first run)
```

### Step 3: Run the Application
No installation required! Both executables are standalone and ready to use.

---

## 🚀 Usage

### GUI Version (`student_gui.exe`)

**Recommended for:** Regular users, data entry personnel, visual preference

#### How to Run:
1. Double-click `student_gui.exe` from Windows Explorer
2. Or run in Command Prompt:
   ```bash
   student_gui.exe
   ```

#### GUI Features:
- **Login/Register Screen**
  - Create a new account or log in with existing credentials
  - Secure authentication system
  
- **Main Dashboard**
  - Add New Student
  - View All Students
  - Search Student (by ID)
  - Update Student Record
  - Delete Student Record
  - Exit Application

- **Data Entry Form**
  - Fill in all student details
  - Enter marks for 5 subjects:
    - Math
    - Physics
    - Chemistry
    - English
    - Computer Science
  - Automatic grade calculation upon save

#### Example Workflow:
```
1. Launch student_gui.exe
2. Register/Login
3. Click "Add Student" button
4. Enter student information:
   - Name
   - Age
   - Gender
   - Address
   - Phone
   - Email
   - Subject Marks (out of 100)
5. Click "Save"
6. View records using "View All Students"
```

---

### CLI Version (`srms.exe`)

**Recommended for:** Quick operations, batch processing, automation, minimal resources

#### How to Run:
1. Open Command Prompt
2. Navigate to the project directory:
   ```bash
   cd D:\CCC_Project
   ```
3. Run the executable:
   ```bash
   srms.exe
   ```

#### CLI Menu Options:
```
========================================
   STUDENT RECORD MANAGEMENT SYSTEM
========================================

1. Add Student
2. View All Students
3. Search Student
4. Update Student
5. Delete Student
6. Exit

Enter your choice: _
```

#### Example Workflow:

**Adding a Student:**
```
Enter your choice: 1
Enter Student Name: John Doe
Enter Age: 20
Enter Gender (M/F): M
Enter Address: 123 Main Street
Enter Phone: 9876543210
Enter Email: john@example.com
Enter Math Marks: 85
Enter Physics Marks: 90
Enter Chemistry Marks: 88
Enter English Marks: 92
Enter Computer Marks: 95
Student added successfully!
```

**Viewing All Students:**
```
Enter your choice: 2
ID | Name      | Age | Marks | Grade | %
1  | John Doe  | 20  | 450   | A     | 90.0
2  | Jane Smith| 19  | 420   | A     | 84.0
```

**Searching a Student:**
```
Enter your choice: 3
Enter Student ID to search: 1
ID: 1
Name: John Doe
Age: 20
Gender: M
Address: 123 Main Street
Phone: 9876543210
Email: john@example.com
Math: 85
Physics: 90
Chemistry: 88
English: 92
Computer: 95
Total: 450
Percentage: 90.0
Grade: A
```

**Updating a Student:**
```
Enter your choice: 4
Enter Student ID to update: 1
[Display current data]
Enter new marks for Math: 87
Enter new marks for Physics: 92
Student updated successfully!
```

**Deleting a Student:**
```
Enter your choice: 5
Enter Student ID to delete: 1
Student deleted successfully!
```

---

## 📁 Project Structure

```
CCC_Project/
├── student_gui.exe          # GUI executable (compiled binary)
├── srms.exe                 # CLI executable (compiled binary)
├── students.dat             # Student database (binary format)
├── README.md                # This file
├── gui.c                    # GUI implementation source code
├── gui.h                    # GUI header file
├── srms.c                   # CLI implementation source code
├── student.c                # Student logic implementation
└── student.h                # Student structure & function definitions
```

---

## 👤 Student Data Fields

Each student record contains the following information:

| Field | Type | Constraints |
|-------|------|-------------|
| **ID** | Integer | Auto-generated, unique |
| **Name** | String | Max 50 characters |
| **Age** | Integer | Positive number |
| **Gender** | Character | M or F |
| **Address** | String | Max 100 characters |
| **Phone** | String | Up to 15 digits |
| **Email** | String | Max 50 characters |
| **Math Marks** | Float | 0 - 100 |
| **Physics Marks** | Float | 0 - 100 |
| **Chemistry Marks** | Float | 0 - 100 |
| **English Marks** | Float | 0 - 100 |
| **Computer Marks** | Float | 0 - 100 |
| **Total** | Float | Auto-calculated (sum of all marks) |
| **Percentage** | Float | Auto-calculated (Total/5) |
| **Grade** | Character | A, B, C, D, or F (auto-calculated) |

---

## 🎓 Features & Functionality

### Grade Calculation System

Grades are automatically calculated based on percentage:

| Percentage Range | Grade |
|-----------------|-------|
| 90 - 100 | A |
| 80 - 89 | B |
| 70 - 79 | C |
| 60 - 69 | D |
| Below 60 | F |

### Data Persistence

All student records are saved in `students.dat` - a binary file that:
- Automatically creates on first run
- Persists data between sessions
- Works with both GUI and CLI versions
- Can be backed up like any regular file

---

## 📊 File Format

The `students.dat` file stores student records in binary format using the following structure:

```c
typedef struct {
    int id;                      // Student ID
    char name[50];               // Student Name
    int age;                      // Age
    char gender;                  // Gender (M/F)
    char address[100];            // Address
    char phone[15];               // Phone Number
    char email[50];               // Email Address
    float math;                   // Math Marks
    float physics;                // Physics Marks
    float chemistry;              // Chemistry Marks
    float english;                // English Marks
    float computer;               // Computer Marks
    float total;                  // Total Marks (calculated)
    float percentage;             // Percentage (calculated)
    char grade;                   // Grade Letter (calculated)
} Student;
```

---

## 🔧 Troubleshooting

| Issue | Solution |
|-------|----------|
| **Executable won't run** | Ensure you're on Windows; check system architecture (32-bit/64-bit match) |
| **"students.dat not found"** | Don't worry! The system will create it automatically on first use |
| **GUI not displaying** | Ensure Windows API libraries are available; try CLI version instead |
| **Cannot save data** | Check file permissions in the project folder |
| **Data seems lost** | Verify `students.dat` exists; it contains all records |

---

## 💡 Tips & Best Practices

1. **Regular Backups:** Periodically copy `students.dat` to a safe location
2. **Consistent Data Entry:** Follow a standard naming convention for consistency
3. **Email Validation:** Manually verify email addresses during entry
4. **Phone Format:** Store phone numbers in a consistent format
5. **GUI vs CLI:** Use GUI for data entry, CLI for quick lookups
6. **Batch Operations:** Use CLI for scripting multiple operations

---

## 📝 Notes

- Both applications share the same database (`students.dat`)
- You can switch between GUI and CLI versions without losing data
- The system automatically calculates total, percentage, and grade
- Student IDs are auto-generated starting from 1 and increment with each new student
- All marks should be entered on a scale of 0-100

---

## 👨‍💼 Support

For issues or questions:
1. Check the Troubleshooting section
2. Verify all input data is in the correct format
3. Ensure the project folder has read/write permissions
4. Try the alternative interface (GUI ↔ CLI)

---

**Version:** 1.0  
**Last Updated:** December 2025  
**License:** Open Source

---

## 🚀 Quick Start Checklist

- [ ] Extract all files to a folder
- [ ] Double-click `student_gui.exe` OR run `srms.exe` from Command Prompt
- [ ] Add your first student record
- [ ] View and manage records
- [ ] Backup `students.dat` regularly

Enjoy using the Student Record Management System! 📚
