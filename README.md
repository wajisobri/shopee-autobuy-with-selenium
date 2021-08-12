# Shopee Auto Buy/Checkout Product

## Goals
This program was created to make it easier for users to make product transactions on the Shopee e-commerce website

## Description
This program is a **BOT** that will automatically purchase a product based on the information entered by the user. The information required is as follows:

 1. Login information (such as email, password, phone number, or cookies);
 2. Product information (containing product links)
 3. Purchase time information (containing hours and minutes when the product will be purchase)

This program is made using the **Python** and uses the **Selenium** library.

## Flowchart

```mermaid
graph LR
A((Start)) --> B[Login with Email]
A --> C[Login with Phone]
A -- login with --> D[Login with Cookies]
B --> |Get Purchase Time| E[Run Bot]
C --> |Get Purchase Time| E[Run Bot]
D --> |Get Purchase Time| E[Run Bot]
E -- loop until the specified time --> E
E --> F[Add Product to Cart]
F --> G[Checkout Cart]
G --> H[Create Order]
H --> I((End))
```
## Requirement

 - [ ] Python 3.8.x
 - [ ] Google Chrome
 - [ ] PIP

## How To Use

Install **Selenium** and **Undetected Chromedriver** library

    pip install selenium undetected-chromedriver
or

    pip install -r requirements.txt

Setup Login Configuration in file *login.py*. Fill in the variables according to their needs

    // Login with Email
    email="YOUR_EMAIL_HERE"
    password="YOUR_PASSWORD_HERE"
    
    // Login with Phone
    phone="YOUR_PHONE_NUMBER_HERE"
    
    // Login with Cookies
    cookie='YOUR_COOKIES_HERE' // cookies value from SPC_EC
![Example of SPC_EC Cookie](https://raw.githubusercontent.com/wajisobri/shopee-autobuy-with-selenium/main/Cookies-SPC_EC-Value-Example.png)

Run Program

    python bot.py

## How to Get Cookies Value

 1. **Open** Google Chrome and go to Shopee (make sure you have **logged in**)
 2. **Open** Product Link and **Press** `Ctrl+Shift+I`
 3. **Click** on tab `Network` and **Refresh** Browser
 4. **Find** and **Click** `https://shopee.co.id/api/v2/item/get itemid=xxx&shopid=xxx`
 5. **Click** on tab `Cookies` and **Find** `SPC_EC`
 6. **Copy** value and **Place** on `login.py`
![enter image description here](https://raw.githubusercontent.com/wajisobri/shopee-autobuy-with-selenium/main/How-To-Get-Cookie-Value.png)
