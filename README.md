# cheat_sheets
Quick start "cheat sheets" for various languages

## Git

Set-up Git for the project

    1) Create the local folder / navigate to it in Vscode
	2) forge init . (if problems run: forge init --force .) 
 	3) forge install foundry-rs/forge-std
  		3a) forge install <any other libraries required>
	4) Create the repository in Github
    5) Copy/paste the Github instructions into terminal (as follows):
        git init -b main
        git config user.name "sarobinson2011"
        git config user.email "sarobinson2011@gmail.com"
        git add .
        git status
        (if you forgot to gitignore .env then):
          git git rm –cached .env
        git commit -m “initial commit”
        git branch -M main (not necessary if you already ran “init -b main”)
        git remote add origin <link-to-repo.git>
        git push -u origin main

To Create a new branch

    1) Run the following command:
        ◦ git checkout -b <branch name>

To check with branch you are on

    1) Run the following command:
        ◦ git branch
			(if the local branch isn't updating, try closing and re-opening vscode)

To Clone a Git Repo

    1) Navigate to the folder you want to clone the project to (clone creates the project folder itself)
	So to clone the fountain-backend 
	2) git clone https://github.com/sarobinson2011/fountain-backend.git
	3) cd fountain-backend
 	4) git config --global user.name "sarobinson2011"
	5) git config --global user.email "sarobinson2011@gmail.com"
 	6) 		curl -L https://foundry.paradigm.xyz | bash					// install Foundry for the project
			# restart your shell or source ~/.bashrc / ~/.zshrc, then:
			foundryup
	7)		forge --version
			forge build
			forge test -vv
	8) Then start coding.

Directory tree structure -BASH commands

    1) tree -a -d -L 3 -I "out|cache|broadcast|lib|node_modules|.git"  --> directories only
	2) tree -a -L 3 -I "out|cache|broadcast|lib|node_modules|.git"  -->  files + directories
 	3) tree -a -L 3 -I "out|cache|broadcast|lib|node_modules|.git" > tree.txt  --> save to a file

Directory structure (standard) + Foundry scaffold commands (for the below structure)

```text
.
├── .github
│   └── workflows
├── script
├── src
│   ├── apps
│   │   └── interfaces
│   └── core
│       └── interfaces
└── test
    ├── helpers
    └── mocks


	 # set your project name
	PROJECT="Collectibles"
	
	# make directories first
	mkdir -p "$PROJECT"/{.github/workflows,script,src/apps/interfaces,src/core/interfaces,test/helpers,test/mocks}
	cd "$PROJECT"
	
	# init git + Foundry (force into non-empty dir)
	git init
	forge init . --force
	
	# remove sample files that Foundry added
	rm -f src/Counter.sol script/Counter.s.sol test/Counter.t.sol
	
	# optional .gitkeep for empty dirs
	for d in .github/workflows script src/apps/interfaces src/core/interfaces test/helpers test/mocks; do
	  touch "$d/.gitkeep"
	done
	
	# verify
	tree -a -d -L 3 -I "out|cache|broadcast|lib|node_modules|.git"




Troubleshooting

Error: “...tip of your current branch is behind its remote counterpart…”

Solution: run the following command, then run ‘git push -u origin main’ 

    • git pull --rebase
    • git pull origin main (can use --rebase or merge)
    • if still having issues:
    	• try: git push -f origin main



 

 


