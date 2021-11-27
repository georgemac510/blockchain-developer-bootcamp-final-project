# blockchain-developer-bootcamp-final-project
This is my final project submission for the Consensys Academy Bootcamp 2021.

<h1>Legal Document Form Repository</h1>

# About

The Legal Document Form Repository will be a datastore and marketplace to purchase common filable-PDF legal documents such as a simple will, articles of incorporation for specific states or provinces, bill of sale sample, building contract, business plan, etc. Currently, the legal documents are stored as .jpg files, but in future iterations, the documents will be filable-PDFs so that the user can use it for their own purposes and fill them with their own unique information. The legal documents are stored on IPFS and deployed to the Rinkeby Ethereum testnet as ERC721 NFTs. A live demo can be found at: https://legaldoc.surge.sh/ .


# Prerequisites

1. Install Node 14.16.1 via `nvm` if not installed

        $ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash
        $ source ~/.nvm/nvm.sh
        $ nvm install 14.16.0 
        $ nvm alias default 14.16.0 
        $ nvm use default

2. Install truffle if not installed

        $ truffle version
        $ npm install -g truffle

3. Install ganache-cli if not installed

        $ ganache-cli --version
        $ npm install -g ganache-cli
        $ ganache-cli

    Make sure that port 8545 is listed in truffle-config.js for ganache-cli

4. Install and run IPFS if not installed

        $ jsipfs version
        $ npm i -g ipfs
        In another terminal run IPFS
        $ jsipfs daemon

5. Install `yarn` if not installed

        $ yarn --version
        $ npm install --global yarn

# Migrate contracts and Run app

6. Git clone repo, enter directory and install

        $ git clone https://github.com/georgemac510/blockchain-developer-bootcamp-final-project.git
        $ cd blockchain-developer-bootcamp-final-project/
        $ yarn install

7. Compile, migrate and test contracts on development network. Make sure `truffle-config.js` is properly configured.

        Compile and migrate
        $ truffle compile
        $ truffle migrate --reset --network ganache_cli
        Test
        $ truffle test

8. Interact with deployed contract and mint tokens. Make sure `jsipfs daemon` is running in another terminal.

        $ truffle exec src/backEnd/scripts/mint.js --network ganache_cli

9. Run app on `localhost:3000`

        $ yarn start

    App should open up on `localhost:3000`

10. Buying legal docs on app

    a. Make sure that you are logged on to Metamask, your network is set to `Localhost 8545` and connected to `localhost:3000`

    b. Fund your Metamask account by grabbing the first private key from `ganache-cli` and import it. Now you have ETH for purchases.
    
    c. Under your chosen legal doc image, click the `Buy` button, confirm the purchase on the Metamask pop up window. You are now the proud owner of a legal doc to meet your needs.

11. Ethereum Rinkeby testnet deployment. make sure that `truffle-config.js` is properly configured for the Rinkeby network.

    a. Switch Metamask network to Rinkeby with a funded Rinkeby ETH account.
    b. Migrate contracts for Rinkeby and mint tokens.

        $ truffle migrate --network rinkeby
        $ truffle exec src/backEnd/scripts/mint.js --network rinkeby

    c. Verify deployment at https://rinkeby.etherscan.io/ by searching your new contract address and checking under `Erc721 Token Txns` to see the minted tokens.

The demo was deployed as a website to the Rinkeby testnet at https://legaldoc.surge.sh/. The address of the deployed contract is at the bottom of the website page.










    