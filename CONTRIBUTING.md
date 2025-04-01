# Contributing to Tax Rates Data

Welcome to the Tax Calculator’s data repository! Help us make this tool truly global by adding or updating tax data for your country. Whether you’re fixing a typo or adding a new nation, every contribution counts.

## How to Contribute
1. **Fork this Repository**: Click "Fork" at the top-right of this page.
2. **Clone Your Fork**: `git clone https://github.com/yourusername/tax-rates-data.git`
3. **Edit `tax-rates.json`**:
   - Add a new country or update an existing one using the format below.
   - Use reliable sources (e.g., PwC Worldwide Tax Summaries, OECD Tax Database, government websites).
4. **Commit Changes**: `git add tax-rates.json` then `git commit -m "Add [Country Name] tax data"`
5. **Push to Your Fork**: `git push origin main`
6. **Submit a Pull Request**: Go to your fork on GitHub and click "New Pull Request". Describe your changes clearly (e.g., "Added tax brackets for Iceland based on Skatturinn.is").

## Data Format
Each country entry should follow this structure:
```json
"countryCode": {
  "currency": "symbol",
  "single": [
    { "min": incomeFloor, "max": incomeCeiling, "rate": taxRate, "base": cumulativeTaxFromLowerBrackets }
  ],
  "married": [
    // Optional: same format as "single"
  ],
  "standardDeduction": amount,
  "childCredit": amountPerChild,
  "maxChildren": maxEligibleChildren,
  "selfEmploymentTax": rate,
  "capitalGains": [
    // Optional: same format as "single" or {"rate": flatRate}
  ],
  "stateTaxes": {
    "regionCode": { "rate": regionalRate, "maxIncome": incomeCap }
  }
}
