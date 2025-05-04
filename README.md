# Introduction

Dive into the data job market! Focusing on data analyst roles, this project explores:
* Top-paying jobs
* In-demand skills
* Optimal skills: where high demand meets high salary in data analytics.

SQL queries? Check them out here: [project_sql folder](/project_sql/)

# Background

Driven by a quest to navigate the data analyst job market effectively, this project was born from a desire to pinpoint top-paid and in-demand skills, streamlining others work to find optimal jobs.

Data hails from [Luke Barousse SQL Course](https://lukebarousse.com/sql). Thanks to his course and content i am to do these insights.

# The questions I want to answer through my SQL queries were:

1. What are the top-paying data analyst jobs?
2. What skills are most in demand for data analyst?
3. What skills are most in demand for data analysts?
4. Which skills are associated with higher salaries?
5. what are the most optimal skills to learn?

# Tools I Used
For this project, I harnessed the power of several key tools:
- **SQL:** The backbone of my analysis, allowing me to query the database and unearth critical insights.
- **PostgreSQL:** For data storage
- **Visual Studio Code:** 
- **Git & GitHub:** For version control and sharing my scripts and analysis

# The Analysis
```sql
SELECT 
    skills,
    ROUND(AVG(salary_year_avg),1) AS avg_salary
FROM job_postings_fact
INNER JOIN skills_job_dim ON job_postings_fact.job_id = skills_job_dim.job_id
INNER JOIN skills_dim ON skills_job_dim.skill_id = skills_dim.skill_id

WHERE
    job_title_short = 'Data Engineer' AND
    salary_year_avg IS NOT NULL AND
    job_work_from_home = TRUE
GROUP BY
    skills

ORDER BY
    avg_salary DESC
LIMIT 10
```
# What I Learned

# Conclusion

