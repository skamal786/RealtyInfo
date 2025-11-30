# RealtyInfo - Project Scope Document

## Project Overview
RealtyInfo is a web application that provides Canadian real estate price information based on user-provided location data (city name or postal code). The app displays current price ranges and averages for three property types: Detached homes, Townhouses, and Condominiums, along with predicted average prices for 2-year and 5-year timeframes.

## Core Objectives
- Provide quick, accessible real estate price information for Canadian locations
- Support both city name and postal code as search inputs
- Display clear, organized pricing data for multiple property types
- Offer price predictions for 2-year and 5-year timeframes
- Deliver a simple, user-friendly interface requiring minimal user effort

## Functional Requirements

### 1. User Input
- **Location Search Field**
  - Single input field accepting either:
    - Canadian city names (e.g., "Toronto", "Vancouver", "Calgary")
    - Canadian postal codes (e.g., "M5V 3A8", "V6B 1A1")
  - Input validation to ensure proper format
  - Auto-formatting for postal codes (uppercase, proper spacing)
  - Clear placeholder text indicating accepted formats

### 2. Data Display
The app should display the following information for each property type:

**Property Types:**
- Detached Homes
- Townhouses
- Condominiums

**Price Metrics (for each type):**
- Price Range (minimum to maximum)
- Average Price (current)
- Predicted Average Price in 2 Years
- Predicted Average Price in 5 Years
- Currency displayed in Canadian dollars (CAD)

### 3. Price Prediction Feature
The app should provide future price estimates to help users understand potential market trends.

**Prediction Timeframes:**
- 2-year prediction
- 5-year prediction

**Prediction Display Requirements:**
- Clearly labeled as "Predicted" or "Estimated"
- Show predicted average price for each property type
- Display percentage change from current price (e.g., "+15% over 2 years")
- Include prominent disclaimer about prediction limitations
- Visual distinction between current and predicted prices

**Prediction Calculation Methods:**
- **MVP Approach:** Simple compound annual growth rate (CAGR) applied to current prices
  - Example: 4% annual growth rate = current price × 1.04^n (where n is years)
- **Enhanced Approach:** City-specific historical growth rates
- **Future Enhancement:** Machine learning models with multiple economic factors

**Disclaimer Requirements:**
- Predictions are estimates only, not financial advice
- Actual prices may vary significantly from predictions
- Based on historical trends which may not continue
- Does not account for unforeseen market changes
- Users should consult real estate professionals for investment decisions

### 4. User Interface Components

**Search Section:**
- Location input field
- Search/Submit button
- Clear/Reset button (optional)
- Error messaging for invalid inputs

**Results Section:**
- Location identifier (displaying searched city/postal code)
- Organized display of property type data (cards, table, or grid layout)
- Current price information formatted with proper currency notation
- Future price predictions clearly labeled with timeframe
- Visual indicators showing predicted growth percentage
- Optional: Simple chart/graph showing price trajectory
- Disclaimer about prediction accuracy and limitations
- Visual distinction between property types
- Responsive design for mobile and desktop viewing

### 5. Data Source Strategy
The scope assumes one of the following approaches:

**Option A: Static/Sample Data**
- Hardcoded data for demonstration purposes
- Pre-populated data for major Canadian cities
- Price predictions based on estimated growth rates (e.g., 3-5% annually)
- Clearly labeled as sample/estimated data

**Option B: Real Estate API Integration**
- Integration with Canadian real estate data provider (e.g., CREA, Zoocasa API, Realtor.ca data sources)
- API key management
- Rate limiting considerations
- Caching strategy to minimize API calls
- Historical data access for trend analysis

**Option C: Web Scraping (if legally permissible)**
- Scraping public real estate listings
- Compliance with terms of service and robots.txt
- Regular data updates
- Historical data collection for prediction modeling

**Price Prediction Methodology:**
- **Simple Model (for MVP):** Apply historical average growth rate to current prices
- **Moderate Model:** Use city-specific historical trends and compound growth
- **Advanced Model (future enhancement):** Machine learning models considering:
  - Historical price trends (5-10 years)
  - Population growth
  - Employment rates
  - Interest rate trends
  - Housing supply and demand
  - Economic indicators

### 6. Input Validation & Error Handling

**Input Validation:**
- Verify postal code format (A1A 1A1 pattern)
- Check for valid city names
- Trim whitespace and handle case-insensitivity

**Error States:**
- Invalid format entered
- Location not found in database/API
- No data available for requested location
- API connection failure (if applicable)
- Rate limit exceeded (if applicable)

**Error Messages:**
- User-friendly error messages
- Suggestions for correction
- Example formats shown

### 7. Technical Considerations

**Performance:**
- Fast response time (<2 seconds for data retrieval)
- Loading indicators during data fetch
- Caching of recently searched locations

**Accessibility:**
- Keyboard navigation support
- Screen reader compatibility
- Proper ARIA labels
- Sufficient color contrast

**Browser Compatibility:**
- Modern browsers (Chrome, Firefox, Safari, Edge)
- Mobile responsive design

## User Experience Flow

1. User lands on RealtyInfo homepage
2. User sees search field with clear instructions
3. User enters city name or postal code
4. User clicks search button or presses Enter
5. App validates input
6. App retrieves price data (shows loading indicator)
7. App displays results for all three property types
8. User can perform new search or refine current search

## Success Metrics
- Successful data retrieval and display for valid inputs
- Clear, readable presentation of price information
- Intuitive interface requiring no instructions
- Fast load times and responsive interactions
- Accurate error handling and user guidance

## Future Enhancements (Out of Current Scope)
- Interactive charts showing historical trends alongside predictions
- Confidence intervals or ranges for predictions (e.g., "likely between $X and $Y")
- Customizable prediction timeframes (1, 3, 10 years)
- Comparison between multiple locations
- Neighborhood information and amenities
- Map integration showing property locations
- Market trend indicators (hot/cold market)
- User accounts and saved searches
- Additional property types (Semi-detached, Land, etc.)
- Rental price information and predictions
- Email alerts for price changes
- Economic indicators affecting predictions (interest rates, GDP, employment)

## Constraints & Assumptions
- App focuses on Canadian real estate market only
- Data accuracy depends on source reliability
- Real-time data may not be feasible depending on data source
- Some locations may have limited or no data available
- Pricing data represents market estimates/averages, not specific listings
- Price predictions are estimates based on historical trends and should not be considered financial advice
- Prediction accuracy decreases with longer timeframes (5-year predictions less reliable than 2-year)
- External factors (economic changes, policy shifts, unforeseen events) may significantly impact actual future prices

## Deliverables
1. Functional web application (HTML/CSS/JavaScript or React)
2. Clean, modern user interface
3. Input validation and error handling
4. Data display for three property types
5. Responsive design for multiple devices
6. Documentation for setup and usage

## Technical Stack Recommendations
- **Frontend:** React (for interactive UI) or vanilla HTML/CSS/JavaScript
- **Styling:** Tailwind CSS or custom CSS
- **Data Handling:** Fetch API or Axios for API calls (if applicable)
- **Deployment:** Static hosting (Netlify, Vercel, GitHub Pages)

## Project Phases

**Phase 1: MVP (Minimum Viable Product)**
- Basic search functionality with city name input
- Static/sample data for 10-15 major Canadian cities
- Simple, clean UI displaying the three property types
- Basic price predictions using fixed growth rate calculation
- Clear disclaimer about prediction limitations
- Basic error handling

**Phase 2: Enhanced Features**
- Postal code support
- Expanded city coverage
- Improved UI/UX with loading states
- Better error messaging

**Phase 3: Data Integration & Advanced Predictions** (if applicable)
- API integration for real-time data
- City-specific historical trend analysis
- More sophisticated prediction algorithms
- Confidence intervals for predictions
- Caching implementation
- Performance optimization

## Notes
- The app should clearly indicate the source and freshness of data
- Disclaimer about data being estimates/averages should be visible
- Price predictions must include prominent disclaimers and should not be presented as financial advice
- Prediction methodology should be transparent and explained to users
- Consider showing prediction confidence levels or ranges in future versions
- Contact or feedback mechanism for users to report issues (optional)
