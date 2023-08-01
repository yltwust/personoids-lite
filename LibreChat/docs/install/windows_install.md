# Windows Install

## **Recommended: [Docker Install](docker_install.md)**

**or**
## **[Windows Installer](https://github.com/fuegovic/LibreChat-Windows-Installer)**
(Includes a Startup and Update Utility)

---

## Manual Installation
### Install the prerequisites on your machine

### **Download LibreChat**
   
  - Download the latest release here: https://github.com/danny-avila/LibreChat/releases/
  - Or by clicking on the green code button in the top of the page and selecting "Download ZIP"
  - Open Terminal (command prompt) and clone the repository by running `git clone https://github.com/danny-avila/LibreChat.git`
  - If you downloaded a zip file, extract the content in "C:/LibreChat/" 
  - **IMPORTANT : If you install the files somewhere else modify the instructions accordingly**
  
### **Enable the Conversation search feature:** (optional)
		
  - Download MeiliSearch latest release from : https://github.com/meilisearch/meilisearch/releases
  - Copy it to "C:/LibreChat/"
  - Rename the file to "meilisearch.exe"
  - Open it by double clicking on it
  - Copy the generated Master Key and save it somewhere (You will need it later)

### **Download and Install Node.js**
    
  - Navigate to https://nodejs.org/en/download and to download the latest Node.js version for your OS (The Node.js installer includes the NPM package manager.)
    
### **Create a MongoDB database**
    
  - Navigate to https://www.mongodb.com/ and Sign In or Create an account
  - Create a new project
  - Build a Database using the free plan and name the cluster (example: LibreChat)
  - Use the "Username and Password" method for authentication
  - Add your current IP to the access list
  - Then in the Database Deployment tab click on Connect
  - In "Choose a connection method" select "Connect your application"
  - Driver = Node.js / Version = 4.1 or later
  - Copy the connection string and save it somewhere(you will need it later)
    
### [Get Your API keys and Tokens](apis_and_tokens.md) (Required)
- You must set up at least one of these tokens or APIs to run the app.

### [User/Auth System](../install/user_auth_system.md) (Optional)
- How to set up the user/auth system and Google login.

## Setup and Run the app

### Using the command line (in the root directory)
#### To setup the app:
1. Run `npm ci` (this step will also create the env file)
2. Run `npm run frontend`

#### To use the app:
1. Run `npm run backend`
2. Run `meilisearch --master-key <meilisearch_Master_Key>` (Only if SEARCH=TRUE)
3. Visit http://localhost:3080 (default port) & enjoy

#### Using a batch file

- **Make a batch file to automate the starting process**
  - Open a text editor
  - Paste the following code in a new document
  - The meilisearch executable needs to be at the root of the LibreChat directory
  - Put your MeiliSearch master key instead of "`<meilisearch_Master_Key>`"
  - Save the file as "C:/LibreChat/LibreChat.bat"
  - you can make a shortcut of this batch file and put it anywhere

``` bat title="LibreChat.bat"
start "MeiliSearch" cmd /k "meilisearch --master-key <meilisearch_Master_Key>

start "LibreChat" cmd /k "npm run backend"

REM this batch file goes at the root of the LibreChat directory (C:/LibreChat/)
```
##

## **Update**
- run `git pull` from the root dir
- Run npm ci from root directory `npm ci`
- Build the client by running `npm run frontend`


---

### Note: If you're still having trouble, before creating a new issue, please search for similar ones on our [#issues thread on our discord](https://discord.gg/weqZFtD9C4) or our [troubleshooting discussion](https://github.com/danny-avila/LibreChat/discussions/categories/troubleshooting) on our Discussions page. If you don't find a relevant issue, feel free to create a new one and provide as much detail as possible.
