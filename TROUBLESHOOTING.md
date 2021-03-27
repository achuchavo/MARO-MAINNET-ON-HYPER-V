
# MARO on HYPER-V LINUX TROUBLESHOOT

List of possible difficulties and solutions!


#### Lee ChangHun Server Template

CH L (Node) - t0f45751b8cd68e9d52f1f46312eae19a6eff4b900
t0b941587170843011e569ca498031b63c00cf7631
----
apt-get update
apt-get upgrade

----
https://github.com/TTCECO/gttc/wiki/Building-GTTC

---
https://github.com/TTCECO/gttc/wiki/HOWTO-BUILD-SUPERNODE

after make gttc create account then go build ethkey
----
cd ~/go/src/github.com/TTCECO/gttc/build/bin/
mkdir chl
./gttc --datadir  chl/ account new
---
ADDRESS : 
GET PRIVATE KEY AND PUBLIC KEY
cd ~/go/src/github.com/TTCECO/gttc/build/bin//chl/keystore
ls
UTC--2021-03-25T08-44-25.486178567Z--b941587170843011e569ca498031b63c00cf7631

cd ~/go/src/github.com/TTCECO/gttc/cmd/ethkey/

./ethkey inspect ~/go/src/github.com/TTCECO/gttc/build/bin/chl/keystore/UTC--2021-03-25T08-44-25.486178567Z--b941587170843011e569ca498031b63c00cf7631 --private

PUBLIC : 04e5c3579c9418cbc5caf85c63ad8cb86770dd6cee15dc837588a1a62ec39681f3c238f4e3407ac643caa8615a14da9d67d18e1571b1218c3f90493dbb3cf07bba
PRIVATE : 5c1bdd765c3c42864b973a16d5626dc8118cb45ec6315bb1c8ff683465d0c079

---
cd ~/go/src/github.com/TTCECO/gttc/build/bin/
echo "fedora" > pass.txt
./gttc --datadir chl/ --port 30303 -unlock 't0b941587170843011e569ca498031b63c00cf7631' --password pass.txt --mine
nohup  ./gttc --datadir chl/ --port 30303 -unlock 'addr' --password pass.txt --mine > output.chl &

/sbin/iptables -I OUTPUT -p tcp –sport $uports –dport 30303 -j ACCEPT
/sbin/iptables -I INPUT -p tcp –sport 30303 –dport $uports -j ACCEPT

---
cd ~/go/src/github.com/TTCECO/gttc/build/bin/
 ./gttc attach chl/gttc.ipc
---
https://github.com/TTCECO/gttc/wiki/Public-Enode-address

---
tail -20  output.chl
ps -ef | grep gttc

-----
cd ~/go/src/github.com/TTCECO/gttc/build/bin/
 sudo ./gttc attach chl/gttc.ipc

ADD NEW ADDRESS
---
personal.importRawKey("pk","pwd");
personal.newAccount("test")
personal.newAccount()

SEND TRANSACTION 
--
personal.unlockAccount("addr","pwd");
personal.unlockAccount("addr","pwd",5);
web3.fromWei(eth.getBalance("t0b941587170843011e569ca498031b63c00cf7631"), "ether")

eth.sendTransaction({
from:"addr",
to:"rep",
value:0,data:web3.toHex("ufo:1:event:vote")
});

web3.eth.sendTransaction({
from: "addr",
to: "adrr",
value: web3.toWei(10, "ether")
});

---
cd ~/go/src/github.com/TTCECO/gttc/cmd/ethkey/chl
mkdir pkbackup
cd keystore
sudo cp * ../pkbackup
sudo rm -v "UTC--2021-03"

----
admin.addPeer("enode://31d1749b76e3fd4aa3e122f5053abbf8909e5767815f2a7b3fb2c9ea72d6e52b37039ef69695898f93278db9385d18615e6191b26ed26e2ac1872a98663e8ec4@34.84.79.178:30311")
admin.addPeer("enode://d58ca89d026515c528a3fad0f87e13022b55c064c19ad6d80fce79d7e008113d7e5be0b0f6521caedb23e709f0bdc731d9287fc3d6accaebc33ec39340a53257@34.84.79.178:30312")

admin.addPeer("enode://c5f2101ddffb6d862faad67f8051b85998c06cb440680c467ba4e7fd99d6a17d7e205425dce9ef3026ec27023e04925f0378dcf1e00f2900492791242af2a4ab@3.208.71.100:30303")

admin.addPeer("enode://5670d5bce9567ff0c5546ec6d284604bba1cce42a5b8a996e67d60ee1167e50ad216fb4305816ca7c0c867e082598b43b531b62416073aaf862b1f2123821ebd@35.189.152.23:30310")
admin.addPeer("enode://94499e31da30473576643d1c27ec163f158fbef47aa1f80a05f400ab2f2ac22e6f8fac224b8a903a095ba7f3ac7c528f80d06157ef9f2f2e0aa6d0f504d9f9ca@104.198.82.39:30310")
admin.addPeer("enode://547623b9a929b725a30666d072625ed37058c8b7418574632483fbe74cd3532614aa9f8518553a72d190164c44550da2f4b38f31959d8307126e0d8d627b3cd9@34.85.14.244:30310")

admin.addPeer("enode://2a31e7fdb7b8524360532ddc2b406a38113a4e250d5d5bc506fe6c6d57211d33f324e905b0c8eb9c4cbe35b64e22a585bad45c21b5c3d4c1730b788a6f562904@47.105.126.150:30310")
admin.addPeer("enode://368558c489e4b3f66545f846c8c1b2f626bf945a2d42d374d3c187ce09672f8a99684b5adf824ae28c98eb4a526e1ab9ab5a423829815163990d8d370db8982d@47.105.126.150:30311")
admin.addPeer("enode://cfd2f6d47b7bd6fd686c40dc23c9e2774b0dde754a7bab9a0955fc7a3c3bb7d295639b8ef9ae899582415f3ca6a6b6470af0cdbc477e949865e6e1d1e13783c8@47.105.126.150:30312")

admin.addPeer("enode://94268dca1403ceaaad778913953134d572e59810e4aa2c208938fceae8315d51963d51ca1ec903332179e34921cfd51e4dca6508e85756f624e1c28fc8d5f613@35.195.13.217:30313")
admin.addPeer("enode://76b8a019103a32df21304b11563afee6d08fc125fd7b6e7fa8a2759f7b27807766e1d1389f40118a4e8fc287123b6210b19965363c3e2134c26ae151e11bbe8c@35.195.13.217:30314")

admin.addPeer("enode://00c9ac313b53b22f0639d7609ae343bb01b3a594503f8e9887f46130771c78536969b52968560828881c7dad3adb0acead5e5c95644cc15da2976acd7bd72e13@35.231.35.71:30311")
admin.addPeer("enode://43bec764570c24620cd32756241fc4fe6afc432b0cdcce3888583042cc894e0715a15d3b4421b3bab79b185cbb699dc1bed7eab64266382da7099038630662e5@35.231.35.71:30312")
admin.addPeer("enode://eb227d3ade864eade034d69a02d46c37a215c25616f5c79a21a131e46c1e47deb1868151d7b4af6e0fa076a43fac6ae9ba0a0937dbf0214e8814945985f0a258@35.231.35.71:30313")

admin.addPeer("enode://1ff1e9e6707b87d674ac2300c949cfa249906e46eaceb6d58d43dd44f8d8f62d75e097b78f5040f22ddd7473831cb70842841fba2a52cea26701b47f69ab7e62@35.228.112.210:30311")
admin.addPeer("enode://26aa260b2dd45392816bf29f3f01532f282f4bd98e1d42fcb1a20d7bc45c48809f87c4f94719207631083e985d88cfbecb5bb98a002f59514c18e64aad282d30@35.228.112.210:30312")
admin.addPeer("enode://6f983c38ab7b34360760668bb032e5c0968ad967c631c5decaee087adb88497a9b5c76bbd61b4dbeb218faa6ffe1a0f77288e5fb8a7a032e975f7cf42d6fce47@35.230.128.59:30311")
admin.addPeer("enode://fcb0c9b8c375b973011a27f1d2ddc2df34d56080c1d8b2daa961542912e90224d650ce38a2c6f61f24189018f960f80123e402d6d40a70fa2dff42b90b995ce7@35.230.128.59:30312")
admin.addPeer("enode://5652b8cb4c5ae8f9ef004fc7eebc3a409e2a3421ad6bda95090a46c3cbcae82324981d0bac8836558f09741d459850452300145085675c87a1e84753b5730474@35.243.91.57:30311")
admin.addPeer("enode://e0fe630505fa7ec17178bdf816018e1b6c566804d1eaad5a6ba50d29522f796b82518b0b168da3a5b222b2ec6be9f651c6a4e321247144d15d0288bff4864a32@35.243.118.24:30311")
admin.addPeer("enode://de741dcc7474645790c1890eea02c1e6dc14689dcbaa8e12a0cba6a0dc96d9c84dfcd3b7a001e9eae1dfc1ce3efabcc0a6b70bfe2d0491347367d2524f684000@35.190.239.155:30303")
admin.addPeer("enode://80b6e1b753e4b662db6c4fc53bd58c51cd3ed549c062e3743c5bd6ce9f7042b0b3152a093fc535c19960a7625aaad4f6e77d88220ad4aa676f2cefb4dce03956@35.190.239.155:30312")
admin.addPeer("enode://0843721927af5ac58a2bdaf3b8c0783c452762788fc578261401c54caac3b6c751804a91d183db806bd9a45012b0000d703c9024ec6920f7c4ba037be44f8965@35.190.239.155:30314")
admin.addPeer("enode://67e7ee1779f6165a8c93df0b7aa281448031660f3301fb59a6a0acfbffa0ea44a4bba3d02008c6c76b8b1218fe8f941d70e431b243d91c3e5e38a6b5bdae6158@34.74.182.148:30303")
admin.addPeer("enode://4c3e8d3ba2c174df4f93eaaac3073d62d5ef49f3d993721c72325add9785ac7290e8c84551a5418884021e993d00df20fc7c05ce486faf189af40768aaaa34dd@34.74.182.148:30312")
admin.addPeer("enode://2bc058f435aeb40f289bb8bb0033c25546abbba90a6691a0337e4adec31a22ab87972800424aafecca4cb37481419e13c40dc228a13ff7821d1585aeed9fc779@34.77.28.121:30303")
admin.addPeer("enode://ea18e7b08e9b7b6951f08bae369616968264b7338a3f3194c2c5e38c0d2ef2fc7ea4d0dbd717c14008204f2e18b5212525013f4c409a00c5663c1ca4266d3aa1@34.77.28.121:30312")

admin.addPeer("enode://77e1dfa02ae62d84460a0abdca6b3bd0bbd2389456e6ea77dccc3a1c1c246b134d8e808351f738eaea152cae5e40a2ba05b4b0e62eac2a58796986105866188f@35.241.177.70:30311")
admin.addPeer("enode://76b30846780ae7d2f296877a67f1bb39da646c92a96d9e13f0a2de4f5305d8dcbe2b07d16b2863b9e280c1cee496332bacaae2ed3949e9734f75dcb9f59f684f@35.241.177.70:30312")
admin.addPeer("enode://81ab2cb3fd0b5298a2d63b4cdb866af824720bce46d69ffe596c32131bd1e94e13f9662b3c06c8c7f5697931012cf806e4fe890d39babd8416a9a9382cbd8765@35.241.177.70:30313")
admin.addPeer("enode://8583f990f2b40fc20e3c4c779b5cdd301071f5bcd1cc32edd7efac566efe0ddf3a7ad8ecad4072f966c56bff913928275918079a26bea8a8f35c5ade72ff5caa@35.241.177.70:30314")


admin.addPeer("enode://c4b924871aa8706a9a07da15bdf450bfb8fbea29a376d26c5649ce2ff9ededa0a2e18ba9ecf8c1f72e626fe274a441cddeb1e831f9e72bb38b4c208405ef5f21@35.243.190.93:30311")
admin.addPeer("enode://1c8891af2328e9cd42dbe46e4d38484ee70d8f371e4310ae4c16b287d6562dbee2ef903d572a09b80e0da1c4b03a483cef723d88616050a27367fd6c960ee055@35.243.190.93:30313")
admin.addPeer("enode://461a358b6bde98f6a29db00f63a552df9e6e72241343c3190380231e551308296f1f875e39109c90796a5cb7551cf505131fa4d317dd44f5bb17f8b1704b09a9@35.243.190.93:30314")
admin.addPeer("enode://36250ccae990efa6d3cf26841c57bf3ce20f0da94f5f8506d3a56d7aacf556d0b5604677cfe0d22c10e9f13b9ca65b8532ac45ec22b2113450f830ed5d3e8477@35.243.190.93:30315")


admin.addPeer("enode://83d248abd03c311bba6c998b1d265bd5313ba11ee617a5978e90c5051bdf08cfd91e998f81a1515ffc08b4d6c63cd3cdaafe9d6bdf435e3b4350d2441e06b59c@35.195.84.56:30311")
admin.addPeer("enode://5dddf9570b93afdc923bfb6eb13779fdb4d98a27d67a5eb549a7ede5a519d430be34e580d081e4c37378ac2df05096e290ce9fb3623fa2486aec948575bdf9f8@35.195.84.56:30312")
admin.addPeer("enode://f93d666e040df1f71fe3808b5f9e34e46c88354294ee0704192fa659d3644429966b437998d96b9eb3215831afed2f09c91857ea2623171dee9c6d577211b600@35.195.84.56:30313")
admin.addPeer("enode://a1e8c3d3a9dd56ca9bac501cdaa217c544e9450a64b1504866069bb4eabffd78cef31477f768a4d37610b7b23a6c21b2099c999e11669830853253ccc7ee75c6@35.195.84.56:30314")









