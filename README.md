# Fuel Station Management System

A web-based application for managing fuel station sales with Excel export capabilities.

## Features

- Track Petrol and Diesel sales
- Multiple nozzle support (2 nozzles each)
- Real-time calculations
- Interactive charts
- Automated Excel report generation
- Responsive design
- Local data persistence

## Excel Export Features

### Daily Sales Report Export
- Generates detailed Excel reports with:
  - Date and employee information
  - Petrol sales summary (per nozzle)
  - Diesel sales summary (per nozzle)
  - Volume calculations
  - Price calculations
  - Total summaries
  - Signature space

### Excel Report Format
```
FUEL STATION DAILY SALES REPORT
Date: [Current Date]                Employee: KTSWamy

PETROL SALES SUMMARY
Nozzle    Opening Reading    Closing Reading    Volume (L)    Amount (₹)
Nozzle 1  [Start Reading]    [End Reading]      [Volume]      [Amount]
Nozzle 2  [Start Reading]    [End Reading]      [Volume]      [Amount]
Total     -                  -                  [Total Vol]   [Total Amount]

DIESEL SALES SUMMARY
[Similar format as Petrol]

FINAL SUMMARY
Category       Volume (L)    Rate/L (₹)    Amount (₹)
Total Petrol   [Volume]     [Rate]        [Amount]
Total Diesel   [Volume]     [Rate]        [Amount]
Grand Total    [Volume]     -             [Total Amount]
```

## Usage Instructions

1. **Initial Setup**
   ```bash
   # Clone the repository
   git clone [repository-url]
   cd fuel-station-management
   ```

2. **Daily Operations**
   - Set fuel prices using "Set Price" buttons
   - Enter opening and closing readings
   - Click "Calculate Total Sales"
   - Generate Excel report when needed

3. **Generating Excel Reports**
   - Click "Generate Excel Report" button
   - Report is automatically downloaded
   - File name format: `FuelStation_Report_YYYYMMDD_KTSWamy.xlsx`

4. **Excel Report Features**
   - Formatted tables with borders
   - Colored headers
   - Automatic calculations
   - Printer-friendly layout

## Technical Details

### Dependencies
```html
<!-- Required for Excel Export -->
<script src="https://unpkg.com/xlsx/dist/xlsx.full.min.js"></script>
```

### Excel Export Function
```javascript
function generateReport() {
    // Get current date and data
    const date = document.getElementById('shiftDate').value;
    const petrolData = JSON.parse(localStorage.getItem('petrolData') || '{}');
    const dieselData = JSON.parse(localStorage.getItem('dieselData') || '{}');
    
    // Create and download Excel file
    // See source code for full implementation
}
```

### Data Structure
```javascript
{
    petrolData: {
        price: number,
        nozzle1: { start, end, sold, amount },
        nozzle2: { start, end, sold, amount },
        totalSold: number,
        totalAmount: number
    },
    dieselData: {
        // Similar structure as petrolData
    }
}
```

## Installation

1. Download or clone the repository
2. Open index.html in a modern web browser
3. No server required - runs locally

## Browser Support

- Chrome (recommended)
- Firefox
- Edge
- Safari

## License

MIT License

## Notes

- Excel reports are generated client-side
- Data is stored in browser's localStorage
- No server or database required
- Reports are downloaded automatically
- Backup data regularly

## Contributing

1. Fork the repository
2. Create feature branch
3. Commit changes
4. Push to branch
5. Create Pull Request
