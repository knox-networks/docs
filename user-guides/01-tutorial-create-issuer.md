## Create Issuer Tutorial
In this Knox Networks Sandbox tutorial, we will walk through the process of creating a Delegated File Issuer (DFI) named `Example Bank` with an issuance limit of `$10,000.00`. A default wallet called `Vault` will be created alongside the issuer.

### Step 1: Creating an Issuer
The first step in the process in the sandbox is to create an issuing institution which serves as a delegated file issuer (DFI). A DFI in a standard implementation would likely be a commercial bank (e.g. ABC Bank).

Let's create our very own example DFI, called `Example Bank`.

First, we go to the `Issuers` page. Then, we click `Create Issuer` in the top right.

<img width="1920" alt="image" src="https://user-images.githubusercontent.com/33649265/210653668-8da26db6-328c-4d3b-a277-a3792f09afde.png">

Then, using the pop-up menu, we set the Institution to `Example Bank` and we can set the issuance limit to any value (let's say `$10,000.00`). Now, a DFI will be created with the name `Example Bank`. 

<img width="1920" alt="image" src="https://user-images.githubusercontent.com/33649265/210653950-9dea1e50-2267-4c40-88a4-afb3d4f0c494.png">

This is our created issuer, which is shown with associated fields such as the ID, Public Key, the number of CPFs (files) isssued and Wallets managed, and its status. Ours will likely have the status `Creating...` for a few seconds. 

The `Actions` column also allows us to mock a sample login portal for the DFI, edit the DFI's name, or delete the DFI entirely if we so choose.

### Step 2: Examining the Issuer
We can click on `Example Bank` after it has been initialized (this may take a few seconds as the issuer gets created).

<img width="1920" alt="image" src="https://user-images.githubusercontent.com/33649265/210654545-8a7540c1-2e0c-43ec-9933-471b6a0af681.png">

This is the main view of the DFI. Here, we can see the most recent details of the DFI's actions. Since we just created the DFI, it's pretty sparse in terms of activity. We can see that the DFI was created, an initial issuance limit pf `$10,000.00` set, and a wallet called `Vault` created.

If we click on the `Issuance Limit` tab, we can see the current available issuance limit, which is affected by the amount of files issued and redeemed. In addition, we can aso see the number of CPFs issued. 

<img width="1920" alt="image" src="https://user-images.githubusercontent.com/33649265/210655010-964fd02e-aef9-433a-8f40-f15b23be8ab4.png">

Since we haven't issued anything, it's still at an available limit of `$10,000.00`. This tab will also be where we will managed the issuance and redemption of CPFs in future 

Next, let's click on the `Bank Wallets` tab. Here, we can see all of the wallets that are created and managed under this particular DFI.

<img width="1920" alt="image" src="https://user-images.githubusercontent.com/33649265/210656200-ad393e50-5b74-4a6a-9c66-eccb8400f004.png">

We only have our `Vault` wallet, which serves as a default wallet for DFI's. For each wallet, we can also see the Public Key, the Balance, and the number of CPFs in the wallet. On the `Actions` column, we can rename the wallet (for wallets other than the `Vault`), inspect the wallet contents, and refresh the status of the wallet.

Finally, let's check out the Bank Accounts tab.

<img width="1920" alt="image" src="https://user-images.githubusercontent.com/33649265/210655835-a6c5c613-43cb-4afb-ad48-4f2c181a98df.png">

This page is a little sparse right now, but will eventually be populated with linked bank accounts representing customers' bank accounts that correspond to wallets `Link Account`.

### Summary
In this Knox Networks Sandbox tutorial, we went through the process of creating a Delegated File Issuer (DFI) named `Example Bank` with an issuance limit of `$10,000.00`. A default wallet called `Vault` was created alongside the issuer. Lastly, we explored around the DFI.

Next suggested tutorial: [Create Wallet Tutorial](./02-tutorial-create-wallet.md)
