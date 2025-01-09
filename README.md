
# SQLite Database README

## Overview
This repository contains an SQLite database designed for managing relationships between students, courses, and associated modules. The database is structured to support operations such as tracking student enrollments, course modules, and student addresses.

The database file is created using SQLite and can be managed using tools like [Beekeeper Studio](https://www.beekeeperstudio.io/). Below is a detailed description of the database schema and its tables.

## Database Schema

### Tables

#### 1. `students`
Stores information about students.
- **Columns:**
  - `id`: INTEGER PRIMARY KEY AUTOINCREMENT
  - `name`: TEXT NOT NULL

#### 2. `courses`
Stores information about available courses.
- **Columns:**
  - `id`: INTEGER PRIMARY KEY AUTOINCREMENT
  - `name`: TEXT NOT NULL

#### 3. `students_courses`
Tracks the enrollment of students in courses.
- **Columns:**
  - `id`: INTEGER PRIMARY KEY AUTOINCREMENT
  - `student_id`: INTEGER NOT NULL (Foreign Key: references `students(id)`)
  - `course_id`: INTEGER NOT NULL (Foreign Key: references `courses(id)`)

#### 4. `course_modules`
Stores information about course modules.
- **Columns:**
  - `id`: INTEGER PRIMARY KEY AUTOINCREMENT
  - `name`: TEXT NOT NULL
  - `course_id`: INTEGER NOT NULL (Foreign Key: references `courses(id)`)

#### 5. `student_adress`
Stores the address information of students.
- **Columns:**
  - `id`: INTEGER PRIMARY KEY AUTOINCREMENT
  - `student_id`: INTEGER UNIQUE NOT NULL (Foreign Key: references `students(id)`)
  - `street`: TEXT NOT NULL
  - `city`: TEXT NOT NULL

### Auto-Generated Table

#### `sqlite_sequence`
This table is automatically managed by SQLite to keep track of the AUTOINCREMENT values for tables.

## Example Data
Here are some examples of data entries in the database:

### Students
- Pedro Quarto
- Ronan Bombom
- Carla Perez

### Courses
- Portuguese Language Fundamentals I
- French Language Fundamentals III
- English Language Fundamentals II

### Course Modules
- Fundamentals of Portuguese Language I
- Fundamentals of French Language II
- Fundamentals of English Language III

### Student Addresses
- Street: Rua Itamaracá, City: Belo Horizonte
- Street: Rua São João, City: São Paulo

## Usage

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd <repository-name>
   ```

2. **Install SQLite**
   Ensure SQLite is installed on your system. You can download it from the [SQLite official website](https://sqlite.org/).

3. **Open the Database**
   Open the database file using SQLite or a GUI tool like Beekeeper Studio:
   ```bash
   sqlite3 <database-file>.sqlite
   ```

4. **Run Queries**
   Use SQL commands to interact with the database:
   ```sql
   SELECT * FROM students;
   SELECT * FROM courses;
   ```

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request with your improvements.

## Contact
For any questions or feedback, feel free to open an issue in the repository or contact the maintainer.
