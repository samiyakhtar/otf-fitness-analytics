# OTF Fitness Analytics
A comprehensive fitness tracking system that processes Orange Theory Fitness workout data using Python and SQLite, featuring automated data collection, SQL analytics, and performance visualization.

## Project Overview
Built a complete end-to-end analytics platform that demonstrates data engineering and analytics capabilities through fitness performance tracking. The system processes 100+ workout records with automated data validation and quality checks to support performance optimization insights.

## Features

### Data Processing & Storage
- **Fitness tracking system** that generates and processes workout data using Python
- **SQLite database** with automated data validation and quality checks
- **100+ workout records** processing with comprehensive data cleaning
- **Automated data collection** strategy for daily performance tracking

### SQL Analytics & Views
- **4 automated SQL views** tracking trends, coach effectiveness, and goal achievement
- **Advanced SQL analytics** using window functions and aggregations
- **Personal bests tracking** with statistical analysis for consistency scores
- **Performance optimization insights** through data-driven analytics

### Visualizations & Reporting
- **6 comprehensive charts** including trend analysis and performance metrics
- **Coach effectiveness analysis** with rating and performance comparisons
- **Workout distribution analysis** across different training types
- **Automated daily reports** with key performance indicators

## Technical Implementation
### Database Schema
```sql
-- Main workouts table
CREATE TABLE workouts (
    workout_id TEXT PRIMARY KEY,
    date TEXT NOT NULL,
    workout_type TEXT,
    coach TEXT,
    duration_minutes INTEGER,
    calories_burned INTEGER,
    avg_heart_rate INTEGER,
    max_heart_rate INTEGER,
    splat_points INTEGER,
    orange_zone_minutes INTEGER,
    red_zone_minutes INTEGER,
    workout_rating INTEGER,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### SQL Views Created
1. **workout_trends_view** - Tracks performance trends over time with rolling averages
2. **coach_performance_view** - Analyzes coach effectiveness and class statistics
3. **personal_bests_view** - Shows personal records and achievement dates
4. **goal_progress_view** - Tracks progress toward fitness goals with trend analysis

### Key Metrics Tracked
- Calories burned per workout
- Heart rate zones and averages
- Splat points (Orange Theory specific metric)
- Workout ratings and consistency scores
- Coach performance and effectiveness
- Training type distribution and preferences

### Analytics & SQL
- **Python ETL pipeline** development with automated data processing
- **Advanced SQL queries** using window functions and CTEs
- **Database view creation** for automated performance tracking
- **Statistical analysis** for personal bests and consistency scoring
- **Trend analysis** with rolling averages and time-series data

### Data Visualization
- **matplotlib/seaborn** for comprehensive dashboard creation
- **Multi-chart dashboards** with 6 different visualization types
- **Performance metrics** visualization and reporting
- **Interactive data exploration** and analysis

## Installation & Usage
### Prerequisites
```bash
pip install pandas matplotlib seaborn sqlite3
```

### Running the Analysis
1. **Data Generation**: Creates 100+ realistic workout records
2. **Database Setup**: Initializes SQLite database with proper schema
3. **SQL Views Creation**: Builds 4 automated performance views
4. **Visualization**: Generates comprehensive fitness dashboard
5. **Export**: Saves analysis results and database for further use

### Sample Queries
```sql
-- Coach effectiveness analysis
SELECT * FROM coach_performance_view ORDER BY avg_rating DESC;

-- Personal records tracking
SELECT * FROM personal_bests_view;

-- Workout trends with rolling averages
SELECT date, calories_burned, calories_trend 
FROM goal_progress_view 
ORDER BY date DESC LIMIT 30;
```

## Project Structure
```
otf-fitness-analytics/
├── main_notebook.ipynb          # Complete analytics pipeline
├── otf_fitness.db              # SQLite database with workout data
├── sample_workouts.csv         # Sample data export
├── calories_trend.png          # Generated visualization
├── heart_rate_analysis.png     # Performance analysis chart
└── README.md                   # Project documentation
```

## Analytics Capabilities

### Performance Tracking
- **Daily workout metrics** with automated data collection
- **Personal best identification** and achievement tracking
- **Consistency scoring** based on workout ratings and frequency
- **Goal progress monitoring** with trend analysis

### Coach Analysis
- **Effectiveness ratings** based on student performance and satisfaction
- **Class performance metrics** including average calories and heart rate
- **Comparative analysis** across different coaches and training styles

### Trend Analysis
- **Time-series analysis** of fitness performance over time
- **Seasonal patterns** in workout frequency and performance
- **Performance correlation** between different workout types
- **Predictive insights** for future performance optimization

## Data Pipeline Architecture
1. **Data Simulation** → Generates realistic workout data
2. **Data Validation** → Ensures data quality and completeness  
3. **Database Storage** → Stores validated data in SQLite
4. **View Creation** → Builds automated analytics views
5. **Analysis Engine** → Processes data for insights
6. **Visualization** → Creates comprehensive dashboards
7. **Export** → Saves results for external use

## Future Enhancements
- Integration with real fitness APIs (Strava, Fitbit)
- Machine learning models for performance prediction
- Advanced statistical analysis and correlation studies
- Real-time data streaming and live dashboards
- Mobile app integration for data collection
