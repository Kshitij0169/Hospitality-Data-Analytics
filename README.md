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

### Step 2: Data Cleaning

# Identify and handle errors

df_bookings[df_bookings.no_guests <= 0]
df_bookings = df_bookings[df_bookings.no_guests >= 0]

min_rev, max_rev = df_bookings.revenue_generated.min(), df_bookings.revenue_generated.max()

### Step 3: Data Transformation

# Explore room categories

df.groupby("room_class")["occ_pct"].mean().round(2)

# Analyze occupancy rates per city

df = pd.merge(df, df_hotel, on="property_id")
df.groupby("city")["occ_pct"].mean().plot(kind="pie")

# Compare weekday vs. weekend occupancy

df = pd.merge(df, df_date, left_on="check_in_date", right_on="date")
df.groupby("day_type")["occ_pct"].mean().round(2)

# Explore June occupancy by city

df_june_22 = df[df["mmm yy"] == "Jun 22"]
df_june_22.groupby("city")["occ_pct"].mean().round(2).sort_values()

# Append new data for August

df_august = pd.read_csv("E:/Automation_Course/Python/3_project_hospitality_analysis/datasets/new_data_august.csv")
latest_df = pd.concat([df, df_august], ignore_index=True, axis=0)

# Print revenue realized per city

df_bookings_all.groupby("city")["revenue_realized"].sum()
