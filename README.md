# Clickhouse-Zeotap
Zeotap Software Engineering Intern Assignment
# ClickHouse-Flat File Data Ingestion Tool

This web application facilitates bidirectional data transfer between ClickHouse databases and flat files. It supports JWT token authentication for ClickHouse, column selection, and provides progress tracking and reporting.

## Features

- **Bidirectional Data Flow**: Transfer data from ClickHouse to Flat File and vice versa
- **Source Selection**: Choose data source via user interface
- **ClickHouse Authentication**: JWT token-based authentication
- **Schema Discovery**: Automatically discover and display available tables and columns
- **Column Selection**: Select specific columns for data transfer
- **Progress Tracking**: Monitor ingestion progress
- **Data Preview**: Preview data before ingestion
- **Error Handling**: User-friendly error messages
- **Completion Reporting**: Display total records processed

### Bonus Features
- **Multi-Table Join**: Join multiple ClickHouse tables during ingestion
- **Progress Bar**: Visual indicator of ingestion progress
- **Data Preview**: Display first 100 records before ingestion

## Requirements

- Python 3.6+
- ClickHouse database (local or remote)
- Web browser

## Dependencies

- Flask
- Flask-CORS
- clickhouse-driver
- pandas
- PyJWT
- pyngrok (for Google Colab)

## Google Colab Setup

1. Upload the Python script to Google Colab
2. Run the script
3. Click on the generated URL to access the web application

## Local Setup

1. Clone the repository:
```
git clone <repository-url>
```

2. Install dependencies:
```
pip install -r requirements.txt
```

3. Run the application:
```
python app.py
```

4. Access the application at: http://localhost:5000

## Usage Instructions

### ClickHouse to Flat File

1. Select "ClickHouse to Flat File" direction
2. Enter ClickHouse connection details and JWT token
3. Click "Connect" to establish connection
4. Click "Load Tables" to retrieve available tables
5. Select a table from the dropdown
6. (Optional) Enable Multi-Table Join if needed
7. Select columns for transfer
8. Configure output file settings
9. Click "Preview Data" to view sample data
10. Click "Start Ingestion" to begin transfer
11. Monitor progress in the status area
12. Download the output file when complete

### Flat File to ClickHouse

1. Select "Flat File to ClickHouse" direction
2. Upload a flat file (CSV, TSV, etc.)
3. Select delimiter type
4. Click "Load File" to parse the file
5. Enter ClickHouse target connection details and JWT token
6. Enter target table name
7. Click "Connect" to establish connection
8. Select columns for transfer
9. Click "Preview Data" to view sample data
10. Click "Start Ingestion" to begin transfer
11. Monitor progress in the status area

## Testing

The application can be tested with ClickHouse example datasets:
- uk_price_paid
- ontime

Test cases:
1. Single ClickHouse table to Flat File (selected columns)
2. Flat File (CSV upload) to new ClickHouse table (selected columns)
3. Joined ClickHouse tables to Flat File (bonus feature)
4. Connection/authentication failures
5. Data preview functionality

## Troubleshooting

- Ensure ClickHouse server is running and accessible
- Verify JWT token is valid and properly formatted
- Check network connectivity between the application and ClickHouse
- For file upload issues, ensure the file is in a supported format (CSV, TSV)
- If encountering memory issues with large files, increase batch size in the code
