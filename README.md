# EtherscanAPI

This is a very simple web application that retrieves and displays Ethereum transactions for given addresses using the Etherscan API.

## Features

- Fetches normal, internal, ERC20, ERC721, and ERC1155 transactions
- Displays all transactions in a single table with the most relevant information
- Shows the total number of transactions and transactions per address

## Usage

1. Clone the repository or download the provided `index.html` file.
2. Open `index.html` in your preferred web browser.
3. Enter your Etherscan API Key and a comma-separated list of Ethereum addresses.
4. Click the "Fetch and Display Transactions" button.
5. The application will fetch the transaction data and display it in a table below the button.

The application consists of a single index.html file with embedded JavaScript and CSS. The JavaScript code fetches transaction data from the Etherscan API and renders it in an HTML table.

## Dependencies 
The application uses the following dependencies:

- Etherscan API

## License

This project is open source and available under the MIT License.

## Documentation (Lite)

Class EtherscanApi: Represents the Etherscan API service.
        constructor: Initializes the API key and base URL.
        fetchTransactionData: Fetches transaction data based on the provided parameters, handling pagination and rate limits.
        buildURL: Constructs the URL for the Etherscan API request.

fetchAndDisplayTransactions: The main function that is triggered when a button is clicked. It initializes the EtherscanApi instance, processes the input Ethereum addresses, initializes the address transaction counts, and fetches and displays all transactions.

initializeAddressTransactionCounts: Initializes the transaction counts for each address with a count of 0.

fetchAllTransactions: Fetches transactions for all transaction types and addresses.
* This function iterates over different transaction types (normal, internal, ERC20, ERC721, and ERC1155) and fetches transactions for all addresses for each transaction type. It does not fetch all transactions in one call; instead, it combines the transactions fetched by 

fetchTransactionsForAllAddresses for each transaction type.
* fetchTransactionsForAllAddresses: This function fetches transactions of a specific transaction type for all addresses. It uses the fetchTransactionsForAddress function to fetch the transactions for each address and then combines the results.

fetchTransactionsForAllAddresses: A function that fetches transactions for a specific transaction type for all addresses.

fetchTransactionsForAddress: Fetches transactions for a specific transaction type for a single address.
* This function fetches transactions of a specific transaction type for a single address. It calls fetchSingleAddressTransactions to fetch the transactions and then maps the results to include the transaction type.

fetchSingleAddressTransactions: Fetches transactions for a single address and a single transaction type using the EtherscanApi instance.
* This function fetches transactions for a single address and a single transaction type using the EtherscanApi instance.

displayAllTransactions: Displays the transaction summary and transaction table.

displayTransactionSummary: Generates and displays a summary of the transaction counts for each address and the total count.

generateSummaryItems: Helper function to generate summary items as a string for display.

displayTransactionTable: Creates and displays an HTML table with the transaction data.

createTransactionTable: Creates an HTML table element with transaction data.

createTransactionTableHeaders: Generates the HTML table headers for the transaction table.

createTransactionTableRows: Generates the HTML table rows for the transaction data.

createEachTransactionTableRow: Generates a single HTML table row for a transaction.

getTransactionValue: Retrieves the transaction value based on the transaction type.

getEthOrErc20TransactionValue: Helper function to get the transaction value for normal, internal, and ERC20 transactions.

getTransactionTokenSymbol: Retrieves the token symbol based on the transaction type.
