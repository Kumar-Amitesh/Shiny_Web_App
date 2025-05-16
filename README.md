# 📰 News Management System

## 📄 Overview

This is a comprehensive full-stack **News Management System** built with:

* **Frontend**: R Shiny Dashboard
* **Backend**: Plumber API Server using SQLite Database

Together, they provide a platform for **news data analysis, visualization, and management**.

---

## 🧩 1. News Management Dashboard (Shiny Application)

### 🔍 Overview

An interactive Shiny web app to:

* Fetch, analyze, visualize, and manage news articles
* Connect to a RESTful API backend (Plumber)
* Explore news trends, sentiment, and content

### ⚙️ Key Functionalities

#### 1. Data Fetching and Filtering

* **API Integration**: Connects to `http://localhost:8000`
* **Filtering Options**:

  * Date (dropdown)
  * Sentiment score range (-10 to 10)
  * Time of day (Morning, Afternoon, Evening)
  * Category (text input)
* **Fallback**: Mock data generation if API unavailable

#### 2. Data Visualization

Interactive charts and plots:

* 📊 **Sentiment Distribution**: Histogram
* 📚 **Category Distribution**: Bar chart
* 🧪 **Sentiment Density**: Density plot by category
* ✍️ **Top Authors**: Bar chart
* 📦 **Sentiment by Category**: Boxplots
* 📈 **Sentiment Over Time**: Line chart
* 📰 **Top Sources by Sentiment**: Bar chart
* ✨ **Word Count vs Sentiment**: Scatter plot
* 🔥 **Sentiment Heatmap**: Category × Source matrix

#### 3. Data Management

* ➕ Add News: Form with metadata
* ✏️ Update News: Edit headline/category
* ❌ Delete News: Confirmation dialog

#### 4. UI Features

* Collapsible Sidebar
* Section Toggles
* Responsive Layout
* Latest News Cards per Category

### 📊 Visualization Justification

* **Sentiment Analysis**: Track sentiment distributions & trends
* **Content Analysis**: Identify category emphasis and author/source bias
* **Relationships**: Correlate article length with sentiment
* **Interactive Exploration**: Filtered, real-time response

---

## 🔧 Technical Implementation (Frontend)

* Built with **R Shiny** & `shinythemes`
* Custom CSS for layout
* JavaScript for sidebar and toggle interactions
* `httr` for API interaction
* `dplyr`, `lubridate` for data manipulation
* Input validation for CRUD operations

---

## 🛠️ 2. News API Server with SQLite Database

### 🗃️ Overview

Backend REST API to:

* Store news in SQLite
* Support **CRUD operations**
* Provide data to frontend dashboard

### 🧱 Database Structure

* **DB**: `news_database.sqlite`
* **Table**: `news_data`
* **Fields**:

  * source, headline, category
  * link, text, domain
  * word count, sentiment score
  * keywords

### 🔌 API Endpoints

| Endpoint                    | Method | Description          | Parameters                       |
| --------------------------- | ------ | -------------------- | -------------------------------- |
| `/news`                     | GET    | Get all news         | -                                |
| `/news/category/<category>` | GET    | Get news by category | category                         |
| `/news`                     | POST   | Add new article      | source, headline, category, etc. |
| `/news/<id>`                | PUT    | Update article       | id, \[headline], \[category]     |
| `/news/<id>`                | DELETE | Delete article       | id                               |

### 🔐 Technical Features

* **Database**: RSQLite with connection handling
* **API**: Plumber + Swagger docs
* **Security**: SQL injection prevention

---

## 🔄 System Integration

### 🔁 Data Flow

1. CSV → SQLite Initialization
2. Dashboard (Shiny) → API Calls
3. API → Queries DB → Returns JSON

### 🔗 Combined Features

* API-based CRUD for Dashboard
* Same data model across system
* Unified management for articles

## ✅ Conclusion

This News Management System provides:

* For Analysts: Powerful visual insights
* For Editors: Intuitive content editing tools
* For Developers: Extensible REST API

Modular, maintainable, and scalable architecture makes this ideal for news data workflows.

---

## Descriptions

1. **Dashboard Overview** — UI with filters and visualizations
2. **Sentiment Histogram** — Frequency of sentiment scores
3. **Category Distribution** — Article count per category
4. **Sentiment Density** — Score distribution by category
5. **Top Authors** — Prolific writers bar chart
6. **Boxplots** — Sentiment by category
7. **Line Chart** — Daily sentiment trends
8. **Source Sentiment** — Best/worst sources
9. **Scatter Plot** — Sentiment vs. article length
10. **Heatmap** — Sentiment by category and source
11. **Add/Edit/Delete Interfaces** — CRUD forms

