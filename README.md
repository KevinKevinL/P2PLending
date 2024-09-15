# Peer-to-peer Lending Platform

## Technology and Tools

- **Blockchain Platform:** Sepolia
- **Frontend:** HTML, CSS, JavaScript
- **Backend:** Python (Flask), Node.js
- **Smart Contract Language:** Solidity
- **Database:** SQLite
- **Cloud Services:** Render

## Implementation

### Smart Contracts

Use Remix to write, deploy, and test smart contracts on the blockchain.

**Contract Structure:**

- Inherits from Token and Calculator contracts
- Defines structures for Depositors, Borrowers, BorrowOptions, and BorrowRecords

**Key Features:**

- Depositor functions: register, deposit money, add and adjust borrowing options
- Borrower functions: register, deposit collateral, borrow money
- Repayment function

**Main Components:**

- Depositors can set lending terms (interest rate, collateral rate, etc.)
- Borrowers can deposit collateral and borrow money based on available options
- The contract manages token transfers between parties
- Implements interest calculation and repayment processing

**Security Measures:**

- Uses modifiers to restrict access to certain functions
- Implements checks for sufficient balances and valid conditions

**Data Management:**

- Uses mappings to store depositor, borrower, and loan information
- Provides functions to view borrowing options and loan records

**Token Integration:**

- Uses an ERC20 token for transactions
- Manages approvals and transfers of tokens between users and the contract

### Coding

**Frontend Development**

- Use technologies like HTML, CSS, JavaScript to build an intuitive user interface (UI).
- Use libraries such as web3.js (for JavaScript) and ethers.js to interact with the Ethereum blockchain.

**Backend Development**

- Develop the backend server using Node.js with frameworks Python with Flask
- The backend handles the interaction between the frontend and the blockchain, processing user requests, and sending necessary data to the Ethereum network via app.py and web3.js.
- Using the pysqlite3 as the database library, which is a light database. We store the user name, depositor information and borrower information.

**Smart Contract Integration**

- Use the Solidity programming language to write smart contracts for the Ethereum platform. We code 7 .sol documents and achieve these function in app.py by constructing many route linking the .html documents.
- Deploy the contracts to the Ethereum blockchain on the remix. This process includes compiling the contracts, testing them on a local blockchain (like Ganache), and finally deploying them to a public testnet: sepolia.

**Integration of Blockchain Features**

- Implement key blockchain features, such as token transfers, interacting with decentralized applications (dApps), or verifying on-chain data.
- Ensure smooth communication between the frontend, backend, and the Ethereum blockchain through API calls and smart contract events.
- We Implement key blockchain features like token transfers and interacting with decentralized applications (dApps), user can transfer their token into the smart contract and other user can borrow them easily, just need to connect their wallet.

### Testing

**Testing Process**

- Test the function of smart contract and deploy it.
- Check the routes in app.py linking the backend and frontend.
- Ensure the backend or frontend can interact with deployed smart contracts using web3.py libraries.
- Ensure the database connect the dapp and receive the data successfully.
- Test a lot of data input to ensure it runs good.

**Bugs Faced**

1. In the smart contracts, use an IERC20 token for transactions but it always has panic issue. Every time it deploys and then retrieves the token contract, for some reason, the gas fees are too high, making our test tokens insufficient for the operation.
2. In app.py, can't connect the database to get the information that users input.
3. Can't get the data from user input to database.

**Bug Fixing**

1. For problem 1, approve the token advanced, not in the code. We approve the authorization on the Etherscan website.
2. For problem 2, modify all the submissions to form format, and insert data into database after the user input.
3. For question 3, we have spent a significant amount of time researching it but haven't been able to solve the issue. Using the method taught by the teacher in class resulted in some errors. For example, every time a specific route is executed, a data insertion operation is performed. However, there isn't user input every time that route is accessed, which leads to errors or the insertion of default values. There is no issue with just inserting and displaying the username, so for now, we have implemented a database operation that displays the username. Therefore, we have temporarily separated the database connection code from the main code, and we plan to refine it later when we have learned more or found a solution.

## Links

Github: https://github.com/KevinKevinL/P2PLending/tree/master

Link: [https://p2plending.onrender.com](https://p2plending.onrender.com/) .

Since using free plan, the web service will spin down with inactivity, so please inform me to redeploy it when you check the website.

