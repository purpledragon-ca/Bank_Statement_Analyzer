# Bank Statement Analyzer - HTML Version

A browser-based application for analyzing PDF bank statements with AI-powered categorization and comprehensive visualizations.

## Features

### 📄 PDF Processing
- **Drag & Drop Upload**: Easily upload multiple PDF bank statements
- **Automatic Extraction**: Intelligently extracts transactions from PDFs
- **Pattern Detection**: Automatically detects transaction patterns in statements

### 📊 Visualizations
- **Summary Dashboard**: 
  - Total Refund, Total Outcome, Net Spend metrics
  - Interactive pie chart showing spending by category
- **Favorite Stores**: 
  - Bar chart of top merchants by spending
  - Detailed table with transaction counts
- **Trends Analysis**: 
  - Line chart showing spending over time
  - View by Year, Month, or Week
- **Net Spend Table**: 
  - Category breakdown by time period
  - Compare spending across different periods

### 🤖 AI Integration
- **DeepSeek Support**: Categorize merchants using DeepSeek API
- **OpenAI Support**: Alternative AI provider option
- **Toggle AI**: Enable/disable AI categorization
- **API Key Management**: Secure storage of API keys in browser

### 📁 Category Management
- **Add/Remove Categories**: Customize spending categories
- **Keyword Management**: Add keywords to match merchants
- **Uncategorized Merchants**: View and assign categories to uncategorized merchants
- **Pattern Matching**: Automatic categorization based on keywords

### 💾 Data Export
- **CSV Download**: Export filtered transactions as CSV
- **Date Range Filtering**: Filter transactions by custom date ranges

## Usage

### 1. Open the Application
Simply open `index.html` in a modern web browser (Chrome, Firefox, Edge, Safari).

### 2. Upload PDF Statements
- Drag and drop PDF files into the upload area, or
- Click to select files from your computer
- Multiple files can be uploaded at once

### 3. Configure AI (Optional)
1. Toggle "Enable AI" switch
2. Select AI provider (DeepSeek or OpenAI)
3. Enter your API key
4. Click "Save Settings"

**API Keys:**
- **DeepSeek**: Get your API key from [DeepSeek Platform](https://platform.deepseek.com)
- **OpenAI**: Get your API key from [OpenAI Platform](https://platform.openai.com)

### 4. Filter by Date Range
1. Select start and end dates
2. Click "Filter" to apply the date range

### 5. Explore Visualizations
Navigate through the tabs to view different analyses:
- **Summary**: Overview with metrics and pie chart
- **Favorite Stores**: Top merchants visualization
- **Trends**: Spending trends over time
- **Net Spend**: Category breakdown by period
- **Categories**: Manage categories and keywords

### 6. Manage Categories
- **Add Category**: Enter name and click "Add Category"
- **Add Keywords**: Enter keyword in category section and click "Add"
- **Assign Uncategorized**: Use dropdown to assign categories to merchants
- **Remove**: Click ✖ buttons to remove categories or keywords

### 7. Download Data
Click "📥 Download CSV" to export your filtered transactions.

## Technical Details

### Libraries Used
- **PDF.js**: PDF text extraction
- **Chart.js**: Data visualizations (pie, line, bar charts)
- **LocalStorage**: Store categories and AI settings locally

### Browser Compatibility
- Chrome/Edge (recommended)
- Firefox
- Safari
- Opera

### Data Storage
- All data is processed locally in your browser
- Categories and AI settings are stored in browser localStorage
- No data is sent to external servers (except AI API calls when enabled)

## Supported Bank Statements
The application works with bank statements that have:
- Date in format: "Mon DD" (e.g., "Jan 15")
- Amount in format: "$XXX.XX" or "XXX.XX"
- Merchant names as text

Tested with:
- RBC statements
- CIBC statements
- Rogers statements
- Other Canadian bank formats

## Customization

### Adding Default Categories
Edit the `categories` object in the JavaScript code:
```javascript
let categories = {
    "Supermarket": ["WAL-MART", "COSTCO", ...],
    "Dining": ["STARBUCKS", ...],
    // Add your categories
};
```

### Modifying Visualizations
All charts use Chart.js. Modify chart options in the respective update functions:
- `updatePieChart()`: Pie chart options
- `updateLineChart()`: Line chart options
- `updateFavoriteStores()`: Bar chart options

## Troubleshooting

### PDF Not Extracting Transactions
- Ensure PDF contains text (not just images)
- Check that date and amount formats match expected patterns
- Try a different PDF to verify extraction logic

### AI Categorization Not Working
- Verify API key is correct
- Check that AI is enabled
- Ensure you have API credits/quota
- Check browser console for errors

### Charts Not Displaying
- Ensure Chart.js library is loaded
- Check browser console for JavaScript errors
- Try refreshing the page

## Security Notes
- API keys are stored in browser localStorage (not encrypted)
- All processing happens client-side
- PDF files are never uploaded to any server
- AI API calls are made directly from your browser

## Future Enhancements
- [ ] Support for more bank statement formats
- [ ] Export to Excel format
- [ ] Advanced filtering options
- [ ] Multi-currency support
- [ ] Budget tracking and alerts
- [ ] Recurring transaction detection

## License
Free to use and modify.

