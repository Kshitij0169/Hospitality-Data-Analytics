# Hospitality Data Analysis Project

Welcome to the Hospitality Data Analysis project! In this project, we explore and analyze hospitality data to derive meaningful insights using Python and Pandas. Below are instructions on how to navigate and contribute to this project.

## Getting Started

### Step 1: Data Exploration

```python
import pandas as pd
df_bookings = pd.read_csv("E:/Automation_Course/Python/3_project_hospitality_analysis/datasets/fact_bookings.csv")

# Display the first few rows
df_bookings.head(4)

# Get the shape of the dataset
df_bookings.shape

# Explore unique room categories and booking platforms
df_bookings.room_category.unique()
df_bookings.booking_platform.unique()
df_bookings.booking_platform.value_counts()

# Visualize data
df_bookings.booking_platform.value_counts().plot(kind="barh")
df_bookings.booking_status.value_counts().plot(kind="pie")

# Quick statistics
df_bookings.describe()

```
