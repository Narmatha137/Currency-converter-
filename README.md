Currency Converter – 

This is a simple Currency Converter written in Python. It uses real-time exchange rates from the ExchangeRate.host API to convert an amount from one currency to another.


---

🚀 Features

✅ Converts any amount between two currencies

✅ Uses real-time exchange rates from a public API

✅ Simple and clean command-line interface

✅ No API key required



---

📦 Requirements

Python 3.6 or higher

requests library (Install via pip)


pip install requests


---

🛠️ How to Use

1. Clone or download the repository.


2. Install the required packages (if not already installed).


3. Run the script.



python currency_converter.py

4. Enter the amount, source currency, and target currency when prompted.




---

📋 Example

Enter amount: 100
From currency (e.g., USD): USD
To currency (e.g., EUR): EUR
100.00 USD = 92.75 EUR


---

🔧 Code Overview

import requests

def convert_currency(amount, from_currency, to_currency):
    # API endpoint
    url = "https://api.exchangerate.host/convert"
    
    # Request parameters
    params = {
        "from": from_currency.upper(),
        "to": to_currency.upper(),
        "amount": amount
    }

    response = requests.get(url, params=params)
    data = response.json()

    if data.get("success", False):
        result = data["result"]
        print(f"{amount:.2f} {from_currency.upper()} = {result:.2f} {to_currency.upper()}")
        return result
    else:
        print("Error: Could not retrieve exchange rate.")
        return None


---
