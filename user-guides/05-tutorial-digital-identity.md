## Digital Identity Tutorial
In this tutorial, we will walk through the linking of an external account (in this case, from Acme Bank) and the issuing of a verifiable credential from this external account. We'll help Bob link his Acme Bank account with a Knox wallet, allowing him to send and receive CPFs while also proving his identity through a privacy preserving identity solution.

### Step 1: Setting up DFIs and Wallets
For this tutorial, we will need to create a DFI and a wallet:
- `Acme Bank` with an issuance limit of `$10,000.00 USD` and a created wallet called `Bob's Wallet`

The tutorial will still work with different names and issuance limit values, but this is suggested for the simplicity of the tutorial. Please refer to the tutorials on [Creating an Issuer](./01-tutorial-create-issuer.md) and [Creating a Wallet](./02-tutorial-create-wallet.md) for the tutorials of creating a DFI and creating a wallet respectively.

Here's Bob's Wallet from the view of the DFI.

![image](https://user-images.githubusercontent.com/33649265/212195622-d0276440-b124-4d6d-a145-c447dc9587e6.png)

Within Bob's wallet, we can see three items of functionality:
- Make Payment - This allows Bob to send money from his wallet to another wallet, similar to how we did in [Issuance-Payment-Redemotion](./03-tutorial-issuance-payment-redemption.md)
- Add (Verifiable) Credentials - Adding credentials bridges Knox Identity services from Bob's connected bank accounts. We'll come back here after we've linked an external bank account for Bob.
- Link (Bank) Account - We can have Bob link his (demo) external bank's account to the Knox sandbox.

![image](https://user-images.githubusercontent.com/33649265/212195733-48a30fc6-66a2-4d02-80d8-c76e37e57a0e.png)

Note: Vault wallets do not have the ability to add credentials or link accounts, since they are not for end users.

### Step 3: Link an External Bank Account
Now, let's have Bob link his bank account by clicking `Link Account` in his wallet. This will bring up an external screen that represents Acme Bank's authorization page. 

![image](https://user-images.githubusercontent.com/33649265/202552190-95c94d49-1b9e-463d-aade-7f8973ad0486.png)

Let's have Bob enter his very insecure credentials of username `bob@acmebank.com` and password `knox1234`.

![image](https://user-images.githubusercontent.com/33649265/202548121-670961e6-d439-400e-b5ca-3e79ee67b4fe.png)

Now, we can see a linked external bank account for Bob. We can see Bob's account number, his branch number, and other data related to his account(NOTE: this is only for demo purposes, real Knox systems follow proper in-house data control procedures). 

If we click on the phone icon on the row of the linked account, we will be given a screen like this: 

![image](https://user-images.githubusercontent.com/33649265/202555451-7831ea28-b0e6-4ae7-b35e-85be644c9dd0.png)

Now, if we have a mobile device near us, we would be able to click on the QR code button and scan the QR code with our phone to be able to automatically login to the Knox Networks mobile app and associate the mobile wallet with the account. This tutorial will not cover the mobile app.

If we click to view details on the account (next to the phone icon), we can see this:

![image](https://user-images.githubusercontent.com/33649265/202548543-937e1a99-daa2-41f8-9ace-922b9fb636e5.png)

In the `Details` tab of this screen, we can see some common bank account fields that are required for KYC purposes. 

If we click over to `Wallets`, we can see the public keys of the `Decentralized Identifiers` that are linked with Bob's external account. The most recent DID at the top is the one we created (Bob currently has a few wallets associated with this account right now).

![image](https://user-images.githubusercontent.com/33649265/202549149-9c005bd1-47cd-49a6-8ffc-7bdcfdfdd548.png)

### Step 4: Get a Verifiable Credential
Let's go back to the `Bank Wallets` tab under Acme Bank, and click on `Bob's Wallet` again.

![image](https://user-images.githubusercontent.com/33649265/202549753-93c88d8d-23a2-4a61-821a-35ddd66f7f36.png)

Now that we have an external account linked, let's add some credentials. In this case, the only Verifiable Credentials schema we can add is from the bank account. In addition, unassociated wallets (ones that do not belong to an issuing institution like a commercial bank) cannot be connected to an external account at this time.

In future scenarios, someone could get VCs from a governmental institution (e.g. a driver's license or citizenship card). Let's click `Add Credentials`, and go over to the newly issued credentials in the `Credentials` tab.

![image](https://user-images.githubusercontent.com/33649265/202550311-af917900-12bb-431a-bdd2-9e966a599f1b.png)

The credentials issued can be viewed more in depth by clicking on the accompanying icon.

![image](https://user-images.githubusercontent.com/33649265/202550511-36a26185-37d6-4538-bebf-861890e673d6.png)

Here, we can see the credential that has been issued. We can see metadata such as the identity schema and the issuance data, as well as personal information such as name and address. 

The proof area helps ensure that the data are cryptographically secure and no tampering of the body has occurred (the decrypted `proofValue` is the hash of the body to prove no tampering). Under a non-demo environment, all user data stays locally on the device to minimize the potential for Personally Identifiable Information (PII) breaches. This VC could be used to verify identity in transactions without having to worry about holding onto/worrying about PII.

![image](https://user-images.githubusercontent.com/33649265/202549365-74b80343-a307-445d-bc7a-c7dfe7dfb868.png)

After hitting `Start Scan`, we'd see the QR code pop up. From here, we would be able to associate our generated Verifiable Credentials to our mobile device.

![image](https://user-images.githubusercontent.com/33649265/202549459-6720cabb-9d81-44e7-92dd-000b21df3d0e.png)

### Summary
In this tutorial, we walked through the linking of an external account (in this case, from Acme Bank) and the issuing of a verifiable credential from this external account. We helped Bob link his Acme Bank account with a Knox wallet, allowing him to send and receive CPFs while also proving his identity through a privacy preserving identity solution.
