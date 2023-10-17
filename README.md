# cheat_sheets
Quick start "cheat sheets" for various languages

## Git

Set-up Git for the project

    1) Create the repository in Github
    2) Copy/paste the Github instructions into terminal (as follows):
        ◦ git init -b main
        ◦ git config user.name "sarobinson2011"
        ◦ git config user.email "sarobinson2011@gmail.com"
        ◦ git add .
        ◦ git status
        ◦ if you forgot to gitignore .env then:
            ▪ git git rm –cached .env
        ◦ git commit -m “initial commit”
        ◦ git branch -M main (not necessary if you already ran “init -b main”)
        ◦ git remote add origin <link-to-repo.git>
        ◦ git push -u origin main

To Create a new branch

    1) Run the following command:
        ◦ git checkout -b <branch name>

To Clone a Git Repo

    1) Run the following command:
        ◦ git clone https://github.com/username/example-repo.git

Troubleshooting

Error: “...tip of your current branch is behind its remote counterpart…”

Solution: run the following command, then run ‘git push -u origin main’ 

    • git pull --rebase
    • git pull origin main (can use --rebase or merge)

## Brownie

Brownie commonly used command-line flags (or options) 

-s or --tb: 

	Enables the stack trace for failing tests, providing more detailed information about errors.
    
-v or --verbose: 

	Increases the verbosity of the output, providing more information about the execution process.
    
-n or --network <name>: 

	Specifies the network to use for the command. <name> can be the name of a network defined in the project configuration.



-p or --port <port>: 

	Specifies the port number to use for the network connection.

-H or --host <host>: 

	Specifies the host address to use for the network connection.

-g or --gas: 

	Enables gas usage statistics for contract function calls.

-F or --gas-price <price>: 

	Specifies a custom gas price to use for contract transactions.

-E or --evm-version <version>: 

	Specifies the EVM version to use for local testing (e.g., byzantium, constantinople, istanbul).
    
-I or --import <module>: 

	Imports a Python module before running the command. This allows you to use custom utility functions or libraries in your Brownie scripts.




Brownie networks – add / delete


# mainnet-fork
     ├─id: mainnet-fork
     ├─cmd: ganache-cli
     └─host: http://127.0.0.1
       ├─accounts: 10
       ├─fork: https://eth-mainnet.g.alchemy.com/v2/Eip3WhOPyEilqfLs5xs4dZ76CZs8R43g
       ├─mnemonic: brownie
       └─port: 8545

brownie networks delete mainnet-fork

brownie networks add development mainnet-fork cmd=ganache-cli host=http://127.0.0.1 fork=https://eth-mainnet.g.alchemy.com/v2/Eip3WhOPyEilqfLs5xs4dZ76CZs8R43g accounts=10 mnemonic=brownie port=8545

brownie networks add <development OR mainnet> <id> <cmd> <host> etc.



Brownie update network-config.yaml file (in .brownie) to include Sepolia

    1) Update network-config.yaml with the following:
    
	- chainid: 11155111
	- explorer: https://api-sepolia.etherscan.io/api
	- host: https://sepolia.infura.io/v3/$WEB3_INFURA_PROJECT_ID
	- id: sepolia
	- multicall2: '0x5BA1e12693Dc8F9c48aAD8770482f4739bEeD696'
	- name: Sepolia (Infura)
	- provider: infura


## Import an OpenZeppelin library into a smart contract

For example, you might have this line in your Solidity code:
   
	- import "openzeppelin-contracts-08/token/ERC20/ERC20.sol";

But it's underlined in red with an error (file not found) --> do this:

	- make sure the compiler remapping (‘@openzeppelin’) is correct
	- if needed use the brownie package manager to install the library, e.g.
 
 	- brownie pm install OpenZeppelin/openzeppelin-contacts@3.4.0
	

 

 


