## Issuance-Payment-Redemption Tutorial
In this Knox Networks Sandbox tutorial, we will walk through the process of creating a Delegated File Issuer (DFI) named `Example Bank` with an issuance limit of `$10,000.00`. A default wallet called `Vault` will be created alongside the issuer.

From there, we will then issued `$100.00` worth of Cryptographic Promissory Files (CPFs) to the `Vault` wallet. This will decrease our `Example Bank`'s available issuance by `$100.00` down to `$9,900.00`. We will then explore the `Vault` wallet's CPFs.

Next, we'll show how to create another bank called `Sample Bank` with an issuance limit of `$5,000.00`. We'll then create a wallet within `Sample Bank` creatively named `Sample Wallet`. This wallet had no CPFs.

After returning to our `Example Bank`, we'll initiate a payment of `$15.00` worth of CPFs from the `Vault` to the `Sample Bank`'s `Sample Wallet`. This will decrease the balance on the `Example Bank`'s wallet and will increase the balance on the `Sample Bank`'s wallet. We will then verify that this transfer has taken place at the individual file level.

### Step 1: Setting up DFIs and Wallets
For this tutorial, we will need to create DFIs:
- `Example Bank` with an issuance limit of `$10,000.00 USD`
- `Sample Bank` with an issuance limit of `$5,000.00 USD` and a created wallet called `Alice's Wallet`

The tutorial will still work with different names and issuance limit values, but this is suggested for the simplicity of the tutorial. Please refer to the tutorials on [Creating an Issuer](./01-tutorial-create-issuer.md) and [Creating a Wallet](./02-tutorial-create-wallet.md) for the tutorials of creating a DFI and creating a wallet respectively.

### Step 2: Issuing a CPF
Let's click on `Example Bank` and go to the `Issuance Limit` tab. Here we will be able to issue and redeem Cryptographic Promissory Files (CPFs). CPFs serve as the basic unit of accounting in the Knox Networks system, and represent a fixed-denomination currency or general asset unit.

![image](https://user-images.githubusercontent.com/33649265/212192434-f00c88ca-82e5-4bfd-b5f4-cf4e4b75e214.png)

Currently, we have issued and redeemed $0.00.

![image](https://user-images.githubusercontent.com/33649265/212192498-1a4a2580-a97f-466e-8509-1e1737c5de95.png)

We can decide to issue a CPF to our default `Vault` wallet using the `Issue CPFs` button in the top right corner. Let's issue `$100.00`. Before we click `Issue`, we can see that our current available issuance is `$10,000.00` above.

![image](https://user-images.githubusercontent.com/33649265/212192634-57f14e88-9936-4b7d-8994-37dc289467e4.png)

Now, `$100.00` worth of CPFs have been issued, and our issuance limit has decreased to `$9,900.00`. 

![image](https://user-images.githubusercontent.com/33649265/212192692-85a042be-aa1f-4669-8cec-71dea8904d81.png)

There were 40 separate CPF files issued (exact numbers might vary based on denomination of bills), which we can verify their value by clicking on the `Bank Wallets` tab. We still only have our default `Vault` wallet, so only one shows up. We can see the name, public key, CPF balance, and the number of CPFs issued to the `Vault` wallet in the row above. Whereas before our `Vault` Balance was `$0.00` before, it is now `$100.00`.

We can click on the `Details` button to get a better understanding of the `Vault` wallet's contents. The image below shows the contents of the `Vault` wallet, which is comprised of 13 different CPFs, ranging in value from `$0.01` to `$50.00`, all of which add up to the `$100.00` issued.

![image](https://user-images.githubusercontent.com/33649265/212192774-273f5230-c485-4f3f-a8ed-ec304c67441b.png)

Currency denomination distributions are currently fixed within the Knox Networks Sandbox, but there are plans to add the feature to specify CPF denomination schemas.

Now that we've peaked inside the `Vault` wallet, we can even peak into the individual CPFs themselves. Let's click on the `Folder` icon for the CPF worth `$50.00`.

![image](https://user-images.githubusercontent.com/33649265/212192849-34353b48-2c72-423d-9c4f-aefe3a59a56d.png)

Here we can see all the relevant data for a CPF, including its currency, amount of value, its date of issuance, and all of the relevant signatures by the Monetary Authority and the DFI (in our case, `Example Bank`).

We can also see the Secure Signature, which provides the cryptographic security for proving transfers of CPFs between parties. As each transaction occurs, the block chain length will grow within each CPF file to reflect this transfer. Currently, our CPF has a block depth of 3, which came from the creation and transfer of the CPF to our wallet.

Congrats on the issuance of some CPFs! Now let's transfer some money to `Alice's Wallet` in `Sample Bank`.

### Step 3: Initiating a Payment
Since we are in a generous mood, we decide to pay `$15.00` worth of CPFs to `Alice's Wallet` in `Sample Bank`. We can do this by clicking on the `Make Payment` button in the top right of the screen inside the wallet.

A menu will come up, asking us to fill out the following fields:
- The sending `Issuer` and the sending `Wallet` belonging to the `Issuer` (will already be filled out with our information)
- The receiving `Issuer` and the receiving `Wallet` belonging to the `Issuer` we want to transfer to
- The `Amount` to be transferred

![image](https://user-images.githubusercontent.com/33649265/212193031-055ae020-51dd-4eb4-a1f1-5f25d6dcb2f7.png)

We saw the fields with a Sender of `Example Bank` and wallet of `Vault`, which has `$100.00` were already filled out. We fill out the fields of Recipient of `Sample Bank` and wallet of `Alice's Wallet`. We decided the amount to transfer was `$15.00` and with a message of `Ice Cream`, so we fill that in as well, looking like the figure above before we hit `Send`.

![image](https://user-images.githubusercontent.com/33649265/212193124-03ceefe3-bc63-44fc-929e-fe4a06fe5085.png)

We can see the transaction reference number, and click `Dismiss`. Now after the `Send`, we can see that our `Example Bank`'s `Vault` wallet has decreased by `$15.00` in balance, and we have only have $85.00 worth of CPFs remaining. You may need to refresh the wallet to see the new balance.

![image](https://user-images.githubusercontent.com/33649265/212193338-0db17110-4ff9-4188-93ca-85530333992e.png)

After clicking over to the `Transactions` tab for the wallet, we can see that a payment worth `$15.00` took place, originating from this wallet. In this case, there were 2 files sent over, a `$5.00` file and a `$10.00` file

![image](https://user-images.githubusercontent.com/33649265/212193494-f57037dd-6022-43f4-aef5-0bdc3e28721d.png)

We can also check from `Alice's Wallet` in `Sample Bank` side as well, where it now shows an inbound transfer of CPFs occurred on the `Transactions` tab.

![image](https://user-images.githubusercontent.com/33649265/212193687-77a10433-af39-49bf-b5de-158c4f52f764.png)

Clicking over to the `CPFs` tab, we see that the balance of our `Receiving Wallet` has increased by `$15.00`, and now has 2 CPFs in it, the `$5.00` and `$10.00` transferred. 

![image](https://user-images.githubusercontent.com/33649265/212193814-53700238-89c4-4077-aa05-e8e94b283b26.png)

In addition, we can verify the individual CPFs took note of this transfer by clicking on the details of a given CPF.

![image](https://user-images.githubusercontent.com/33649265/212193940-77f82a0b-a8de-4fda-be98-ffc82cb6b744.png)

Previously, these CPFs all had a block depth of 3 (like the remaining `$50.00` in the `Example Bank`'s `Vault`), but the transferred ones now have a block depth of 4 (with the most recent transaction adding to this block depth).

### Step 5: Redeeming a CPF
Now that `Sample Bank` has a CPF, it can redeem the CPF in the `Issuance Limit` tab. Click on the `Redeem CPFs` button in the top right.

![image](https://user-images.githubusercontent.com/33649265/212194037-6ec92d17-d69a-476e-ae9b-56d43a03587f.png)

Let's have `Receiving Bank` redeem `$5.00` of the `$15.00` sent by selecting `Alice's Wallet` and `$5.00` for the fields.

![image](https://user-images.githubusercontent.com/33649265/212194085-e8c92d55-b858-4950-9dd7-c608f1a294ad.png)

The CPF has now been redeemed! We can see that we now have `$5.00` worth redeemed of CPFs, and our available limit has increased by `$5.00` to `$5,005.00`.

![image](https://user-images.githubusercontent.com/33649265/212194138-bfb486e7-4ca5-4f79-9e17-7bf2216f49e3.png)

### Summary
We issued `$100.00` worth of Cryptographic Promissory Files (CPFs) to the `Vault` wallet of `Example Bank`. This decreased our `Example Bank`'s available issuance by `$100.00` down to `$9,900.00`. We explored the `Vault` wallet's CPFs.

We then initiated a payment of `$15.00` worth of CPFs from the `Vault` to the `Sample Bank`'s `Alice's Wallet`. This decreased the balance on the `Example Bank`'s wallet and increased the balance on the `Sample Bank`'s wallet. We then verified that this transfer had taken place at the CPF level.

Finally, we decided to redeem `$5.00` worth of CPFs for the Sample Bank, which increased our available limit by `$5,000.00` to `$5,005.00`

Next suggested tutorial: [Check and Set DFI Issuance Limits](04-tutorial-get-set-issuance-limits.md)
