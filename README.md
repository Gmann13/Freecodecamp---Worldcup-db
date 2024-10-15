
# World Cup Database and Reporting System

**Description:**  
This project involves creating a PostgreSQL database to store World Cup match data and generate reports from it. It includes:
- A set of SQL scripts to create tables for storing match and team data.
- A shell script that automates the process of inserting data from a CSV file into the database.
- SQL queries to generate reports based on the stored data.

---

## Features

- **Database Schema:** Includes tables for `teams` and `games` to store World Cup match data.
- **Shell Script Automation:** A shell script automates the data insertion process, reading from a CSV file.
- **Reports:** SQL queries that generate detailed reports, such as match results and team performance.

---

## Project Components

1. **SQL Scripts:**
   - Create the necessary database schema with tables (`teams` and `games`) and constraints.
   - Insert World Cup match data into the `teams` and `games` tables.
   
2. **Shell Script (`insert_data.sh`):**
   - Automates the process of inserting data from a CSV file (`games.csv`) into the database.
   - The script checks for existing teams before inserting new ones, avoiding duplicates.
   - It also handles inserting match data by relating teams using their IDs.

3. **Report Generation Queries:**
   - SQL queries that can be used to generate reports from the `games` and `teams` tables, such as total wins, highest-scoring matches, and team statistics.

---

## Installation

### Prerequisites

- **PostgreSQL:** Make sure PostgreSQL is installed and running on your machine.
- **Shell Environment:** The shell script is written for a Unix-like environment (Linux, macOS).

### Steps to Set Up

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/worldcup-db.git
   cd worldcup-db
   ```

2. **Set up the PostgreSQL database:**
   - Log in to PostgreSQL and run the SQL script to create the database and tables:
     ```bash
     psql -U postgres -f worldcup.sql
     ```

3. **Run the Shell Script:**
   - To insert the data from the `games.csv` file:
     ```bash
     ./insert_data.sh
     ```

4. **Generate Reports:**
   - You can run specific SQL queries to generate reports from the data stored in the `games` and `teams` tables:
     ```bash
     psql -U postgres -d worldcup -f reports.sql
     ```

---

## Usage

1. **Insert Data:**
   - The `insert_data.sh` script automates the data insertion process. Simply run the script to populate the database with data from the `games.csv` file.

2. **Query Data:**
   - Use the SQL queries provided in the `reports.sql` file to generate various reports from the database.

---

## Database Schema

- **Teams Table:**  
  Stores information about the teams, including their ID and name.
  - Columns: `team_id`, `name`.

- **Games Table:**  
  Stores match data, including the teams that played, the year of the match, and the score.
  - Columns: `game_id`, `year`, `round`, `winner_id`, `opponent_id`, `winner_goals`, `opponent_goals`.

---

## Contributing

Contributions are welcome! To contribute:

1. **Fork the repository.**
2. **Create a new branch for your feature or fix:**
   ```bash
   git checkout -b feature-name
   ```
3. **Commit your changes:**
   ```bash
   git commit -m "Add new feature"
   ```
4. **Push to the branch:**
   ```bash
   git push origin feature-name
   ```
5. **Create a pull request.**

---
