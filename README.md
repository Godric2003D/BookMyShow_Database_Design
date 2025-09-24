# BookMyShow Theatre Show Database Design – Debayan Ray

> A relational database project simulating a movie ticketing system similar to BookMyShow.  
> Includes table designs, sample data, normalization, and SQL queries to fetch shows by date and theatre.

---

## About the Project
This project demonstrates a SQL-based database design for a movie ticketing scenario.  
It includes:

- Complete list of tables with attributes
- Sample rows for each table
- SQL statements to create tables (1NF, 2NF, 3NF, BCNF)
- SQL queries to fetch shows by date and theatre

---

## Tables and Attributes

### 1. Theatre
| Attribute   | Type | Description |
|------------|------|-------------|
| theatre_id | INT (PK) | Unique theatre identifier |
| name       | VARCHAR(100) | Theatre name |
| location   | VARCHAR(150) | City/location |

### 2. Movie
| Attribute   | Type | Description |
|------------|------|-------------|
| movie_id    | INT (PK) | Unique movie identifier |
| title       | VARCHAR(150) | Movie title |
| language    | VARCHAR(50)  | Movie language |
| format      | VARCHAR(50)  | e.g., 2D, 3D, 4DX |
| certificate | VARCHAR(10)  | e.g., UA, U |

### 3. ShowDetails
| Attribute   | Type | Description |
|------------|------|-------------|
| show_id     | INT (PK) | Unique show identifier |
| theatre_id  | INT (FK → Theatre) | Theatre reference |
| movie_id    | INT (FK → Movie) | Movie reference |
| show_date   | DATE | Date of show |
| show_time   | TIME | Time of show |
| screen      | VARCHAR(20) | Screen number/name |

---

## Sample Data

### Theatre
| theatre_id | name                  | location   |
|-----------|----------------------|-----------|
| 1         | PVR: Nexus Forum Mall | Bangalore |
| 2         | Inox: City Centre     | Kolkata   |
| 3         | Miraj Cinemas         | Pune      |
| 4         | UpTown Hall           | Dehli     |

### Movie
| movie_id | title                         | language | format | certificate |
|----------|-------------------------------|---------|--------|-------------|
| 1        | Dasara                         | Telugu  | 2D     | UA          |
| 2        | Kisi Ka Bhai Kisi Ki Jaan      | Hindi   | 2D     | UA          |
| 3        | Tu Jhoothi Main Makkaar        | Hindi   | 2D     | UA          |
| 4        | Avatar: The Way of Water       | English | 3D     | UA          |

### ShowDetails
| show_id | theatre_id | movie_id | show_date  | show_time  | screen   |
|---------|------------|----------|-----------|-----------|---------|
| 1       | 1          | 1        | 2023-04-25 | 12:15:00 | Screen 1 |
| 2       | 3          | 2        | 2023-04-25 | 13:00:00 | Screen 2 |
| 3       | 2          | 2        | 2023-04-25 | 16:10:00 | Screen 2 |
| 4       | 1          | 2        | 2023-04-25 | 18:20:00 | Screen 2 |
| 5       | 4          | 2        | 2023-04-25 | 19:20:00 | Screen 2 |
| 6       | 3          | 2        | 2023-04-25 | 22:30:00 | Screen 2 |
| 7       | 1          | 3        | 2023-04-25 | 13:15:00 | Screen 3 |
| 8       | 4          | 4        | 2023-04-25 | 19:20:00 | Screen 4 |

