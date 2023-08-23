# TRON Coin on Internet Computer Blockchain

![TRON Token Logo](/images/logo.webp) <!-- Replace with your logo -->

Welcome to the TRON Token project on the Internet Computer Blockchain! This repository contains the code for a decentralized TRON token implemented using React for the frontend and Motoko for the backend. The project provides various functionalities, including ICP authentication, faucet, balance check, and token transfers. This document will guide you through the project, its functionalities, and how to set it up for development or deployment.

## Overview

The TRON Token project is an innovative and decentralized platform that leverages the power of React for the frontend and Motoko for the backend. This dynamic combination allows for the creation of a cutting-edge token ecosystem that introduces a range of functionalities designed to enhance user experience and interaction.

At its core, the TRON Token project introduces a novel approach to authentication through the utilization of the ICP blockchain. Users are seamlessly authenticated via this robust blockchain system, ensuring a high level of security and trust. What sets this project apart is its user-centric design, allowing users to choose their own unique user IDs. This personalized approach to access not only enhances security but also adds a layer of familiarity to the platform.

A standout feature of the TRON Token project is the innovative faucet system. New users who complete the ICP blockchain authentication process are rewarded with an initial allocation of 10,000 tokens. This generous allocation empowers users to immediately engage with the TRON Token ecosystem, making their entry into the platform both exciting and rewarding.

For users already within the ecosystem, the platform offers a balance check functionality. Authenticated users can easily view their TRON token balance through an intuitive and user-friendly interface provided by the frontend. This transparency ensures that users have real-time insights into their holdings, enhancing their overall engagement and experience.

One of the most compelling aspects of the TRON Token project is its robust transfer functionality. Authenticated users have the ability to seamlessly transfer a specified number of tokens to other users who are also authenticated via the ICP blockchain and registered on the platform. This peer-to-peer transfer capability opens up a world of possibilities for interactions and transactions within the TRON Token ecosystem.

In summary, the TRON Token project is a revolutionary undertaking that merges the power of React and Motoko to create a decentralized token ecosystem. Its feature-rich nature encompasses ICP authentication, a rewarding faucet system, balance checks, and frictionless token transfers. This comprehensive suite of functionalities ensures that users can securely and seamlessly engage with the TRON Token platform, unlocking a new realm of possibilities in the world of decentralized tokens.

## Functionalities

The TRON Token project comes with the following functionalities:

1. **ICP Authentication**: Users get authenticated via the ICP blockchain and can choose their own user ID to access the platform securely.

2. **Faucet**: New users receive 10,000 tokens for getting authenticated via the ICP blockchain. This allows users to start interacting with the TRON Token ecosystem immediately.

3. **Balance Check Functionality**: Authenticated users can check their TRON token balance by accessing the interface provided by the frontend.

4. **Transfer Functionality**: Authenticated users can transfer a certain number of tokens to other authenticated users of the ICP blockchain who are registered on the website.

## Setup Instructions

Follow the steps below to set up the TRON Token functionalities:

### Check Your Balance

1. To check your TRON token balance, you need your principal ID, which is your identity on the ICP blockchain.

```shell
dfx identity get-principal
```

2. Save it somewhere.

3. Format and store it in a command line variable:

```shell
OWNER_PUBLIC_KEY="principal \"$( \dfx identity get-principal )\""
```

4. Check that step 3 worked by printing it out:

```shell
echo $OWNER_PUBLIC_KEY
```

5. Check the owner's balance:

```shell
dfx canister call token balanceOf "( $OWNER_PUBLIC_KEY )"
```

## Charge the Canister with TRON Tokens

To ensure the token functionality works, you need to charge the TRON Token canister with a balance.

1. Check canister ID:

```shell
dfx canister id token
```

2. Save the canister ID into a command line variable:

```shell
CANISTER_PUBLIC_KEY="principal \"$( \dfx canister id token )\""
```

3. Check that the canister ID has been successfully saved:

```shell
echo $CANISTER_PUBLIC_KEY
```

4. Transfer half a billion tokens to the canister Principal ID:

```shell
dfx canister call token transfer "($CANISTER_PUBLIC_KEY, 500_000_000)"
```

## Deploy the Project to the Live IC Network

To deploy the TRON Token project to the live IC network, follow these steps:
``

1. Create and deploy canisters:

```shell
dfx deploy --network ic
```

2. Check the live canister ID:

```shell
dfx canister --network ic id token
```

3. Save the live canister ID to a command line variable:

```shell
LIVE_CANISTER_KEY="principal \"$( \dfx canister --network ic id token )\""
```

4. Check that it worked:

```shell
echo $LIVE_CANISTER_KEY
```

5. Transfer some tokens to the live canister:

```shell
dfx canister --network ic call token transfer "($LIVE_CANISTER_KEY, 50_000_000)"
```

6. Get the live canister front-end ID:

```shell
dfx canister --network ic id token_assets
```

7. Copy the ID from step 6 and add .raw.ic0.app to the end to form a URL.

```
For example: zdv65-7qaaa-aaaai-qibdq-cai.raw.ic0.app
```

# Working Images of the Project

### Internet Computer Authentication Page 
![Internet Computer Authentication Page](https://github.com/RachitJain959/TRON-token/blob/master/images/ICP-Authentication.png)

### Windows Authentication Page 
![Windows Authentication Page](https://github.com/RachitJain959/TRON-token/blob/master/images/Windows-Authentication.png)
### Internet Computer Page 

![Internet Computer Page](https://github.com/RachitJain959/TRON-token/blob/master/images/ICP-loader.png)
### Website Home Page 

![Website Home](https://github.com/RachitJain959/TRON-token/blob/master/images/website.png)
