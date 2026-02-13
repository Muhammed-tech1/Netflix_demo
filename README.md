# 🎬 Netflix Content Analytics – Advanced SQL Case Study

This project is a **hands-on SQL analytics challenge** that simulates working as a **Data Analyst / Analytics Engineer at Netflix**.

The goal of this project is to analyze **content performance, availability, and viewer engagement** across movies and TV shows using **real-world business questions**.

---

## 📌 Project Overview

In this case study, I solved **15 business-driven SQL problems** covering:

- Content performance analysis
- Data quality & integrity checks
- Regional ranking insights
- Viewership trends
- Content coverage auditing

This project helped me strengthen my **SQL querying, analytical thinking, and data storytelling skills**.

---

## 🛠 Tools & Technologies

- **PostgreSQL**
- Advanced SQL
- Relational Database Design
- Analytical Problem Solving

---

## 🧠 Key SQL Concepts Used

- `DISTINCT ON`
- Window Functions (`ROW_NUMBER`)
- INNER JOIN, LEFT JOIN, FULL OUTER JOIN
- Subqueries & CTEs (`WITH`)
- Aggregation (`SUM`, `GROUP BY`)
- Data Integrity Audits
- Business-driven analytics logic

---

## 📊 Business Problems Solved

1. Latest performance snapshot per movie  
2. Most recent season performance per TV show  
3. Movies with actual viewership  
4. Seasons with recorded engagement  
5. Movies without any viewership  
6. All TV shows and seasons (even unwatched)  
7. Orphaned viewing records detection  
8. Content coverage audit  
9. Movies never viewed  
10. Seasons without views  
11. Broken foreign key reference detection  
12. Unified data integrity audit  
13. Weekly performance dashboard  
14. Global availability vs performance  
15. **Top-performing content by locale**

---

## 🏆 Example Highlight — Top Performing Content by Locale

```sql
WITH tv_summary AS (
	SELECT 
		t.title, 'TV-show' AS content_type, t.locale, v.view_rank
	FROM tv_show t
	JOIN season s ON t.id = s.tv_show_id
	JOIN view_summary v ON s.id = v.season_id
),
movie_summary AS (
	SELECT 
		m.title, 'Movie' AS content_type, m.locale, v.view_rank
	FROM movie m
	JOIN view_summary v ON m.id = v.movie_id	
),
combined AS (
	SELECT * FROM tv_summary
	UNION ALL
	SELECT * FROM movie_summary 
)
SELECT DISTINCT ON (locale)
	title,
	content_type,
	locale,
	view_rank
FROM combined
ORDER BY locale, view_rank;
🚀 What I Learned
This project helped me develop:

Strong SQL query writing skills

Business-focused analytical thinking

Data quality auditing mindset

Understanding of real-world analytics workflows

Confidence working with complex joins and logic

🎯 About Me
I am a Computer Science student and Data Science learner actively building a strong foundation in:

Data Analysis

SQL

Python

Machine Learning

Exploratory Data Analysis (EDA)

I'm focused on hands-on projects, portfolio building, and continuous learning.

🔗 Connect With Me
GitHub: https://github.com/Muhammed-tech1
LinkedIn: https://www.linkedin.com/in/muhammed-bello-abdullahi-1912603a9/
Twitter (X): https://x.com/Muhamme84886612

⭐ If you find this project helpful, feel free to star the repository!
