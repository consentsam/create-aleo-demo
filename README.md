# Aim : To deploy helloworld on local node 

# Reproducing the error

Step 1: Instantiated the starter code using the command `npm create aleo-app@latest`  and then did `npm install` and `npm run dev` to start the project UI

Step 2: Made some changes in the starter code i.e. changed the `ENDPOINT` to https://localhost:3030 and filled the value of `PRIVATE_KEY`

Step 3: Installed the `snarkos`  using the following instructions

### Installation Steps

* **Clone the snarkos repo**

```sh
git clone git@github.com:AleoHQ/snarkOS.git
```

* **Checkout the correct version**

```sh
git checkout 7970ea752ea73ae234f749dd395006e3e231f256
```

I installed this specific version as I didn't face any issues while working on the last project.

* **Install**

```bash
cargo install --path .
```

Step 4: After this, I started  the local development node by running the command

````bash
snarkos start --nodisplay --dev 0 --beacon
````

I sent some credits from the node account to developer account (the account used in the `worker.js`) using both the functions `transfer_private_to_public` and `transfer_private`





Step 5: I tried deploying the code using the deploy `helloworld.aleo` button on the UI but after taking some zk-time, I started getting this issue

```
error decoding response body: Invalid prefix for a bech32m hash: ar
```

Please find the console logs below in the screenshot 

![image-20231125235227378](/Users/consentsam/Library/Application Support/typora-user-images/image-20231125235227378.png)

I have been getting this error whenever I am trying to interact with `execute` function of the `programManager` class. I am not able to understand what this error `Invalid prefix for a bech32m hash: ar` . Please note that when I try to deploy the program locally, I have been able to deploy the program on the local aleo blockchain ( local development node).
