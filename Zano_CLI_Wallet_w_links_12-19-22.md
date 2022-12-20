# Setting-up a Zano CLI Wallet

## Step (1)

Go to the official site: Zano.org

![Hx6rumN.png](https://iili.io/Hx6rumN.png)

## Step (2)

Go to Downloads, which takes you to:
https://github.com/hyle-team/zano/releases

![Hx6bYgI.png](https://iili.io/Hx6bYgI.png)

## Step (3)

Download Linux (Ubuntu 16.04+) CLI Wallet

![Hx6b6rB.png](https://iili.io/Hx6b6rB.png)

## Step (4)

Right click the file and select Properties

![Hx6m9rN.png](https://iili.io/Hx6m9rN.png)

## Step (5)

Copy the file name

![Hx6mqQf.png](https://iili.io/Hx6mqQf.png)

## Step (6)

 Open a terminal in this directory & validate the authenticity of the file by running a checksum (<XXX> represents your version):

```
sha256sum zano-linux-x64-v<XXX>.tar.bz2
```

(results should match release notes from Download page)

![Hx6m8vt.png](https://iili.io/Hx6m8vt.png)

![Hx6pMKl.png](https://iili.io/Hx6pMKl.png)

## Step (7)

If checksums match, decompress & extract the .tar.bz2 file:

```
tar -xvjf zano-linux-x64-release-devtools-v1.5.0.143[336fac2].tar.bz2
```

![Hx6p6R1.png](https://iili.io/Hx6p6R1.png)

## Steps (8-10)

(8) Delete your original .tar.bz2 file

(9) Move the Zano folder to a location of your choice

(10) Within the Zano directory, open a terminal and run the daemon to start the node and download the blockchain:

```
./zanod
```

![Hx6pLxa.png](https://iili.io/Hx6pLxa.png)

![Hx6pblp.png](https://iili.io/Hx6pblp.png)

## Step (11)

Wait for the blockchain to download and sync. This may take quite a few hours, depending on your download speed. And leave the daemon running! We’ll need that to use our new wallet.

![Hx6y3WG.png](https://iili.io/Hx6y3WG.png)

## Step (12)

Once sync is complete, open another terminal in the Zano directory with "simplewallet"—that's our CLI wallet executable. Give command:

```
./simplewallet --generate-new-wallet=name.wallet
```

Replace “name” with your new wallet’s name, e.g.,:

```
./simplewallet --generate-new-wallet=zanocli.wallet
```

![Hx6yzbe.png](https://iili.io/Hx6yzbe.png)

## Step (13)

When asked, enter a password for your wallet. You should use a password generator, found in password managers such as KeePass.

![Hx6y70Q.png](https://iili.io/Hx6y70Q.png)

## Steps (14-15)

(14) To open your new wallet, give the following command in the same terminal:

```
./simplewallet --wallet-file name.wallet
```

(15) Enter your password, when prompted. Notice that the wallet displays your receive address after “Opened wallet.” You will use this to fund your new wallet.

![Hx6y1mF.png](https://iili.io/Hx6y1mF.png)

## Steps (16-17)

(16) Now we must get our wallet’s seed phrase, as well as set an additional password for the seed itself. Give the command:

```
show_seed
```

(17) Again, when prompted provide a password for the seed phrase you’re about to get. Confirm the password, and be sure to save both it and your seed phrase!!

![HxP8B7p.png](https://iili.io/HxP8B7p.png)

## Step (18)

You are now ready to get yourself some ZAN! If you didn’t copy-down your receive address, simply give the command:

```
address
```

Two exchanges to consider:

- Trade Ogre: https://tradeogre.com/account/signin

- Stex: https://www.stex.com/

Zanod (your node) can be left running, if you’ll be transferring some ZAN to your wallet soon. If not, close your wallet by giving the command:

```
exit
```

## Step (19)

After you’ve funded your new Zano CLI wallet, open it again and check for your funds (steps 14-15 above). If they’re not visible, wait a bit and then give the command:

```
refresh
```

Now let’s send some ZAN to a friend!

The command for sending ZAN consists of four important bits of information:

1. the command itself

2. the number of txs with which to mix yours (between 10-50/maximum available)

3. the receiving address

4. the amount of ZAN you wish to send

For example:

         (1)           (2)                  (3)                  (4)

```
transfer mix# receiveaddress amount
```

![Hx6yLk7.png](https://iili.io/Hx6yLk7.png)

## Other Useful Flags in Terminal

For wallet password

```
--password arg
```

Use daemon instance at <host>:<port> for changing default host and port

```
--daemon-address arg
```

Prevents connecting to Zanod (daemon) for working offline (e.g., for cold-signing)

```
--offline-mode
```

Provides the destination for the log file

```
--log-file arg
```

Sets the level of detail for the log

```
--log-level arg
```

?

```
--set-log arg
```

?

```
--scan-for-wallet arg
```

?

```
--addr-to-compare arg
```

And finally, to run any of the following commands outside of the wallet:

```
--command arg
```

## Other Useful in-Wallet Commands

- `address` = Shows current wallet public address

- `balance` = Shows current wallet balance

- `exit` = Closes the wallet

- `export_history [filename needed?]` = Exports tx history into a CSV file

- `export_recent_transfers` = Writes recent transfer txs in json to    wallet_recent_transfers.txt (in Zano directory)

- `help` = Shows a list of flags and commands

- `list_recent_transfers` = Shows recent maximum 1000 sent amounts, offset default = 0, count default = 100

- `refresh` = Resynchronize transactions and balance

- `resync` = Resets all transfers and re-synchronize the wallet

- `save` = Saves wallet synchronized data

- `show_seed` = Displays secret 24 word phrase used to recover wallet

- `sweep_below <mixin_count> <address><amount_lower_limit> [payment_id]`: Tries to transfer all coins with amount below the given limit to the given address
