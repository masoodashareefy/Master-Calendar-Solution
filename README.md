# Master-Calendar-Solution

1. **Data Collection:**
   - Utilized Python and PySpark to pull data from multiple APIs, including NBA, NHL, MLS, and Ticketmaster.
   - Implemented secure API integrations by storing sensitive keys in Azure Key Vault and ensuring all API calls were handled with robust error handling.

2. **Data Transformation:**
   - Enhanced raw datasets by applying schema definitions using PySpark’s `StructType`.
   - Transformed data to standardize columns like EventDate, EventTime (converted to MST), Title, Home, Away, and Venue.
   - Applied mappings for consistent team names and venue standardization across datasets.

3. **Data Integration:**
   - Combined data from all sources into a unified Spark DataFrame using `unionByName` while also handling schema mismatches.
   - Removed duplicate events by implementing a deduplication process based on key attributes like EventDate, EventTime, Title, and Venue.

4. **Data Enrichment and Structuring:**
   - Ranked events with multiple times on the same day using PySpark’s `Window` functions, creating separate columns (EventTime1, EventTime2, EventTime3).
   - Generated unique `HashKey` values for each event to ensure data integrity and added metadata columns like InsertDate.

5. **Database Integration:**
   - Stored the final dataset in Delta Lake for efficient querying and real-time analytics.
   - Created a staging table for initial validation and processing of data.
   - Archived data into a separate table and prepared a DataVerse-compatible format for BI tools and reporting.

6. **Technologies Used:**
   - **PySpark**: For distributed data processing, transformations, and schema enforcement.
   - **Delta Lake**: For efficient storage, versioning, and querying of master calendar data.
   - **Azure Key Vault**: For secure storage and retrieval of API keys and sensitive credentials.
   - **Ticketmaster, NBA, NHL, MLS APIs**: For retrieving real-time event schedules.

7. **Problem Solved:**
   - This project consolidates multiple event schedules into a centralized Master Calendar.
   - It ensures accurate, deduplicated, and enhanced data ready for BI tools, reducing manual intervention and enhancing event planning workflows.
