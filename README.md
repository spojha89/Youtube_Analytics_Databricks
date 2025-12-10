📺 YouTube Trending Video Analyzer on Databricks

Find top trending YouTube videos by duration category and deliver insights via automated email

This project discovers top 10 trending / most viewed YouTube videos across three categories — Short, Medium, and Long — using the YouTube Data API.
The results are processed in Databricks using PySpark and automatically emailed to users through Databricks Jobs.

🚀 Features
✅ 1. YouTube API Integration

Searches YouTube based on keyword, category, or region.

Fetches most viewed or trending videos.

Supports all duration filters:

Short: < 4 minutes

Medium: 4–20 minutes

Long: > 20 minutes

✅ 2. Intelligent Duration-Based Ranking

Finds Top 10 videos for each duration class.

Extracts metadata:

Title

Channel name

View count

Duration

Publish date

Video URL

✅ 3. Databricks-Based ETL

Uses PySpark/Python scripts to process API responses.

Cleans, normalizes, and structures YouTube metadata.

Stores output in DBFS / Delta tables.

✅ 4. Automated Email Delivery (Databricks Jobs)

DATBRICKS JOB:

Runs notebooks on schedule (daily/hourly).

Generates formatted email content containing:

Top 10 short videos

Top 10 medium videos

Top 10 long videos

Sends results to your email inbox.

Supports custom sender + receiver emails.

✅ 5. Configurable Search

Set search terms such as:

“Technology reviews”

“Garments business vlogs in India”

“Top finance creators”

“Machine learning tutorials”

📁 Repository Structure
/notebooks
    ├── youtube_search_short.py
    ├── youtube_search_medium.py
    ├── youtube_search_long.py


🧱 Architecture Overview
YouTube Data API → Databricks Notebook → Data Transformation → Job Scheduler → Email Delivery

Components:

Data Extraction: YouTube Data API v3

Processing: PySpark + Python

Scheduling: Databricks Jobs

Messaging: SMTP-based email integration

🔧 Technologies Used
Category	Technologies
Platform	Databricks
Languages	Python, PySpark
Cloud Storage	DBFS / Delta 
External API	YouTube Data API v3
Messaging	SMTP (Gmail, Outlook, etc.)
Automation	Databricks Jobs
🏗️ Setup & Execution
1. Generate a YouTube API Key

Get it from the Google Cloud Console → YouTube Data API v3.

2. Add key to google secret and reference it in databricks notebook

3. Configure Email Credentials

Store email credentials in the same secret scope.

4. Run Notebooks

Execute extraction notebooks to verify results.

5. Create a Databricks Job

Task 1 → Run the extraction notebook

Task 2 → Run the email notebook

Set daily schedule

6. Receive Email

You will get a neatly formatted email containing the top videos.

📧 Sample Email Output (Text Format)
TOP 10 SHORT VIDEOS
1. Title - Channel - Views - URL
2. ...
TOP 10 MEDIUM VIDEOS
1. ...
TOP 10 LONG VIDEOS
1. ...


📌 Future Enhancements

Store output in Delta tables for historical tracking

Create Power BI / Tableau dashboards with monthly data

Track trending videos over time with MLflow

Send email with HTML table formatting
