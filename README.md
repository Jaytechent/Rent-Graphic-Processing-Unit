# Rent and Setup GPU
Guide to Rent, Setup and Connect to GPU servers.

# Step 1. Create a Public SSH using Ubuntu
### 1- Open  Ubuntu Terminal


### 2- In the terminal run:
```bash
ssh-keygen -t rsa -b 4096
```
* You'll see:
```
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa):

```
* Press `Enter` to accept the default location.

```
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
```
* Press `Enter` to bypass setting password.

### 3- Navigate to `.ssh` directory
```
 cat ~/.ssh/id_rsa.pub
```

### 4- Copy the `id_rsa.pub` file content in clipboard
```
Get-Content id_rsa.pub | Set-Clipboard
```
* Your public key is now copied into your `clipboard`

# Step 2. Add SSH KEY to GPU Provider Site
### [Vast.ai:]([https://cloud.vast.ai](https://cloud.vast.ai/?ref_id=62897&creator_id=62897&name=Ubuntu%2022.04%20VM)/) 
* 1- Register in [Vast.ai]([https://cloud.vast.ai/](https://cloud.vast.ai/?ref_id=62897&creator_id=62897&name=Ubuntu%2022.04%20VM))
* 2- Create an SSH key session by going to `three-lines > Keys > SSH Keys` [here](https://cloud.vast.ai/manage-keys/)
* 3- Paste Public SSH key created in your local pc in previous steps.


# Step 3. Rent a GPU & Get your GPU's SSH Command
* Vast  supports  **crypto payments** and cheaper than others
* Vast has  More GPU avalilability, Supporting VM template which is needed for this Prover Node
s

### [Vast.ai:]([https://cloud.vast.ai](https://cloud.vast.ai/?ref_id=62897&creator_id=62897&name=Ubuntu%2022.04%20VM)/)
* 1- Select Ubuntu(Vast) template [here]([https://cloud.vast.ai](https://cloud.vast.ai/?ref_id=62897&creator_id=62897&name=Ubuntu%2022.04%20VM)/)
* 2- Choose a supported GPU (I recommend =24GB GPU vRAM)
* 3- Increase `Disk Space` slidebar to `100GB`
* 4- Top-up credits with crypto and rent it.
* 5- Go to [instances](https://cloud.vast.ai/instances/), refresh the page, click on `key` button.
* 6- If you don't see a ssh command in `Direct ssh connect:` section, then you have to press on Add SSH Key.
* 7- Copy SSH Command, and Replace `-L 3000:localhost:3000` in front of the command.


# Step 4. Connect to GPU server using SSH Command
* You must get a command like this. For example, it's hyperbolic's SSH Command:
```
ssh ubuntu@xxxxxx.hyperbolic.xyz -p 123456
```
* You can add this flag: `-L 8080:localhost:8080` in front of you command to get access to apps running on port 8080 from your local pc.
* Paste and Enter the command you copied in `Ubuntu Terminal` to access your server.
* Enter the password you set for SSH public key (if you set before) and press enter to open your GPU terminal
* Add this flag: `-i $env:USERPROFILE\.ssh\id_rsa` in front of your command, to specify the ssh privatekey file.
* You should now be in your GPU environment and run your node now.
