**SHELBY CLI SETUP GITHUB**


**Step 1:** 

. Create a GitHub Repository

. Go to https://github.com/new

. Enter a repository name (e.g. shelbynode)

. Select Public or Private

. Check "Add a README file"

. Click Create repository

. Click the green Code button

. Select → Open with Codespaces → + New codespace

. Wait for load


**Step 2: Commands**

run these commands in terminal one by one

```bash
sudo apt-get update && sudo apt-get upgrade -y
```
```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - && sudo apt-get install -y nodejs
```
```bash
node -v
npm -v
git --version
```

**Step 3: Install Shelby CLI & Aptos CLI**
```bash
npm i -g @shelby-protocol/cli
```
```bash
shelby --version
```
```bash
curl -fsSL "https://aptos.dev/scripts/install_cli.sh" | sh
```

**Step 4: Get your APY key**

Go to - https://geomi.dev

Click Sign Up and create an account

On the overview page, click "API Resource"

Fill:

Network: Shelbynet

Resource Name: shelby

Usage Description: storage

Click Submit

Copy your API key (starts with aptoslabs_...)

**Step 5: Initialize Shelby**

**Run:**

```bash
shelby init
```

**When prompted:**

| Prompt         | Action                                            |
|----------------|--------------------------------------------------|
| API Key        | Paste your API key from Step 4                   |
| Private Key    | Press Enter to generate new (or paste existing)  |
| Other prompts  | Press Enter to accept defaults                   |

**Step 6: Get APT and ShelbyUSD testnet faucet**

```bash
shelby faucet --no-open
```

This displays a faucet URL with your address pre filled. Copy it with ctrl+c and open in your browser on new tab.

claim APT faucet and then ShelbyUSD

**Step 7: check balance**

Run
```bash
shelby account balance
```

If balance shows 0 like this

<img width="770" height="215" alt="image" src="https://github.com/user-attachments/assets/a2c132d6-b04b-48cf-83da-4809e8a89645" />

then check explorer on shelbynet once: https://explorer.aptoslabs.com/

if you can check your balance on explorer and not on codespace then run- ```shelby context list``` , check which chain you're connected like this

<img width="713" height="486" alt="image" src="https://github.com/user-attachments/assets/6ce6ced8-03c5-4e1c-a525-ca648e493430" />

if its showing testnet "(default)" then run- ```shelby context use shelbynet``` , it will change the network from testnet to shelbynet

Now check balance

```bash
shelby account balance
```

**Step- 8: Upload File**

Create a test file

```bash
echo "Hi Shelby!" > test.txt
```

Upload the file

```bash
shelby upload test.txt myfile.txt -e "in 7 days" --assume-yes
```

