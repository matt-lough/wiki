## Setting up Non-AWS VM for Validator Node Deployment

#### Last Updated: 2018/02/01
#### Changelog:
- **2018/02/01**: Add instructions to set validator metadata.
- **2018/01/28**: Add instructions to recommend creating a local Ansible Control Station user, clarify where to collect AWS Node IP info, add more info and correct a few typos.
- **2017/12/27**: Add info about Sokol testnet
- **2017/12/21**: Rewrite part about security groups (how to close access). Add description of the option to use elastic IP.

### MoC: Master of Ceremony Key Exchange & Generation
1. Start Chrome
2. Connect to the desired network in MetaMask by selecting the `Network` dropdown menu on MetaMask and add `Custom RPC` with the following endpoints.
 - Core Network: `https://core.poa.network`
 - Sokol Test Network: `https://sokol.poa.network`
3. Upload your initial key to MetaMask that MoC has supplied you using the password provided.
4. Navigate your chrome browser to [https://ceremony.poa.network/](https://ceremony.poa.network/)
- Make sure you have your `Initial Key` supplied by MoC, selected in MetaMask.
5. Click "Generate keys", confirm transaction.
6. __ATTENTION:__ This next part is __VERY__ important and must be done correctly in order to be able to participate in the consensus immediately, follow directions below __BEFORE__ closing out of the browser window. Open up a Notepad and copy required info as follows.
- Click the `Copy` Button next to each `Address`. Mining, Payout, Voting. Paste them separately in the Notepad.
- Click the `Copy` Button next to each `Password`, matching to resulting address in the Notepad. Mining, Payout, Voting.
- Finally, Click Button to download the JSON Keystore files for each key and keep the Notepad file & all 3 keys + initial key somewhere safe.  
__*NOTE*__  
Preferred method to store the keyfiles and information is to store on an encrypted drive. e.g. usb drive  
If you go this route, please do not forget your password for the encryption as you will lose your data and will have to get your old keys voted out and new ones voted in if any issue happens with the validator's node.

### After Ceremony Stage: Validators vote in new validators
After the initial ceremony stage, it's time for the initial set of validators to vote in new validators using the POA Voting Dapp. One validator will create a Ballot for each of the needed keys to participate and each validator will cast their own vote minus the MoC, who is not allowed to vote on consensus level. It has been agreed upon by the POA network that the next stage would end with 25 Validators on the Core network. This number may change in the future and can have any amount one desires, this would likely be proposed by a ballot to increase.  

Before the ballot can be proposed, the applicant would need to generate 3 separate key pairs with passwords & JSON keyfiles. There is a very simple method of doing this, see below.
1. Simply go to this URL in your browser to generate 3 key/pass pairs with needed keyfiles.
- [https://ceremony.poa.network/#just-generate-keys](https://ceremony.poa.network/#just-generate-keys)
6. __ATTENTION:__ This next part is __VERY__ important and must be done correctly in order to be able to participate in the consensus immediately, follow directions below __BEFORE__ closing out of the browser window. Open up a Notepad and copy required info as follows.
- Click the `Copy` Button next to each `Address`. Mining, Payout, Voting. Paste them separately in the Notepad.
- Click the `Copy` Button next to each `Password`, matching to resulting address in the Notepad. Mining, Payout, Voting.
- Finally, Click Button to download the JSON Keystore files for each key and keep the Notepad file & all 3 keys + initial key somewhere safe.  
__*NOTE*__  
Preferred method to store the keyfiles and information is to store on an encrypted drive. e.g. usb drive  
If you go this route, please do not forget your password for the encryption as you will lose your data and will have to get your old keys voted out and new ones voted in if any issue happens with the validator's node.

##### After you have successfully deployed your node, Submit your Validator MetaData
1. Follow the guide on how to [Update Validator MetaData](https://github.com/poanetwork/wiki/wiki/Validator-Set-Metadata).

#### Local/Remote Machine System Requirements
##### Remote Machine Minimum System Requirements
- Ubuntu 16.04 Image
- Minimum 1 CPU
- Minimum 1GB Memory
- Anything > 4GB will be good, but may need to be upgraded in the future

##### Control Machine Dependencies
- Linux Based Bash Terminal
- Python 2 (v2.6-v2.7)/Python3 (v3.5+)
- Ansible v2.3+
- Git

### Getting Started
Log into your Cloud Dashboard and deploy a new node with a minimum of 1 CPU, 1GB (1024Mb) Memory & at least 4GB Hard Drive Capacity (This may need to be upgraded in future). This guide will be using `ubuntu` as the username, use the default or replace with your `sudo` username.
- If prompted to create new user during deployment, do so and skip the section about adding new user.  
- If prompted to add SSH Key for your new user, follow the steps below to generate your SSH Key and follow directions how to add to deployment.

#### Generating SSH Key
1. On your local control machine, open a terminal and generate your SSH key. It is recommended to use a different SSH Key for each POA network, key for `core` & key for `sokol`. We can set a parameter in ansible inventory script to use the specific key.

        ssh-keygen -t rsa -b 4096 -C "node-label"

    Enter a __STRONG__ password (write it down) and save the key as something memorable, enter complete path to key to save as custom name, replacing `user` with your current local user. e.g. below

        /home/ubuntu/.ssh/id_poa-core
        /home/ubuntu/.ssh/id_poa-sokol

 - This will save 2 files, .pub will be your public key and the other is your private key. Private SSH key stays on your local machine and Public key gets copied to remote machines you want access to.

#### Add User with Sudo Privileges 
1. SSH into Remote Node using the root password provided by cloud service (either by web portal or email) or using the SSH key supplied during deployment. If you already have `sudo` user, replace `root` with your user and skip the next two steps.  
 __*Azure users will not have access to their root account by default, use your sudo user and skip to next section after connecting.*__

        ssh root@192.0.2.1

2. Logged in as `root` add user and grant sudo privileges. It is recommended to use default user `ubuntu`.

        adduser ubuntu

- Enter a __STRONG__ password to protect the user and you can leave the next 5 fields blank. Confirm the information is correct. We will be using a parameter to ask `sudo` pass during ansible deployment.

3. Grant user `ubuntu` sudo privileges

        usermod -aG sudo ubuntu

Your Non-AWS node is now ready for configuration using ansible-playbook provided by POA. Please follow the directions below to obtain the `deployment-playbooks` required to configure network node.

### Configure node with Deployment-playbook
To run playbook you will need a user on the server with `sudo` privileges and who can be logged in via SSH public key. By default it is assumed that this user is called `ubuntu`. If you already have a user with different name who satisfies these requirements, at the top of `site.yml` in `-hosts: all` section change line `user: ubuntu` to the `sudo` user you have

```
---
- hosts: all
  user: ubuntu
  become: True
...
```
_NOTE_: Playbook will additionally create a new unprivileged user named `validator` and add your ssh public key to `root` account.

3. Clone repository with ansible playbooks and checkout branch with the network name you want to join (e.g. `core` for mainnet and `sokol` for testnet)
```
git clone https://github.com/poanetwork/deployment-playbooks.git
cd deployment-playbooks
# for core mainnet
git checkout core
# OR for sokol testnet
git checkout sokol
# check that you ended up on a correct branch (look where the `*` is)
git branch
```

4. two files with ssh public key need to be created for ansible playbook to configure node correctly, use the path to your desired key.
```
cat ~/.ssh/id_poa-core.pub > files/admins.pub
cp files/admins.pub files/ssh_validator.pub
```

5. create configuration file
```
cat group_vars/all.network group_vars/validator.example > group_vars/all
```

6. edit the `group_vars/all` file and comment out parameters corresponding to aws:
```
#access_key
#secret_key
#awskeypair_name
#vpc_subnet_id
```

7. set values given to you by Master of Ceremony for the following parameters in `group_vars/all`:
* `NODE_FULLNAME` - your real name (will be visible to other mebers of the network)
* `NODE_ADMIN_EMAIL` - your public email address (will be visible to other members of the network)
* `MINING_KEYFILE` - insert content of your mining keystore json file. Resulting value should be enclosed in single quotes and look similar to this: `MINING_KEYFILE: '{"address":"..."}'`
* `MINING_ADDRESS` - insert your mining key address, e.g. `MINING_ADDRESS: "0x..."`
* `MINING_KEYPASS` - insert your mining key password

8. set values given to you by Master of Ceremony for the following parameters in `group_vars/all`:
* `NETSTATS_SERVER`
* `NETSTATS_SECRET`

9. set the following options as follows in `group_vars/all`:
```
allow_validator_ssh: true
allow_validator_p2p: true
associate_validator_elastic_ip: false
```
_Double check that_ `allow_validator_ssh` _is_ `true` _otherwise you won't be able to connect to the node_.

9. create file `hosts` with the server's ip address (e.g. 192.0.2.1):
```
[validator]
192.0.2.1
```

10. run ansible playbook, replace the `--key-file` path with your desired SSH key
```
ansible-playbook -i hosts site.yml -K --key-file "~/.ssh/id_poa-core"
```

11. open `NETSTATS_SERVER` url in the browser and check that the node named `NODE_FULLNAME` appeared in the list

12. login to the node and get enode from parity logs:  
_Without access to `root` you can use `sudo` user instead, append `sudo` in front of commands after connecting to remote machine_
```
ssh root@192.0.2.1
grep enode /home/validator/logs/parity.log
```
copy `enode` uri and send it to Master of Ceremony. If this line is not found, restart parity
```
systemctl restart poa-parity
```
and try again. If `enode` uri is still not found, use the commands below to restart all services.

_NOTE_ if after parity restart you notice that on `NETSTATS_SERVER` url your node starts to fall behind other nodes (block number is less than on other nodes), try to restart statistics service (assuming you are connected as `root`):
```
su validator
pm2 restart all
```
after that refresh `NETSTATS_SERVER` url and check your node's block number. If your node is still not active or missing `enode`, log in to root account and reboot.  
_Without access to `root` you can use `sudo` user instead, append `sudo` in front of commands after connecting to remote machine_
```
su
shutdown -r now
```
