## Introductory Web3 & NFT User Operational Security for the ETH (EVM) Ecosystem.
*This White Paper will be Accompanied by an Infographic / Slide Deck*

1. Summary and Overview of Threat Landscape 
  - List of Never Do's! 
  - Costs of Doing Business 
2. Hardware vs. Software Wallets
3. ENS Domain and Subdomains
4. "Good Enough" Hybrid Hardware and Software Wallet Configuration
  - Configure Software Wallet 
  - Configure Hardware Wallet 
  - Purchase ENS 
  - Configure Subdomains and map to Hardware Accounts
  - Test Transfers 
5. Use cases and Web3 Actions for Each Account:
  - mint-burner.you.eth : software
  - you.eth : hardware 
  - vault.you.eth : hardware
  - defi.you.eth : hardware
  - p2e.you.eth : hardware 
6. Additional OpSec Recommendations and Resources:
  - Tips
  - Links

## Summary and Overview of Threat Landscape (Why Should I Care?!) 

Web3 (connectivity between blockchain and applications) and the evolving NFT (non-fungible token) and P2E (play 2 earn) space require that users own the full responsibility for the security of their increasingly valuable assets. There is no FDIC insurance, nor second chances should your wallet be compromised, or permissions unknowingly granted to a scammer. This is a new responsibility, not previously shouldered on "Consumers/Users". YOU are now the target, not your bank or employer.

Adversaries ARE OUT TO TARGET YOU, and are doing so through a variety of means, both old and specific to the Web3 environment, these include but are not limited to: 

- Social Engineering via Discord, Email, Twitter. 
- Phishing emails containing links to sites which will either compromise your computer, ask for your seed phrase, or attempt to elicit you to sign or interact with malicious contracts. 
- Malicious Contract Deployment "Mints" which will drain either your ETH, ERC-20 tokens, or NFTs.
- Installation of RATs (Remote Access Trojans) which will give an attacker full control of your PC/MAC
- Browser and Plugin exploits, either of Chrome/FFX or your Web3 wallet specifically (MetaMask, XDefi, etc)
- Malicious injections into trusted websites which may redirect or ask for malicious signatures. 
- Smart Contract exploits which while not directly impacting your wallet, will steal your funds if you have entrusted them to a third party (custodial staking for example of NFT's or ERC-20 tokens)
- Etc... 

These methodologies are not new, but they are now being applied to users with little technical or security knowledge instead of major corporations and governments with full time security teams and tooling. For the purposes of this guide to secure wallet set-up and usage we will focus on the most popular tooling, Metamask + Ledger + ENS, similar instructions apply to other software and hardware wallets, or domain providers which can route eth transactions. 

### List of Never Do's! 

Your Web3 identity and assets live on the blockchain, this is accessed through a "wallet" of your choosing. However contrary to the name, the "Wallet" does not in-fact contain anything. It's simply the key which allows you to interact with other entities on the block chain. Your private key or "wallet" came into existence by using 12-24 words from a [BIP-39 wordlist](https://www.blockplate.com/pages/bip-39-wordlist) to generate a private key. 

Put simply your "seed phrase" is the master key to everything you do in web3. This single seed phrase will create multiple public addresses, which can be used for different purposes, and should one be compromised by any means other than your seed phrase being stolen or shared, the others are still secure. 

1. DO NOT GIVE OUT YOUR SEEDPHRASE
2. DO NOT STORE YOUR SEED PHRASE ON YOUR COMPUTER
3. DO NOT TAKE A DIGITAL PICTURE OF YOUR SEED PHRASE
4. DO NOT IMPORT YOUR _HARDWARE_ SEED PHRASE INTO A _SOFTWARE_ WALLET
5. There are no exceptions to these rules, if you violate them, you will lose everything you hold. 

Note: if your seedphrase is lost (your wallet compromised) it doesn't matter if you had a hardware or software wallet, the adversary has full control of everything, HOWEVER, so do you. Unlike losing a regular wallet, you now "share" access with the adversary. So transfer everything out as quickly as possible and pray. 

There are very many "shouldn't do without research and trust's" in Web3, but in each of those cases there are also times where they may be done securely and diving into each use case is beyond the scope of this document. DO NOT SHARE YOUR SEED PHRASE.

### Costs of Doing Business in Web3

Web3 requires that as a user you will pay for "usage" in the form of gas (expensive on ETH L1, less expensive on L2's such as arbitrum, IMX, ZKxxxx, or EVMos etc) this is different from Web2, but what this means is you are an OWNER and not owned by the companies who previously paid for these bills. ($1-$30 per transaction) [Etherscan Gas Estimator](https://etherscan.io/gastracker)

You will also need to purchase a hardware wallet in order to be remotely secure, this purchase should make sense only when relative to your investment in web3/NFT's/Crypto. ($100-150) [Ledger Nano X](https://shop.ledger.com/products/ledger-nano-x)

You *should* also purchase an ENS (.eth) domain which will make it far easier and more secure to manage your funds. Minimizing user error and providing for additional peace of mind. ($40-100 for 5 year registration of 5+ character domains) (shorter domains cost exponentially more) [ENS Application](https://app.ens.domains/)

**Security should cost no more than 1-1.5% of your overall portfolio.** 

A 200-250$ set-up cost is required for the steps in this guide. So you should be protecting or plan to have $15-$25,000 portfolio, or be protecting items with sentimental/utility value to you which is priceless. 

### Hardware vs. Software Wallets

There are two fundamental types of wallets (ways to hold your keys and authorize transactions on the blockchain) in Web3. Hardware and Software. It's important to understand some key differences, and what neither wallet will protect you from. 

**HARDWARE WALLETS**
- Secret Key and Seed Phrase are never present on your computer/phone.
- Utilizes a dedicated ["Secure Element"](https://en.wikipedia.org/wiki/Secure_cryptoprocessor) to perform cryptographic functions vs your CPU or GPU and normal system memory.
- Requires a *physical* interaction in order to sign, transfer crypto, or interact with any contracts. 
- One physical hardware wallet (one seedphrase) can have multiple public addresses (discussed later)
- Does Protects you if your COMPUTER/PHONE/BROWSER is compromised or even controlled by an adversary. 
- Does NOT protect you if you sign, approve a transfer or interact with a malicious contract.
- Does NOT protect you if your seedphrase is compromised.


**SOFTWARE WALLETS**
- Secret Key is generated and/or stored (usually password protected) on your computer or phone. 
- Utilizes your memory and CPU/GPU for cryptographic functions. 
- Requires only *digital* interaction in order to sign, transfer crypt, or interact with any contracts. (Mouse click/Password)
- One software wallet (one seedphrase) can have multiple public addresses (discussed later).
- Does NOT protect you if your COMPUTER/PHONE/BROWSER is compromised or even controlled by an adversary. 
- Does NOT protect you if you sign, approve a transfer or interact with a malicious contract.
- Does NOT protect you if your seedphrase is compromised.

As you can see both wallets are similar, and even with a hardware wallet, you must be extremely cautious as to what is signed, and what contracts are interacted with. It's for this reason that we will set up 3-4 separate public wallets/keys controlled by the same hardware wallet (+optionally one software), each to be used for different use cases in Web3/NFT/Crypto.  

### ENS Domains and Subdomains, human readable and secure. 

The Etherium Name System, works similarly to normal Domain Name Systems to improve security and human readability however instead of primarily being used to link a website to an IP (google.com -> 10.0.0.1) it links a .eth domain to your wallet address. 

*foobar.eth -> 0x123456789504fc9a8d69381e50bda77965584b8e* 

ENS domains are also NFTs meaning they can be sold and transferred between addresses simply. 

Subdomains may be created from ENS domains which point to separate addresses (vault.foobar.eth)

Purchase and usage of an ENS domain is not mandatory, but will dramatically increase security by providing human readable addresses for transfer, identification, and use case specific interactions. ENS domains may be registered and managed without KYC (DOXXing) with either a hardware or software wallet at https://app.ens.domains/

### "Good Enough" Hybrid Hardware and Software Wallet Configuration

Security is always implemented along a continuum, and it's critical that it not prevent the effective use of the resources it aims to protect. Web3 requires many interactions of different types and varying levels of risk. For this purpose we'll create what I consider to be "Good Enough" for most users with under 1M USD in crypto / NFT assets. 

This will be accomplished with the following tools: 

1) Metamask (Chrome or Firefox) [https://metamask.io/download/](https://metamask.io/download/)
2) Etheerium Name System ENS [https://app.ens.domains/](https://app.ens.domains/)
3) Ledger Nano X (any will work) and Ledger Live [https://www.ledger.com/ledger-live](https://www.ledger.com/ledger-live)

NOTE: If you don't yet have, or chose not to purchase a hardware wallet, you can still implement and ENS and multiple use case specific accounts/subdomains but it is highly recommended that a hardware wallet be utilized. 

### Configure Software Wallet 

In order to effectively interact with the majority of Web3 applications you will need a software wallet installed in your webbrowser. You CAN work with hardware only via a number of means, but this is "Good Enough" security and we want to ensure frictionless access to most/all web3 resources. We will utilize our Hardware wallet (Ledger) primarily through meta-mask as well. 

Metamask is the de-facto standard for Etherium/EVM wallets though there are many others which have been released or in development with more advanced feature sets, and multichain support. Metamask is the choice here as the codebase is oldest and most battle-tested of any software wallet. 

- [ ] Install Metamask for Firefox or Chrome [https://metamask.io/download/](https://metamask.io/download/)
- [ ] Create a New Account. 
- [ ] Enter a complex password to access your new software wallet.
- [ ] Write down your recovery/seed phrase on paper or utilize a fireproof recovery phrase nemonic device such as: [Keystone] (https://www.amazon.com/Cobo-Tablet-Storage-Compatible-Supports/dp/B07RZW8CWY)
- [ ] Name this account in Metamask as "mint-burner"
- [ ] Transfer enough ETH (From a CEX or Crypto Wallet) to this account to complete all following steps. 
   A small test transfer then real transfer of .3-.4 ETH is reccomended in order to complete ENS registrations and ensure all wallets have enough gas. 

### Configure Hardware Wallet and Accounts

Configuring your ledger or other hardware wallet is very similar to that of a software wallet, however it is far more important that you do not enter the generated seedphrase/recovery phrase into electronic media of any sort, and is fireproof storage as referenced above is highly recommended. 

The hardware wallet will be used primarially through Metamask to interact with Web3/NFT/De-FI websites, however this DOES NOT detract from the security provided by the ledger, it simply provides a user friendly pathway to usage. 

- [ ] Purchase a Ledger Nano X or S DIRECTLY from Ledger [https://www.ledger.com/](https://www.ledger.com/)
- [ ] Upon receipt ensure neither the box, nor wallet appear to be opened or tampered with.
- [ ] Download and Install Ledger Live on PC/MAC and/or IOS [https://www.ledger.com/ledger-live](https://www.ledger.com/ledger-live)
- [ ] Power on your Ledger and enter a 6-8 digit pin. (This pin will be used to access your device, but it is NOT a recovery key)
- [ ] Select Create New Account
- [ ] Write down your recovery/seed phrase on paper or utilize a fireproof recovery phrase nemonic device such as: [Keystone] (https://www.amazon.com/Cobo-Tablet-Storage-Compatible-Supports/dp/B07RZW8CWY)
- [ ] Connect your ledger to your PC/MAC and Open Ledger Live
- [ ] Install the "Etherium" application on your ledger
- [ ] Select "+ Add Account" in ledger live, select etherium, and name this account "Main"
- [ ] Connect your ledger to your computer open MetaMask and select "Connect Hardware Wallet"
- [ ] Select your Ledger and newly created Etherium account in the following steps. Label this account "Main" in Metamask. 
- [ ] Transfer .1 eth from your software wallet to your new hardware account using the "Send" -> "Transfer Between My Accounts" option in Metamask. 


Now we will repeat the following steps to add additional public accounts for specific uses controlled by the same ledger, and linked to the same private key. 

You may determine if these use cases are relevant to you or not and either skip or add more accordingly. This guide will cover "Vault" "DeFi" "P2E" and the "Mint-Burner" and "Main" accounts we just set up. 

- [ ] Select "+ Add Account" in ledger live, select etherium, and name this account "Vault" or "p2e" or "DeFi" or custom use case.
- [ ] Connect your ledger to your computer open MetaMask and select "Connect Hardware Wallet"
- [ ] Select your Ledger and newly created Etherium account in the following steps. Label this account "Vault" in Metamask. 
- [ ] Transfer .1 eth from your software wallet to your new hardware account using the "Send" -> "Transfer Between My Accounts" option in Metamask. 


You should now have one software wallet which is labeled "mint-burner" and multiple hardware accounts "main" "vault" "defi" "p2e" etc. These latter should all be visible in Ledger Live, and all should be visible in MetaMask. All accounts should now have a small amount of ETH in them as well (.1). 

### Register ENS Domain 

Registering an ENS domain is entirely optional, if you can easily remember the hexadecimal address's of each of your accounts, when you should use them, and how you should use them you can skip this portion. However, it is highly highly recommended not just for YOUR ease of use but for any counter-party who may send you crypto, nfts, or interact with your addresses. 

It's very easy to typo a hexadecimal address, but myname.eth or vault.myname.eth is clear and concise for you and others. 

You will purchase and register your ENS domain using your "main" hardware wallet account. This way it will be pre-configured for you, and not require additional gas to move/change settings. 

- [ ] Connect to Etherium Name System ENS with your "Main" account in metamask. [https://app.ens.domains/](https://app.ens.domains/)
- [ ] Identify an available XXXXXXXX.eth name using the application. [ENS TOOLS can help in the search](https://ens.tools/domains)
- [ ] Proceed to register the domain of your choice for as long as you'd like. This will take 2 ledger transactions, one to reserve the domain, and the second to purchase it and issue the domain NFT. 
- [ ] Proceed to "My Account" ENS page while still connected with your "Main" account, and select XXXXXXXX.eth from the "Primary ENS Name" drop-down. Select Save. This will require an approval from your ledger. 

This will ensure your address resolves to XXXXXX.eth and vice versa. 

Your address will now appear as XXXXXXX.ETH on etherscan and most web3 applications always securely clarifying which account you are connected with or sending from/to. 


### Configure Subdomains and map to Hardware Accounts

Just as your main XXXXXX.eth domain is now your human readable identifier for web3 we will now use that domain to create sub-domains for each of our hardware wallets (and optionally software mint-burner wallet). By doing this you will always be confident of which account you are using, transferring to or approving a contract interaction or signature with. 

For example once completed you would never do a DeFi transaction, such as provide liquidity with your Vault, nor play a web3 p2e game with your DeFi account, without the need to memorize their hexadecimal addresses. 

This process is straight forward, but will cost small amount of GAS per transaction, as they are recorded on the block chain, it's recommended to wait for low gas conditions to proceed. [Gas Tracker](https://etherscan.io/gastracker)

- [ ] Connect to Etherium Name System ENS with your "Main" account in metamask. [https://app.ens.domains/](https://app.ens.domains/)
- [ ] Navigate to "my account" and select XXXXXX.eth which was purchased earlier. 
- [ ] In the upper right corner select "Subdomains"
- [ ] Select "add subdomain" and enter the label you wish to use for your addressee. "vault" "defi" "p2e" are recommended. 
- [ ] Each subdomain will require a contract interaction and approval from your "Main" ledger account. 
- [ ] Once completed select each newly created subdomain individually. 
- [ ] Select "Add/Edit Record" enter the hexadecimal eth address from Ledger Live for the associated account (e.g. Defi -> defi.xxxxxx.eth) save this change. This will also require an approval from your ledger. 

For Each Subdomain / Account you have created we now want to set that XXXXX.XXXXX.eth account as primary so just like our main account it will reflect as "vault.xxxxxxx.eth" on all web3 applications and etherscan. 

- [ ] Connect to Etherium Name System ENS with your "Vault" account in metamask. [https://app.ens.domains/](https://app.ens.domains/)
- [ ] Proceed to "My Account" ENS page while still connected with your "Vault" account, and select Vault.XXXXXXXX.eth from the "Primary ENS Name" drop-down. Select Save. This will require an approval from your ledger. 
- [ ] Repeat this for each ledger account and subdomain you have created. 


### Test Transfers

As with anything on the blockchain, transfers are irrevocable, so before moving valuable NFTs, DeFi Tokens, or other crypto items, perform a small test transfer. Conduct a small transfer to/from various newly configured XXXXXX.eth to vault.xxxxxxx.eth or p2e.xxxxxx.eth etc. Do this until you are comfortable that everything is properly configured. You can transfer as little as .000001 eth, but gas will still be dependent upon network conditions. 

Trust but Verify, then Verify again. 


Your "Good Enough" hybrid wallet set up is now complete. You should have: 

1) Mint-Burner --> Software Wallet (Optionally mint-burner.xxxxx.eth)
2) Main HW Account --> Ledger -> XXXXX.eth
3) Vault HW Account ---> Ledger -> vault.xxxxx.eth
4) DeFi HW Account --> Ledger -> defi.XXXXX.eth
5) p2e HW Account ---> Ledger -> p2e.xxxxx.eth
6) XXX HW Account ---> Ledger -> XXX.xxxxx.eth

This is easily extensible for any future eth/EVM based usecases you might encounter, additionally these addresses (hex not ENS) will proxy to ETH L2's such as polygon, arbitrum, etc. Making secure use case based segmentation easy and cohesive. 

### Use Cases and Web3 Actions for Each Account

Please use your own judgement as to the amount of time and value risked or locked in these various activities for your personal use case, many will not need a DeFi account or P2E account and may simply use Main, Vault, and Software burner. However we believe the use cases below will satisfy the majority of Web3 user personas:

**NFT Mints & Risky Site Interactions** mint-burner.you.eth : software
- Use this account to mint NFT's or to interact with new and unverified contracts (if you chose to)
- use this account to test/try new services of any sort, with a small amount of funds you are comfortable losing. 
- Use this account for any high interaction/low risk activities that may not be feasible for hardware approvals.
- Do not use this account for staking or any action which will require THE SAME wallet to recover the assets (as it may be burnt/compromised, and is replaceable by design)
  
**Primary Web3 Identity** you.eth : hardware
- This account is "Web3 You" treat it as such! Associate with people and places you trust.
- Use this account to create your persona and accounts on sites which you trust and are well regarded. (OpenSea, Twitter, Instagram etc)
- Use this account to keep simi-valuable NFTs permanently and highly valuable ones here when buying/selling them. 
- Use this account to hold simi-valuable NFTs/erc-20 resources needed for token gated access. 
- Use this account to approve marketplaces and TRUSTED sites to sell/stake NFTs or tokens. 
- Do not use this account to mint NFTs or interact with unverified contracts or websites you do not trust.

**Long Term Secure Storage** vault.you.eth : hardware
- This account is your bank vault treat it as such! In and Out only to your other accounts.
- Use this account should be used simply to store valuable NFTs 
- Use this account to store ETH and Valuable ERC-20's you plan to HODL and not utilize actively. 
- Do not interact with any external contracts from this account. 
- *Signing for proof of ownership should be done only with highly trusted sites if necessary.*

**Decentralized Finance, Staking, Liquidity Providing** defi.you.eth : hardware
- This is your checking account! Direct Deposit, Pay Bills etc. Some contract interactions are needed but only with Trusted DeFi Services.
- Use this account should be used to store ETH and ERC-20 tokens which will be actively traded.
- Use this account should be used to stake or provide liquidity to trusted protocols (e.g. uniswap).
- Use this account should be used to interact primarily with exchanges and derivative trading platforms (on or off chain)
- ETH and ERC20 token transfers should be made to your other accounts from here. 
- Do not use this account to buy/sell/mint NFTs or authorize marketplaces. 
- Do not use this account to connect to or authorize social or p2e dapps. 

**GameFi "P2E" Requiring NFTs and Crypto** - p2e.you.eth : hardware 
- This is your Playstation, Xbox, or Gaming PC. Except you may get paid to play in Web3. 
- Use this account to interact with GameFi contracts (TrasureDAO, Otherside, Sandbox, Realms, etc) which involve NFTs, ERC-20's, Staking, and multiple complex contract interactions. 
- Use this account to store active assets required to participate in P2E activities. 
- Use this account to exchange or sell P2E earnings and NFTs, as often there will be dedicated exchanges for such items. 
- Do not use this account for long term storage of valuable NFTs not critical to P2E
- Do not use this account for social, de-fi staking, or nft minting (aside from those activities captive to p2e game)


### Additional OpSec Recommendations and Resources ###

**Tips**
1) Never sign a contract interaction which "Approve All" unless you are selling an NFT at a trusted marketplace, or staking an NFT or ERC-20 token with a trusted site (usually the tokens creator)
2) If you feel you may have approved something malicious, or a site has been compromised utilize etherscan's token approval checker from the wallet in question: https://etherscan.io/tokenapprovalchecker or https://revoke.cash/
3) It's a good idea to review active approvals every 3-6 months, revoking any which are unneeded or to sites which are not recognizable.
4) Marketplace listings ARE NOT cancelled when you transfer an NFT. e.g. if you move a listed NFT from your main to Vault, and move it back, it will still be for sale as long as the listing is active. 
5) If trading over-the-counter use https://x2y2.io/ private sale or https://atomic0.com/ for trades without giving up custody of your NFTs. (only from Main account)
6) If trading NFTs for NFTs use https://www.nfttrader.io/ this will cost gas, and be very leery of scams. This site does not use links, and if a counter-party says they can't access it, and suggests an alternative it is a scam. 
7) Read the words on any ledger or metamask signature before signing. 
8) All contracts are opensource and visible, if you can read code you can see what is occuring, especially for an NFT mint contract, this is usually pretty basic, don't be afraid to look and learn! 
9) If it's too good to be true it is! Reach out and ask for a second opinion in discord or on twitter before moving forward. 


**Links**

[https://app.forta.network/](https://app.forta.network/)

[https://a16z.com/2022/04/23/web3-security-crypto-hack-attack-lessons/](https://a16z.com/2022/04/23/web3-security-crypto-hack-attack-lessons/)

[https://medium.com/immunefi/security-best-practices-of-web3-wallets-f167eadd9037](https://medium.com/immunefi/security-best-practices-of-web3-wallets-f167eadd9037)

[https://github.com/crytic/blockchain-security-contacts](https://github.com/crytic/blockchain-security-contacts)
