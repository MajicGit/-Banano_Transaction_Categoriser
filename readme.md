This script fetches all your banano transactions for a given year, gets the value of the transaction at the time using coingecko, and then tries to auto-categorise them into mining - airdrops - exchange and other transactions.

To run: You just need Python (has only been tested with 3.9) and the pycoingecko library. 

Note that running the script can take **very long**, as the average receive transaction will take around ~ 13 seconds, and the average send transaction around 1 second.

The script generates the following files:
account_export.csv: CSV with all your transactions, as provided by YellowSpyGlass
account_export_adjusted_dates.csv: The above CSV file, with another row where the transaction timestamp for receive transactions is (optionally) updated to the timestamp of the corresponding send transaction.
account_export_withprice.csv: The above, with the ban price at the timestamp of each transaction in your desired currency, and the ban price of the transaction as a whole added.
account_export_filtered.csv: The above, filtering out all transactions that did not take place in 2021.

Then the 4 final files, containing all transactions auto-categorised in these categories. (Others includes all unknown addresses)

mining_output.csv, faucet_output.csv, exchange_output.csv, other_output.csv



Potential future plans:
- Change from coingecko api/only use coinex price data. (Apparently this has inflated prices at times)
- Categorise outgoing transactions better. E.g. get a list of all JungleTv fund wallets so you can have a good overview of that as well
- Tidying up the files it creates (it currently creates around 8 different CSV files -- this is kinda needed in case it crashes so that you don't loose all your progress) but hopefully I'll be able to find a better solution 
- Do further testing to actually verify the results, with more currencies
- Build out the list of known addresses -- any report on ones the script is missing are very welcome.
