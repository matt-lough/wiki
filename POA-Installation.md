
Running a full node that is synced to POA Network's blockchain will require you to install `Parity` Ethereum client and to start the client with extra parameters using POA's `spec.json` configuration. This allows you to send/receive transactions on POA Core/Sokol network and interact with deployed Contracts/Dapps, sign transactions and much more in the GUI interface. Follow directions below to install `Parity` Client and Connect to desired POA network.

## Installation of Parity

### Ubuntu/Debian & MacOS with Homebrew one-line Binary Installation
This method is for Ubuntu/Debian based OS and MacOS machines with Homebrew installed. Faster than building from source, but no cutting edge features or latest version. If you would like to build from [source](https://github.com/paritytech/parity) or download binary release, see the official [Parity Releases Page](https://github.com/paritytech/parity/releases).   
  Please use `Parity v1.8.5` or later. 

- Open a bash Terminal and enter the command below, if the client needs an update just simply run the command a second time.  
  ```
  bash <(curl https://get.parity.io -kL)
  ```  

This will install and configure the Parity client for you. On Ubuntu, this script will also offer to install the Netstats client and connect it to ethstats.net. If you plan on using `Parity` for POA only, there is no need to install the extra software. To connect to POA Network using `Parity` on Linux/MacOS, please follow the appropriate section below.

#### Installing from the Linux distro Snap Service
``` 
sudo snap install parity --edge
```
### Installing Parity on Windows
Parity on Windows can either be installed as a System Service or executed from a folder. Head over to [Parity's Releases Page](https://github.com/paritytech/parity/releases) and choose the desired executable file. To connect to POA Network using `Parity` on Windows, please follow the appropriate section below.

## Connecting to and Syncing with POA Networks

### Connecting Linux/MacOS to POA Network on Parity
1. Obtain [spec.json](https://github.com/poanetwork/poa-chain-spec/blob/core/spec.json) and [bootnodes.txt](https://github.com/poanetwork/poa-chain-spec/blob/core/bootnodes.txt) files from POA Github.  
  __*NOTE*__  For POA Sokol Testnet, Select the appropriate 'Branch' on Github.  
  ##### By cloning the Github Repo
For Core(live) network
```
git clone -b core https://github.com/poanetwork/poa-chain-spec.git
```
For Sokol(test) network
```
git clone -b sokol https://github.com/poanetwork/poa-chain-spec.git
```

2. In terminal run    
```
parity --chain /path/to/spec.json --bootnodes /path/to/bootnodes.txt ui
```
If you would like to limit or choose specific bootnodes, run 
```
parity --chain /path/to/spec.json --bootnodes enode://ENODE@IP:PORT,enode://ENODE@IP:PORT ui
```
Enter all the supplied enodes for the desired network separated by a comma, no space. The `ui` is only needed if you would like to use the graphics enabled browser wallet to get the full experience.

### Connecting a Windows machine to POA Network on Parity
1. Obtain [spec.json](https://github.com/poanetwork/poa-chain-spec/blob/core/spec.json) and [bootnodes.txt](https://github.com/poanetwork/poa-chain-spec/blob/core/bootnodes.txt) files from POA Github.  
  __*NOTE*__  For POA Sokol Testnet, Select the appropriate 'Branch' on Github.  
  ##### Using Git Bash
For Core(live) network
```
git clone -b core https://github.com/poanetwork/poa-chain-spec.git
```
For Sokol(test) network
```
git clone -b sokol https://github.com/poanetwork/poa-chain-spec.git
```

2. Open Windows Command Prompt CMD or Windows Powershell and navigate to `Parity` executive file.    
```
parity --chain c:\path\to\spec.json --bootnodes c:\path\to\bootnodes.txt ui
```
If you would like to limit or choose specific bootnodes, run 
```
parity --chain c:\path\to\spec.json --bootnodes enode://ENODE@IP:PORT,enode://ENODE@IP:PORT ui
```
Enter all the supplied enodes for the desired network separated by a comma, no space. The `ui` is only needed if you would like to use the graphics enabled browser wallet to get the full experience.
