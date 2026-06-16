# Business Performance Dashboard

A modern, responsive, and enterprise-grade Business Analytics Dashboard built with React.js. This application provides hierarchical business insights through summary KPIs, location-based filtering, interactive data grids, and account-level drill-down views.

Overview

The Business Performance Dashboard is designed for organizations such as banks, financial institutions, telecom companies, and large enterprises that need to monitor business performance across multiple geographical levels.

Users can analyze data at Province, Region, Area, and City levels and drill down into detailed account-level information through an interactive side panel.

Features
Executive Summary Dashboard
KPI Cards
Business Performance Metrics
Revenue Analysis
Customer Statistics
Transaction Insights
Growth Monitoring
Location-Based Filtering

Hierarchical filters:

Province
Region
Area
City

Dynamic cascading dropdown functionality ensures that each selection updates the available options in the next filter.

Interactive Data Grid

The dashboard includes a powerful data table with:

Sorting
Filtering
Searching
Pagination
Sticky Headers
Responsive Layout
Row Selection
Export Functionality

Displayed information includes:

Province	Region	Area	City	Customers	Accounts	Revenue	Transactions
Account-Level Drill Down

Clicking a grid row opens a sliding drawer displaying:

Account Number
Customer Name
CNIC (Masked)
Branch Information
City
Account Type
Current Balance
Monthly Transactions
Account Status
Last Activity Date
Export Options

Users can export dashboard data into:

Excel (.xlsx)
CSV (.csv)
Responsive Design

Optimized for:

Desktop
Laptop
Tablet
Mobile Devices
Technology Stack
Frontend
React.js
JavaScript (ES6+)
React Hooks
Context API / Redux Toolkit
UI Framework
Material UI (MUI)
Data Grid
AG Grid Community
OR
MUI Data Grid
State Management
React Context API
Redux Toolkit (Optional)
Styling
Material UI Components
CSS Modules / Styled Components
Project Structure
src/
│
├── components/
│   ├── SummaryCards/
│   ├── FilterPanel/
│   ├── BusinessGrid/
│   ├── AccountDrawer/
│
├── pages/
│   └── BusinessDashboard/
│
├── services/
│   └── api.js
│
├── hooks/
│   └── useBusinessData.js
│
├── context/
│   └── DashboardContext.js
│
├── mock-data/
│   ├── businessSummary.json
│   ├── accountData.json
│
├── utils/
│   ├── exportExcel.js
│   ├── exportCSV.js
│
└── App.js
Dashboard Workflow
Step 1

Select geographical filters:

Province
   ↓
Region
   ↓
Area
   ↓
City
Step 2

Summary cards update automatically.

Step 3

Grid data refreshes based on selected filters.

Step 4

Select any row.

Step 5

Account-level details open in a side drawer.

Sample KPIs
Total Customers
Active Customers
Total Accounts
New Accounts
Monthly Revenue
Total Transactions
Growth Percentage
Risk Accounts
Mock Data

The application contains realistic business data representing:

Provinces
Sindh
Punjab
Khyber Pakhtunkhwa
Balochistan
Gilgit Baltistan
Azad Jammu & Kashmir
Sample Cities
Karachi
Hyderabad
Lahore
Faisalabad
Islamabad
Rawalpindi
Peshawar
Quetta
