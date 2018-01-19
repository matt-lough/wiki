## Setting up Non-AWS Node for MoC/Validator/Bootnode Deployment
#### Minimum System Requirements
Create Ubuntu 16.04 Server Image with minimum of 1 CPU and 1 GB Memory. At the blockchain's current state, it does not need much HD space. The minimum available should work on any cloud service (4GB or more), but may need to be upgraded in future when more transactions get added to the blockchain. 

In order for Ansible Playbook scripts to work, you need to set up your remote machine (validator, bootnode, etc) to have a sudo user that can execute sudo without password. This node also needs to be set up so you can SSH into it using a SSH-Key. Please, follow directions below to set up remote node.

## Getting Started
After you obtain your `Public IP` from your cloud service, we can now start. Replace `192.0.2.1` used in this guide, with your `Public IP` throughout the guide. We will use the username `ubuntu` in this guide, but if you have a different sudo username, edit `site.yml` and change `user: ubuntu` to your sudo w/o password user.

### root or not to root
This guide will assume the cloud service allows you to log in with `root`. If you already have a `sudo` user, skip to [Execute sudo without password](#execute-sudo-without-password) and replace the username `ubuntu` & `root` used in this guide with your `sudo` username and append `sudo` in front of the commands below. __Azure__ cloud service's root account is disabled by default so use the user you created during deployment and skip to second section.

#### Connect and Add User with Sudo Privileges
1. SSH into Remote Node using the root password provided by cloud service (either by web portal or email). If you already have `sudo` user, replace `root` with your user and skip the next two steps.
- Azure users will not have access to their root account by default. Use your sudo user and skip to next section after connecting.

        ssh root@192.0.2.1

2. Logged in as `root` add user and grant sudo privileges. It is recommended to use default user `ubuntu`.

        adduser ubuntu

    - Enter a password to protect the user and you can leave the next 5 fields blank. Confirm the information is correct.

3. Grant user `ubuntu` sudo privileges

        usermod -aG sudo ubuntu

#### Execute sudo without password
One of the requirements for the Ansible script to run properly is root/sudo privileges without password. Since using `root` account is not recommended, we add a line of code to allow our `ubuntu` user to do just this. __If you are logged into sudo user instead of root, append `sudo` to the beginning of each cli command.__

1. Create a new file in `sudoers.d` directory, this new file can be named anything

        nano /etc/sudoers.d/user

2. Enter the line below in the new file and then hit `Ctrl + x` to exit `y + Enter` to save

        ubuntu ALL=(ALL) NOPASSWD:ALL

    - Replace `ubuntu` with your sudo username, if different.

5. Exit current SSH Session to generate/install SSH keys

        exit

#### Generating SSH Key and Copying to Node
1. On your local control machine, let's generate our SSH keys. It is recommended to use a different SSH Key for each bootnode/validator node deployed. There are two easy ways to do this since SSH by default uses `id_rsa` to connect via SSH.  
     1. Create new user on local machine for each node to deploy. If done this way, use the default `id_rsa` SSH key name while generating SSH key, to be automatically configured.

    2. Create a ssh `config` file and specify `hostname` & `IndentityFile` for each node and label keys accordingly. If done this way, please follow the [Multiple SSH Keys](Multiple-SSH-Keys) wiki guide.

                ssh-keygen -t rsa -b 4096 -C "node-label"

    - If deploying using different local user for each node (multiple deployments only) please leave SSH key name as default `id_rsa` by just pressing `enter`.

    - Enter a __strong__ password (write it down) and save the key as something memorable, enter complete path to key to save as custom name. e.g. below

                ~/.ssh/sokol-bootnode1

        - This will save 2 files, .pub will be your public key and the other is your private key. Private SSH key stays on your local machine and Public key gets copied to remote machines you want access to.

2. Copy your newly generated SSH key to your remote node

        ssh-copy-id -i ~/.ssh/sokol-bootnode1 ubuntu@192.0.2.1
    
    - It will ask if you would like to accept the new public key, type `yes + enter` and it will automatically add SSH Key to remote machine.

Your Non-AWS node is now ready for configuration using ansible-playbook provided by POA. Please follow the corresponding section in the wiki to finish deploying your node.

- [Non-AWS Validator Setup](Validator-Node-Non-AWS)
- [Non-AWS Bootnode Setup](Bootnode-Setup-Non-AWS)