# UniversityOfExeter
Smart Contracts: BEEM161 - Basic Smart Contract Analysis

Welcome to today's exercise on Basic Smart Contract Analysis. In this session, we will be discussing the tools and techniques used to analyze and understand Solidity smart contracts. Specifically, we will be using VSCode, Solidity Visual Developer, RemixIDE, and Metamask, with the optional tool, Slither.

Smart contracts are self-executing programs that run on a blockchain, and they have become increasingly popular due to their ability to automate complex processes and enforce agreements without the need for intermediaries. However, like any other software, smart contracts can have bugs or vulnerabilities that can lead to unintended consequences, such as loss of funds or theft.

Therefore, it is important to have a good understanding of how to analyze and evaluate smart contracts to ensure they are secure and function as intended. In this lecture, we will explore the various tools and techniques used in smart contract analysis, and demonstrate how they can be used to identify potential issues and improve the overall security and functionality of the contracts.

So, let's get started by discussing the tools we will be using, including VSCode, Solidity Visual Developer, RemixIDE, Metamask, and Slither, and how they can be used in smart contract analysis.

To follow along with the exercise you will need tohe following:

1.	We will be using VSCode, Solidity Visual Developer, RemixIDE, Metamask | *Optional* Slither.

2.	Open VSCode and Install any needed tools to follow along.

A.	https://marketplace.visualstudio.com/items?itemName=tintinweb.vscode-solidity-language

B.	https://marketplace.visualstudio.com/items?itemName=tintinweb.graphviz-interactive-preview

C.	https://marketplace.visualstudio.com/items?itemName=tintinweb.vscode-ethover

D.	https://marketplace.visualstudio.com/items?itemName=tintinweb.vscode-LLL

E.	https://marketplace.visualstudio.com/items?itemName=JuanBlanco.solidity

F.	https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn?hl=en

G.	https://remix.ethereum.org/

H.	*OPTIONAL* https://github.com/crytic/slither/wiki

3.	Set up a custom network in Metamask with these settings.

Network name: BSC Testnet

New RPC URL: https://data-seed-prebsc-1-s1.binance.org:8545/

Chain ID: 97

Currency symbol: BNB

Block explorer URL: https://testnet.bscscan.com

4.	Get some BSC Testnet BNB.

A.	https://testnet.bnbchain.org/faucet-smart

B.	https://faucet.quicknode.com/binance-smart-chain/bnb-testnet/

C.	https://faucet.triangleplatform.com/bnbsmartchain/testnet

6.	Open the ‘UOEcontract.sol’ file.

7.	What type of contract is this?

8.	What would this be used for?

9.	Create a new workspace/folder in VSCode and call it ‘UOEcontract’.

10.	Create a folder inside called ‘contracts’.

11.	Right click on the ‘contracts’ folder and select ‘New File…’.

12.	Name the new file ‘UOEcontract.sol’.

13.	Copy the smart contract code from the GitHub repository into the ‘UOEcontract’ file and save.

14.	If you have Solidity Visual Studio installed *NOTE: You will need it for the practical lesson on Friday* you will see some options above line 1 of the code.

15.	These are “report | graph (this) | graph | inheritance | parse | flatten | fungSigs | uml | draw.io”, we will cover these soon.
16.	First, we will fix the compiler version problem.

17.	Look at the pragma version and you will see it is ‘pragma solidity ^0.7.4;’. This means that we need a compiler version that is 0.7.4 or higher but below version 0.8.0.

18.	To fix this we will be using Solidity Visual Developer’s built in compiler. Right click anywhere on the ‘UOEcontract.sol’ file and select ‘Solidity: Select workspace compiler version (remote)’ and select ‘0.7.6’.

19.	Using the latest stable version is always best practice when building smart contracts. However this is an old contract so ‘0.7.6’ is the most up to date version that will compile the smart contract.

20.	Next right click anywhere on the ‘UOEcontract.sol’ file and select ‘Solidity: Compile contract’.

21.	You will see a new folder called ‘bin’ and inside that another ‘contracts’ folder which contains the abi and other formatted data that was generated from the various libraries, interfaces and contracts during compilation.

22.	Next we are going to create a new folder inside our main ‘UOEcontract’ folder called ‘reports’.

23.	Now that we have our development workplace setup we can open the ‘UOEcontract.sol’ file. Take a look at the code and see if anything looks out of place for a smart contract of this type – Mentioned earlier.

24.	Scroll back to line 1. Let’s explore the option above this line.

A.	Click on report and wait for the report to open to the right. Save the file in the ‘reports’ folder and close it for now. (You may need to close and reopen VSCode)

B.	Click on ‘graph (this)’ and you will get a Graphviz DOT interactive flow chart. You can save the corresponding Graphviz DOT file in the ‘reports’ folder. These are useful to visualize the flows between contracts and functions particularly when writing reports. It is not relevant to today’s exercise. Play around with this as you wish.
C.	Clicking ‘graph’ does the same as ‘graph (this)’

D.	Click on ‘inheritance’ and you with get a Graphviz DOT interactive inheritance graph. You can save the corresponding Graphviz DOT file in the ‘reports’ folder. These are more useful for analysing more complex code ecosystems like DAO’s.

E.	Click on ‘parse’ and you will be presented with the child structure of a smart contract visually in a hierarchical tree-like structure.

i.	Contract hierarchy: The top-level of the child structure represents the overall contract structure, with each contract listed as a separate node in the hierarchy. Child nodes within each contract represent different elements of the contract, such as functions, variables, and events.

ii.	Function hierarchy: Within each contract, the child structure represents the different functions defined in the contract, with each function listed as a separate node in the hierarchy. Child nodes within each function represent the different statements and expressions within the function.

iii.	Variable hierarchy: Within each contract or function, the child structure represents the different variables defined in the contract or function, with each variable listed as a separate node in the hierarchy. Child nodes within each variable represent the different attributes of the variable, such as its type, name, and default value.

iv.	Modifier hierarchy: Within each contract, the child structure represents the different modifiers defined in the contract, with each modifier listed as a separate node in the hierarchy. Child nodes within each modifier represent the different statements and expressions within the modifier.

Using "parse" in Solidity Visual Developer provides a useful way to understand the organization and relationships between the different elements of a smart contract. For this exercise, it is not necessary to analyse this data. You can save it in the reports folder.

F.	Clicking on ‘flatten’ will do nothing with this smart contract. The "flatten" feature is used to merge all of the contracts in a Solidity project into a single file.

G.	Click on ‘funcSigs’ will generate the function signatures of the smart contract functions. A function signature is a unique identifier that represents the function name and its parameters. This provides a convenient way to generate and view function signatures for Solidity smart contracts, making it easier to interact with and debug contracts. Save this file in the ‘reports’ folder.

25.	Right click on the ‘Sūrya's Description Report.md’ and select ‘Open With…’ then select ‘Markdown Preview’ and you get a well formatted markdown of the libraries, interfaces, and contracts.

26.	Analyse this file. The function names although they can be named anything by the developer may show some anomalies. We are looking for functions with a ‘Mutability’ which is a function that can modify the state of a smart contract. We are also looking for ‘Modifiers’ with the ‘onlyOwner’ and ‘authorized’ values.

27.	Functions meeting these requirements exclusively give the smart contract owner or authorized user the ability to modify or change the state of a contract using that specific function.

28.	Identify any functions meeting the requirements above that you think may be malicious and require further analysis and explain why.

29.	How can we take a closer look at what these functions do?

A.	Use the ‘ftrace’ button you may have noticed above the functions in the ‘UOEcontract.sol’ file.

30.	Click on the ‘ftrace’ buttons of some of the functions you thought might be malicious. What do you see?

A.	‘clearStuckBalance’ could be a liquidity pool drainer, manual testing would need to be performed (centralized privilege).

B.	‘tradingStatus’ likely switches trading on and off so could be used as a honeypot (centralized privilege).

C.	‘purge’ high probability of being a liquidity pool drainer, manual testing would need to be performed (centralized privilege).

D.	‘purgeBeforeSwitch’ high probability of being a liquidity pool drainer, manual testing would need to be performed (centralized privilege).

E.	‘switchToken’ potential use for a honeypot (centralized privilege).

F.	‘setTxLimit’ can be used for a honeypot (centralized privilege).

G.	‘setFees’ can be set to 100% and take all trade values as fees (centralized privilege).

H.	‘airdrop’ there is a lot going on here with a lot of state change calls, ‘getCumulativeDividends’ gets called three times, an airdrop shouldn’t be subject to dividends. There is also an internal transfer called ‘_basicTransfer’ using inheritance, any privileged function that calls internal transfers is suspicious.

I.	‘airdropFixed’ is the same as the ‘airdrop’ function which raises more suspicion around this being an obfuscated malicious function.

31.	For this exercise we are going to test the theory that this is an obfuscated malicious function on the BSC Testnet. Static analysis has its limits, but we have only used one tool and one method of identifying suspicious functions by analysing the smart contract code. There are many more opensource static analysis tools out there.

32.	Open RemixIDE in your browser and use a default workspace and delete all files and folders.

33.	Create a new file called ‘UOEcontract.sol’ and copy the smart contract code from either your VSCode file or the GitHub repository.

34.	In RemixIDE open the ‘Solidity Compiler’ tab and select compiler ‘0.7.6…’.

35.	Open the ‘Advanced Configurations’ menu and select the ‘Enable Optimization’ tick box. Then click ‘Compile UOEcontract.sol’

36.	Next open the ‘Deploy & run transactions’ tab. In the ‘Environment’ dropdown select ‘Injected Provider’ and connect your Metamask wallet with the custom network we set up earlier.

37.	In the ‘Contract’ dropdown select ‘UOEcontract – contracts/UOEcontract.sol’ option.

38.	We are now ready to deploy the smart contract so click ‘Deploy’ and Metamask should pop up with a Contract Deployment transaction. Now click confirm.

39.	Congratulations you just deployed a smart contract onto a live blockchain.

40.	In RemixIDE you will see you deployed smart contract in the ‘Deployed Contracts’ section. Expand this section to reveal more information about the contract. The buttons in orange represent function calls that require a gas fee to process, the blue buttons represent functions that are free to call. Click on some of the blue ones and see what they do.

41.	The ‘airdrop’ function does not work until a liquidity pool has been made. I will show you how that works.

42.	I have set up a ICO presale link here https://dx.app/dxsaleview?saleID=61&chain=BNB-Test for today’s exercise.
