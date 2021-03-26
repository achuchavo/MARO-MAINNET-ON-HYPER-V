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


### Create Address

#### Command 1 

```
personal.newAccount("pwd")
```


#### Command Parameters (Body)

| #    | Type                               | Description                                                  |
| ---- | ---------------------------------- | ------------------------------------------------------------ |
| 1    | {[`pwd`](`string`)}                  | address passowrd                               |
