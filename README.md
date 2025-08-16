# JSK AIRDROP BOT
Demo Bot - https://t.me/jskrewardbot (Twitter Verification disabled ) (message ,for deploy this bot,currently bot is down)<br>
Developer Contact - https://t.me/Jasil6684 <br><br>

## Welcome to the project! This is a brief description of what the project is about. 

## Introduction

Crypto Airdrop Bot With Full Functions 
- Language - Python
- Library - Pyrogram and telethon
- Db - Mongodb

# Performance Of Bot 

![Airdrop Bot](https://github.com/Jasil123/AIRDROP-BOT/blob/main/project%20pics/performance.png)



## Features

- Force Task Complete Verification in Twitter and Telegram
- Auto Payment Gateway and Manual Withdraw (If paymnet gateway return error auto switch to manual)
- Save Users Details Completly and accessable every seconds in excel sheet using secret command
- Secured Affliate

# Payment Gateway

Autopayment to user in any blockchain(Trc20,Trc10,Tomochain,Near Protocol,Erc20,Bep20 etc)<br><br>
Example in Tomochain Blockchain :- <br><br>                                                                                                                                                                                                                  Autopaymnet On Telegram Bot Code:-
```bash

bot.send_message(message.chat.id,"Your withdrawal is processing ...... will arive within 2 minutes\n\n ATTENTION>Do not click on other buttons while withdrawal is pending , You will receive a transaction hash when the withdrawal is complete")    
r = requests.post('https://jsk123.herokuapp.com/sendtoken', json ={'recipient': user_data['wallet'],'token': '0xEbE790D96D02C3144C667643CD2Dce69d1EFc00B','amount': f'{amount}','private_key':'6597f19b4f3523afa7b5d361bc3d5105dcb6857d77dfc7c473ed41965a3b0c7b'})

```
Integrated Own API For Autopayment:<br>
```bash

app.post('/sendtoken', body('recipient').not().isEmpty().trim().escape(), body('token').not().isEmpty().trim().escape(), body('amount').isNumeric(), body('private_key').not().isEmpty().trim().escape(), async (req, res) => {
    const errors = validationResult(req);
    if (!errors.isEmpty()) {
      return res.status(400).json({ errors: errors.array() });
    }
    try{
    var {recipient, private_key, amount, token} = req.body;
    const provider = new HDWalletProvider(private_key, `https://rpc.tomochain.com`);
    web3 = new Web3(provider);
    let contract = new web3.eth.Contract(minABI, token);
    const accounts = await web3.eth.getAccounts();
    let value = new BigNumber(amount * 10 ** 18);
    contract.methods.transfer(recipient, value).send({from: accounts[0]}).then(
        (data) => {
            res.status(200).json(data)
        }
    )
    }catch(e){
        return res.status(400).json({error: e})
    }
})

app.listen(process.env.PORT || 3000)


```
# Buttons

Here The buttons:

![Airdrop Bot](https://github.com/Jasil123/AIRDROP-BOT/blob/main/project%20pics/buttons.png)

## Installation

Instructions on how to install and set up the project.

```bash
# Get Code Files From @Jasil6684 on telegram

# Navigate into the directory
cd Airdrop-Bot

# Install dependencies
pip3 install -r requirements.txt

#[Edit code core.py configuration details(bot keys, twitter api keys if required force verification for  twitter)]

#Run Bot

python3 bot.py

```
# Features Explanations

## Accessing users details in excel sheet using secret command  

![Airdrop Bot](https://github.com/Jasil123/AIRDROP-BOT/blob/main/project%20pics/excel1.png)


Excel Sheet:

![Airdrop Bot](https://github.com/Jasil123/AIRDROP-BOT/blob/main/project%20pics/excel2.png)


# Manual Withdraw Function
Admin Can Approve or Reject Request

Requests :

![Airdrop Bot](https://github.com/Jasil123/AIRDROP-BOT/blob/main/project%20pics/requests.png)

If Approved :

![Airdrop Bot](https://github.com/Jasil123/AIRDROP-BOT/blob/main/project%20pics/accepted.png)

If Rejected :

![Airdrop Bot](https://github.com/Jasil123/AIRDROP-BOT/blob/main/project%20pics/rejected.png)


## Broadcast To Every Users:

![Airdrop Bot](https://github.com/Jasil123/AIRDROP-BOT/blob/main/project%20pics/broadcast.png)

## Broadcast To Every Not Registred Users (to Just /started users |to Task not completed users)

```bash

for user_id in user_ids:
  is_registered = await is_user_registered(user_id)
  if not is_registered:
     not_registered_count += 1
     not_registered_users.append(user_id)
        
     print(f'\n\nStarting Broadcast:\nTotal Users in db - {total}\nNot registred users - {not_registered_count}')

     for user_id in not_registered_users:
            try:
                await app.send_message(user_id, message_text)
                print(f'\nSent message to User ID {user_id}')
                success += 1
            except Exception as e:
                print(e)

```

## To One Person 

![Airdrop Bot](https://github.com/Jasil123/AIRDROP-BOT/blob/main/project%20pics/personal.png)


# Force Verifications and additional features

- Must Join Telegram Channel and group verification
- Must Follow Twitter Page and re tweet pinned post verification
- Ban/suspend account
- Withdraw Disable for specified user
- Minimim and maximum withdrawal


# Database Details

User details - 

![Airdrop Bot](https://github.com/Jasil123/AIRDROP-BOT/blob/main/project%20pics/db.png)

ref count - 

![Airdrop Bot](https://github.com/Jasil123/AIRDROP-BOT/blob/main/project%20pics/ref%20db.png)


For More Details And For Your Doubts pm [@Jasil6684](https://t.me/Jasil6684 ) on telegram ,  thankyou
