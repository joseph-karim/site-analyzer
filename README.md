# site-analyzer

Enhanced Site Selection Tool - Implementation Guide
This document provides implementation guidance for the enhanced Site Selection Tool that includes data explanation, chat functionality, and zoning variance options.
Overview
The enhanced tool builds on the original concept with these additional features:

Detailed Property Data Analysis with interactive chat functionality
Zoning Variance Options to show designs that require regulatory approvals
Tabbed Interface to toggle between standard and variance-based designs

Architecture
The application consists of these key components:
Frontend Components

Main Application (SiteSelectionTool.jsx)

Manages overall state and layout
Handles API calls and data processing
Coordinates between sub-components


PropertyDataChat Component

Provides scrollable chat interface
Handles questions about property data
Offers contextual explanations of zoning, topography, etc.


ZoningVariances Component

Displays potential variance options
Shows impact of each variance
Links to variance-based floor plans


Floor Plan Components

Standard designs (compliant with current zoning)
Variance-based designs (requiring regulatory approval)



Backend API
The backend API (FastAPI) includes the following endpoints:

/api/analyze-site - Primary endpoint that:

Processes address input
Returns comprehensive site data
Includes standard floor plan recommendations


/api/variance-options - Returns:

Available zoning variance options
Impact analysis for each option
Approval likelihood estimates


/api/analyze-variance - Generates:

Floor plans based on selected variances
Compares standard vs. variance-based options
Provides regulatory context



Data Flow

User enters an address
Frontend queries the backend API
API retrieves/calculates:

Property boundaries
Zoning regulations
Topographical data
Solar orientation
Available variance options


Frontend displays:

Site analysis visualization
Standard floor plan options
Chat interface for data explanation
Variance options (in variance tab)



