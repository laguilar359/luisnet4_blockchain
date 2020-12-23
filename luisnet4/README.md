## luisnet4 Blockchain Network 

In this project, we have created a private testnet to explore potentials for blockchain. We have created a custom Genesis file, and asked Geth to use that genesis file to create our own genesis block, which in turn is the start of our custom private blockchain. 

To test the blockchain, we will start the network nodes and connect to MyCrypto to send transactions.

### Network Configuration
Consensus Engine: Clique - Proof-of-Authority
Blocktime: 15 seconds (default)
Chain/Network ID: 111

### Required Installations
1. Geth : Command line interface for running Ethereum node implemented in Go Language.
2. MyCrypto : A free, open-source interface for interacting with the blockchain.

### Setup Instructions and Dependencies

I. INITIALIZE NODES
1. Clone the luisnet4 directory into your local repository.
    a. Ensure that Geth is pre-installed.
2. In Terminal or Bash, navigate to the luisnet4 directory and initialize each node with the "luisnet4.json" network name.
    a. node1: ./geth --datadir node1 init luisnet4.json
    b. node2: ./geth --datadir node2 init luisnet4.json

II. RUN NODES TO BEGIN MINING BLOCKS
1. Open Terminal or Bash window and navigate to the luisnet4 directory and start node1 with the following command:
    a. "./geth --datadir node1 --unlock "0x4D7aB3B4b8100A3C001932DA5030Fc5Ce04D3672" --mine --rpc --allow-insecure-unlock"
    b. The following Flags must be declared:
        i. --datadir : Specifies the node directory.
        ii. --unlock : Unlocks the specified account.
        iii. --mine : Tells teh node to begin mining the block.
        iv. --rpc : Enables the http-rpc option.
2. Hit enter and while node1 begins to run, enter the account password: Newla1978
3. While node 1 is running, open a new Terminal or Bash window and navigate to the luisnet4 directory and start node2 with the following command:
    a. "./geth --datadir node2 --unlock "0xa786A40B12118d2723Be895970De0321f72c3C61" --mine --port 30304 --bootnodes "enode://051ea2ea796489c4c4cf73ce52ae71f8ad6e8970d18cca398b151ceef3e1b3fe37c5ef9f11460886a377aa5ed5c1c0a9692a478a48d0980c58cdb3e7addf5dfd@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock"
    b. The following Flags must be declared:
        i. --datadir, --unlock, --mine : Perform the same functions as stated in step 1b above. 
        ii. --port : Specifies a new port "30304" since port "30303" is used by node1 by default.
        iii. --bootnodes : States the "enode" address from node1 to connect with node2.
        iv. --ipcdisable : For Windows machines. Disables the ipc-rpc server.
        v. --allow-insecure-unlock : Allows insecure account unlocking when account-related RPCs are exposed by http.
4. Hit enter and while node2 begins to run, enter the account password: Newla1978

### Connect network to MyCrypto and Send Transactions

1. While node1 and node2 are running, open MyCrypto.
2. Within MyCrypto, select "Change Network" [bottom left], then choose "Add Custom Node"
3. In the "Set Up Your Node" window, enter the following:
    a. Node Name: luisnet4
    b. Network: Custom
    c. Network Name: luisnet4
    d. Currency: ETH
    e. Chain ID: 111
    f. URL: http://127.0.0.1:8545
4. Once all required settings are entered, select "Save & Use Custom Node"
5. Go back to the MyCrypto homepage and select "View & Send" [top right].
6. Access your wallet selecting the "Keystore File" option at the bottom, and follow the steps below:
    a. Hit the "SELECT WALLET FILE" option.
    b. Navigate to the luisnet4 directory.
    c. Choose the node1 "directory"
    d. Then choose the "keystore"
    e. Select the file contained within.
    f. Then enter the account password (Newla1978) and hit the "Unlock" button.
7. In the "To Address" field, enter the node2 public key (0xa786A40B12118d2723Be895970De0321f72c3C61).
8. Choose the Amount of ETH to send.
9. Select "Send Transaction" then in the popup window, select "Send"
10. Verify the transaction status by selecting the "Check TX Status" button in the popup window, or by navigating to the "TX Status" tab in the main window.

### Congratulations! You have joined the luisnet4 blockchain network!
