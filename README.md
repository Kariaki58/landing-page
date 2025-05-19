# Global Pricing Page

A responsive pricing page that displays localized prices based on the user's country and currency, with automatic country detection and manual selection options.

## Features

- **Automatic Country Detection**: Uses IP geolocation to detect the user's country on page load
- **Manual Country Selection**: Dropdown with 18 supported countries
- **Currency Conversion**: Converts USD-based prices to local currencies using exchange rates
- **Responsive Design**: Works on mobile, tablet, and desktop devices
- **Visual Pricing Cards**: Three-tier pricing with highlighted "Most Popular" option
- **Loading States**: Shows loading spinners during API calls

## Technologies Used

- HTML5
- CSS3 (with CSS variables for theming)
- JavaScript (ES6)
- Fetch API for external requests
- ipapi.co for geolocation
- exchangerate-api.com for currency conversion

## How It Works

1. On page load:
   - Populates the country dropdown
   - Attempts to detect the user's country via IP address
   - Shows detected country and currency

2. When a country is selected (or detected):
   - Fetches current exchange rates from USD to the local currency
   - Converts all prices to the local currency
   - Formats prices according to currency conventions (decimal places, symbols)
   - Displays three pricing cards with converted amounts

3. Special handling:
   - Currencies without decimals (JPY, KRW, etc.) are rounded to whole numbers
   - Fallback to USD if currency conversion fails
   - Loading states during API calls

## Setup

1. Clone the repository
2. Open `index.html` in a web browser
3. No server or additional dependencies required

## Customization

You can easily customize:

- Colors by modifying the CSS variables in the `:root` selector
- Pricing tiers by editing the `usdPricing` object in JavaScript
- Features lists by modifying the `createPricingCard` function calls
- Supported countries by editing the `countries` array

## Limitations

- Uses free APIs that may have rate limits
- Exchange rates are not cached (would refresh on each page load)
- No persistent storage of user's country preference

## Future Improvements

- Add more countries and currencies
- Implement local storage to remember user's country selection
- Add more pricing tiers or customization options
- Improve currency formatting with Intl.NumberFormat
- Add annual pricing options

## Screenshot

![Image](https://github.com/user-attachments/assets/12f94a7c-71ad-4c3a-a4ae-c251cbd45715)

## License

MIT License - free to use and modify
