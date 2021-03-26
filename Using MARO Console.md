# OPEN CONSOLE ( 콘솔 실행 )

#### Go to GTTC Build-Bin Directory 

```
cd ~/go/src/github.com/TTCECO/gttc/build/bin/
```
#### Create IPC (inter process communications) channel with Node

Replace `datadir` with the name of your data directory

```
./gttc attach datadir/gttc.ipc
```

# Console Commands ( 콘솔 명량 )

- [Create Address - 주소 만들기 ](#CreateAddress)
- [Check Address List - 주소 목록 확인 ](#AddressList)
- [Check Address Balance - 주소 자산 확인 ](#CheckBalance)
- [Send Vote - 투표 하기 ](#SendVote)
- [Send MARO - 마로 전송 하기 ](#SendMaro)


### CreateAddress

#### Command 1
 Create address without password prompt.

```
personal.newAccount("pwd")
```


##### Command 1 Parameters (Body)

| #    | Type                               | Description                                                  |
| ---- | ---------------------------------- | ------------------------------------------------------------ |
| 1    | {`pwd`(`string`)}                  | address passowrd                               |



#### Command 2
 Create address with password prompt. You will be prompted to enter password for address.

```
personal.newAccount()
```


### AddressList


#### Command
 Check List of Addresses with the following command

```
eth.accounts
```

### CheckBalance


#### Command
 Check balance of address

```
web3.fromWei(eth.getBalance("addr"), "ether")
```

##### Command Parameters

| #    | Type                               | Description                                                  |
| ---- | ---------------------------------- | ------------------------------------------------------------ |
| 1    | {`addr`(`string`)}                  | maro valid address                               |


### SendVote
Before voting you must first unlock address with password. To unlock address :

#### Command To unlock Address

```
personal.unlockAccount("addr","pwd");
```

##### Command Parameters

| #    | Type                               | Description                                                  |
| ---- | ---------------------------------- | ------------------------------------------------------------ |
| 1    | {`addr`(`string`)}                  | address existing on node                               |
| 1    | {`pwd`(`string`)}                  |  password of address existing on node                               |

#### Command to Cast vote
After unlocking address run this command to vote.

```
eth.sendTransaction({
from:"voter_addr",
to:"node_addr",
value:0,data:web3.toHex("ufo:1:event:vote")
});

```

##### Command Parameters

| #    | Type                               | Description                                                  |
| ---- | ---------------------------------- | ------------------------------------------------------------ |
| 1    | {`voter_addr`(`string`)}                  | voter's address address                               |
| 2    | {`node_addr`(`string`)}                  | address of representative                               |


### SendMaro
Before sending Maro you must first unlock address with password. To unlock address :

#### Command To unlock Address

```
personal.unlockAccount("addr","pwd");
```

##### Command Parameters

| #    | Type                               | Description                                                  |
| ---- | ---------------------------------- | ------------------------------------------------------------ |
| 1    | {`addr`(`string`)}                  | address existing on node                               |
| 1    | {`pwd`(`string`)}                  |  password of address existing on node                               |

#### Command to Send Maro
After unlocking address run this command to send Maro.

```
web3.eth.sendTransaction({
from: "from_addr",
to: "to_addr",
value: web3.toWei(10, "ether")
});


```

##### Command Parameters

| #    | Type                               | Description                                                  |
| ---- | ---------------------------------- | ------------------------------------------------------------ |
| 1    | {`from_addr`(`string`)}                  | address existing on node                               |
| 2    | {`to_addr`(`string`)}                  | receiver's address                               |
| 3    | {`10`(`integer`)}                  | amount of maro to send                               |

