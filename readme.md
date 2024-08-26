Spend-Sentinel-App
Spend-Sentinel-App is an open-source application designed to help users track and manage their credit card payments. This monorepo contains the various submodules that work together to provide a seamless experience for users.

Submodules Overview
1. bank-scraper
Description:
This submodule uses the third-party library israeli-bank-scrapers to scrape data from relevant banks and credit card companies according to the user's preferences.
2. transaction-api
Description:
The transaction-api submodule serves as the backend of the application, facilitating communication between the frontend (telegram bot and web-app) and the MongoDB database. It stores all scraped transaction data securely.
3. telebot
Description:
This submodule is responsible for sending notifications via Telegram whenever new transactions are detected. The user must start the bot on Telegram to receive these alerts.
4. web-app
Description:
The web-app submodule provides a local website where users can view their current transactions and their statuses:
Approved: Green
Declined: Red
Needs to be Checked: Yellow
Users can also change the status of transactions and view the status of an entire month's transactions.
Data Storage
All data is stored locally in a MongoDB database for security purposes.

Dependencies
Docker
How to Use
1. Generate a Telegram Bot
Use BotFather in Telegram to create a new bot.
2. Configure Secrets
Fill in the necessary information in the following secret files:
secrets/botSecrets.env (Telegram bot token and Telegram ID)
secrets/loginInformation.env (Username and password for credit companies)
3. Run the Application
Use the following command to build and start the application:
bash
Copy code
docker compose up --build
