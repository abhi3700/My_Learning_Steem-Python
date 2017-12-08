![learn_steem-python.png](https://res.cloudinary.com/hpiynhbhq/image/upload/v1512602616/wfsroqejia8tvjjsmlrq.png)

Hi Guys!!...

### Today in this tutorial, we will learn about few basic commands for programming the **Steem blockchain** using *Python* language.

Please, refer to [Part 1](https://utopian.io/utopian-io/@abhi3700/learn-steem-python-1-installation-guide) before going any further, if the required tools are not installed.

## Introduction
This is all about practising the basic commands of **"Steem-Python"**. 


## Basic commands
Import the Steem function from steem library. After importing, we can use the function to access further commands (variables) inside that function.
```python
>>> from steem import Steem
>>> s = Steem()
```
#### All keys
Using all keys, we can query.
```python
>>> s.get_account('abhi3700').keys()
```
![all_keys.png](https://res.cloudinary.com/hpiynhbhq/image/upload/v1512602920/nwrzuxs3dadupw36eead.png)

#### Id
This represents the 'user id' of the steem account holder. This is assigned whenever the user joins for 1st time and it remains permanent for the 'username'
```python
>>> s.get_account('abhi3700')['id']
143518
```
#### Name
```python
>>> s.get_account('abhi3700')['name']
'abhi3700'
```
#### Owner, Active, Posting, Memo Keys
Here, all the keys required to access account's different features.

![posting_active_owner_memo_keys.png](https://res.cloudinary.com/hpiynhbhq/image/upload/v1512602979/ejppg7pr5ajiniitijsw.png)

##### Owner
```python
>>> s.get_account('abhi3700')['owner']
{'weight_threshold': 1, 'account_auths': [], 'key_auths': [['**************************************************', 1]]}
```

##### Active 
```python
>>> s.get_account('abhi3700')['active']
{'weight_threshold': 1, 'account_auths': [], 'key_auths': [['**************************************************', 1]]}
```

##### Posting
```python
>>> s.get_account('abhi3700')['posting']
{'weight_threshold': 1, 'account_auths': [['utopian.app', 1]], 'key_auths': [['**************************************************', 1]]}
```
##### Memo
```python
>>> s.get_account('abhi3700')['memo_key']
'**************************************************'
```
#### Public Profile Settings
This shows the meta-data about the user.
![public_profile_settings.png](https://res.cloudinary.com/hpiynhbhq/image/upload/v1512603030/jjpqzslh5z5qsd4cd734.png)

```python
>>> s.get_account('abhi3700')['json_metadata']
'{"profile":{"name":"Abhijit Roy","about":"A Software Developer, Traveller, Crypto Trader, Blockchain enthusiast","location":"Chandigarh, India","profile_image":"https://firebasestorage.googleapis.com/v0/b/bitinfocoinfree.appspot.com/o/14068548_1125160424216001_2627046384272844500_o.jpg?alt=media&token=8bb1b1f9-36f5-4b9a-8220-4134f01f8542","website":"https://play.google.com/store/apps/details?id=in.topux.bitinfocoin","cover_image":"https://www.ethereum.org/images/assets/1900/Ethereum-homestead-background-4.jpg"}}'
```

#### Proxy
It is null in this case as no proxy server used.
```
>>> s.get_account('abhi3700')['proxy']
''
```
#### Last owner update
It comes from the UNIX command i.e. January 1st 1970. Also birthdays are written in timestamps (time from this date till date).
```
>>> s.get_account('abhi3700')['last_owner_update']
'1970-01-01T00:00:00'
```

#### Last account update
It mainly is when the account settings (public profile) was last updated.
```python
>>> s.get_account('abhi3700')['last_account_update']
'2017-11-26T17:57:18'
```

#### Account creation time
The date, time when the account was created.
```python
>>> s.get_account('abhi3700')['created']
'2017-04-02T08:00:57'
```

#### Recovery account
If your account gets hacked, it can be recovered before any data is manipulated.
```python
>>> s.get_account('abhi3700')['recovery_account']
'steem'
>>> s.get_account('abhi3700')['last_account_recovery']
'1970-01-01T00:00:00'
```
Click [here](https://steemit.com/steem/@someguy123/how-the-steem-account-recovery-works-and-why-your-trustee-can-t-steal-your-account) for details.

#### Post counts
The no. of posts posted by the user.
```python
>>> s.get_account('abhi3700')['post_count']
198
```
#### Can vote
Whether a person can vote or not.
```python
>>> s.get_account('abhi3700')['can_vote']
True
```

#### Voting Power
This depends upon the 'steem power' a user holds. Here, it calculates out of 10,000. 
```python
>>> s.get_account('abhi3700')['voting_power']
9800
```
So, I hold 98 % voting power currently.

#### Last vote time
Last time, I voted.
```python
>>> s.get_account('abhi3700')['last_vote_time']
'2017-12-01T18:30:27'
```
#### Balance
All balances in steem, SBD.
The user account looks like this...
![wallet.png](https://res.cloudinary.com/hpiynhbhq/image/upload/v1512603104/gmdyplgadjatovjxodpg.png)


```python
>>> s.get_account('abhi3700')['balance']
'0.000 STEEM'

>>> s.get_account('abhi3700')['sbd_balance']
'0.603 SBD'

>>> s.get_account('abhi3700')['savings_sbd_balance']
'0.000 SBD'
```

#### Vesting
Basically, it defines the steem power.
Click [here](https://steemit.com/steemitguide/@steemitguide/steemitguide-what-exactly-is-vested-steem-why-is-it-important-for-you-know-how-smart-contracts-allocates-power-within-the) for details.
```python
>>> s.get_account('abhi3700')['vesting_shares']
'1038936.179712 VESTS'
>>> s.get_account('abhi3700')['delegated_vesting_shares']
'0.000000 VESTS'
>>> s.get_account('abhi3700')['received_vesting_shares']
'12358.959056 VESTS'
>>> s.get_account('abhi3700')['vesting_withdraw_rate']
'0.000000 VESTS'
>>> s.get_account('abhi3700')['next_vesting_withdrawal']
'1969-12-31T23:59:59'
```
Basically, I have never withdrawn my *steem-power*. The time itself indicates i.e. before Jan 1, 1970 ())
 
#### Bandwidth
It is the power to post, upvote, comment. The more Steem-power one has, the more steem-blockchain's bandwidth is owned by the user.
It is like holding a percent of the network.

```python
# Content post bandwidth
>>> s.get_account('abhi3700')['average_bandwidth']
'46792401000'

>>> s.get_account('abhi3700')['lifetime_bandwidth']
'677875000000'

>>> s.get_account('abhi3700')['last_bandwidth_update']
'2017-12-06T20:42:42'

**************************************************************************************************
# Market bandwidth
>>> s.get_account('abhi3700')['average_market_bandwidth']
1660341514

>>> s.get_account('abhi3700')['lifetime_market_bandwidth']
'24130000000'

>>> s.get_account('abhi3700')['last_market_bandwidth_update']
'2017-12-06T20:42:42'
```

#### Last post date
The date, time for last post.
```python
>>> s.get_account('abhi3700')['last_post']
'2017-12-03T13:20:21'
```

#### Witness votes
The witnesses I have voted for.
```python
>>> s.get_account('abhi3700')['witness_votes']
['steemed', 'utopian-io']
```
Basically, all the above discussed user properties can be viewed here-(https://steemd.com/@username)
![steemd_user.png](https://res.cloudinary.com/hpiynhbhq/image/upload/v1512664879/wx2a8i2bsws3ejziszen.png)


That's all.

### Stay tuned for more such tutorials......

## View in [Github](https://github.com/abhi3700/My_Learning-Steem/blob/master/Learn_steem-python/Basic_commands.md)


<br /><hr/><em>Posted on <a href="https://utopian.io/utopian-io/@abhi3700/learn-steem-python-2-basic-commands">Utopian.io -  Rewarding Open Source Contributors</a></em><hr/>

### View in [Steemit](https://steemit.com/utopian-io/@abhi3700/learn-steem-python-2-basic-commands)

