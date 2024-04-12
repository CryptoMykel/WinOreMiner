# WinOreMiner
Mining Ore on Windows CLI


#Things You Need
1. Ore CLI Miner
2. Rustup/Cargo
3. Solana CLI wallet
4. 0.01-0.02 SOL
5. Free RPC "Paid preferred" 


#Links

RPC "free & Paid": https://account.getblock.io/sign-in?ref=MDdiZTU0OGMtODg0MC01Y2JjLWI3ZDMtMTU3YzRhYzQyNTY2

RustUp: https://rustup.rs/

SolanaCLI: https://docs.solanalabs.com/cli/install

Ore Website: https://ore.supply/


#Start Building

1. Install RustUp -------------------------------------------------------------------------------------------------------------------

- goto the RustUp webiste and download
- click/run the exe as admin
- went promt enter 1 and press Enter
- exit terminal when done


2. Isntall Solana CLI ---------------------------------------------------------------------------------------------------------------
 
- open admin terminal
- goto the Solana Docs page in the links
- enter these in admin terminal  
$ cmd /c "curl https://release.solana.com/v1.18.4/solana-install-init-x86_64-pc-windows-msvc.exe --output C:\solana-install-tmp\solana-install-init.exe --create-dirs"  
$ C:\solana-install-tmp\solana-install-init.exe v1.18.4 
- exit terminal when done
- open new terminal
- check the version  
$ solana --version


3. Install Ore-CLI ----------------------------------------------------------------------------------------------------------------

- open a admin terminal and run  
$ cargo install ore-cli


4. Create And Back Up Wallet ------------------------------------------------------------------------------------------------------

- create the wallet  
$ solana-keygen new

- save the Recovery phrase and password
- goto your keypair folder it told you "C:\Users\ "keypair location"\.config\solana\id.json"
- open and copy the id.json


5. Top Up Wallet-----------------------------------------------------------------------------------------------------------------

- get your address  
$ Solana address

- send 0.01-0.02 SOL here


6. Get Your RPC-----------------------------------------------------------------------------------------------------------------

- goto the RPC link and create a account
- copy your free rpc api 
- OR pay for you basic tier about 14-20$ 


7. Start Mining Ore-------------------------------------------------------------------------------------------------------------

- create a text file and enter this

  @echo off
  
  :loop
  
  echo start mining ore...
  
  ore --rpc "your free or paid RPC" --keypair C:\Users\ "keypair location"\.config\solana\id.json --priority-fee 8000000 mine --threads " your PC thread count"
  
  goto loop

- change the keypair location to your that you saved from step 5
- click save as
- name the file "OreMiner.bat"
- save to desktop or anywhere you like
- right click the file "run as admin"


#Helpful Commands---------------------------------------------------------------------------------------------------------------

Check ORE Rewards"unclaimed":  
$ ore --keypair C:\Users\ "keypair location"\.config\solana\id.json rewards

Check ORE Balance"claimed":  
$ ore --keypair C:\Users\ "keypair location"\.config\solana\id.json balance

Claim ORE Rewards:  
- you can run this a a batch but watch closly for a claim so you can stop the batch  
$ ore --rpc "your free or paid RPC" --keypair C:\Users\ "keypair location"\.config\solana\id.json --priority-fee 7000000 claim

Check SOL Balance:   
$ solana balance

Check SOL Address:  
$ solana address

Import A SOL Seed Phrase:  
$ solana-keygen recover
