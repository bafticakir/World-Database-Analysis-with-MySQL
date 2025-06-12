🌍 World Database Analysis with MySQL

Welcome to a structured exploration of the **World** database!  
is project dives into global data covering 🌐 countries, 🏙️ cities, and 🗣️ languages – ideal for practising SQL and relational database analysis.

![3e64dae3-4ba5-42ff-9aaf-2cb840fadecc](https://github.com/user-attachments/assets/7535afc2-ee7e-44b0-a5aa-c3157362113c)


---

## 📦 Dataset Overview

### 🗺️ `country`
Contains:
- 🌍 `Name`, `Continent`, `Region`
- 👨‍👩‍👧‍👦 `Population`, 🏞️ `SurfaceArea`, 💉 `LifeExpectancy`
- 🏛️ `GovernmentForm`, 💰 `GNP`, and more

### 🏙️ `city`
Includes:
- 🏘️ `Name`, `District`, `Population`
- 🔗 Linked to `country` via `CountryCode`

### 🗣️ `countrylanguage`
Describes:
- 🌐 `Language`, ✅ `IsOfficial`, 📊 `Percentage`
- 🔗 Linked to `country` via `CountryCode`

---

## 🧭 ER Diagram

📌 Relationships:
- `city.CountryCode` ➝ `country.Code`  
- `countrylanguage.CountryCode` ➝ `country.Code`

![ER Diagram](./path-to-your-diagram.png)  
<sub>*Replace the image path with your actual diagram file*</sub>

---

## 🔍 Sample SQL Queries

### 🏙️ Top 10 Most Populated Cities
```sql
SELECT Name, Population 
FROM city 
ORDER BY Population DESC 
LIMIT 10;
```

### 🌍 Countries Over 100M Population
```sql
SELECT Name, Population 
FROM country 
WHERE Population > 100000000;
```

### 🗣️ Official Languages by Continent
```sql
SELECT c.Continent, cl.Language 
FROM countrylanguage cl
JOIN country c ON cl.CountryCode = c.Code
WHERE cl.IsOfficial = 'T';
```

### 🧬 Average Life Expectancy per Continent
```sql
SELECT Continent, AVG(LifeExpectancy) AS AvgLife
FROM country
GROUP BY Continent;
```

---

## 🎯 Objectives

- 🤝 Practise JOINs & relationships
- 📊 Use aggregate functions & filtering
- 🧠 Understand real-world ER models
- 🔄 Work with normalised data structures

---

## ⚙️ Tech Stack

- 🛢️ MySQL 8  
- 🧰 MySQL Workbench  
- 💻 SQL (DDL + DML)

---

## 🙋‍♂️ Author

**Bafti Çakır**  
📍 Based in the UK | Data Analytics 
🔗 [View Project on GitHub](https://github.com/bafticakir/World-Database-Analysis)

---


> Created 🔥 by **Bafti Cakir**
