# Install a Zano CLI Wallet (Ubuntu)

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

 Open a terminal in this directory & validate the authenticity of the file by running a checksum (XXX represents your version):

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

Wait for the blockchain to download and sync. This may take quite a few hours, depending on your download speed. And leave the daemon running! We’ll need that to create our new wallet.

![Hx6y3WG.png](https://iili.io/Hx6y3WG.png)

## Step (12)

Once sync is complete, open another terminal in the Zano directory with the `simplewallet`binary—that's our CLI wallet executable. Give command:

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

(14) To open your new wallet, give the following command in the same terminal (again, substituting "name"):

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

## You've successfully installed your new Zano Wallet!
