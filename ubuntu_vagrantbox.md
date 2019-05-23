# Craete ubuntu box

1. Create VM installed ubuntu on Virtual box
2. Install make by below comand

   ```bash
   sudo apt install make
   ```

3. Insert CD

4. Start CD start up program

5. Make home directories english by below command

   ```bash
   LANG=C xdg-user-dirs-gtk-update
   ```

6. Install Typora by below command

   ```bash
   wget -qO - https://typora.io/linux/public-key.asc | sudo apt-key add -
   sudo add-apt-repository 'deb https://typora.io/linux ./'
   sudo apt-get update
   sudo apt-get install typora
   ```

   

7. Packages upgrade

8. Reboot

9. Shutdown

10. Create box on host OS by below command

    ```bash
    vagrant package --base [virtualbox vm name]
    vagrant box add sabotagecla6/ubuntu1804 package.box
    ```

11. Confirm whether ubuntu box is added by below command

    ```bash
    vagrant box list
    ```



# Create VM from box

1. Create Vagrantfile by below command

   ```bash
   vagrant init sabotagecla6/ubuntu1804
   ```

2. Edit Vagrantfile like below

   ```bash
   # -*- mode: ruby -*-
   # vi: set ft=ruby :
   
   Vagrant.configure("2") do |config|
     config.vm.box = "sabotagecla6/ubuntu1804"
   
     config.vm.provider "virtualbox" do |vb|
       vb.gui = true
       vb.memory = "2048"
     end
   
     config.vm.provision "shell", inline: <<-SHELL
       apt-get update
       apt-get upgrade
     SHELL
   end
   ```

3. move directory that exists Vagrantfile Start vagrant by below command

   ```bash
   vagrant up
   ```

4. login by below user

   | username      | password |
   | ------------- | -------- |
   | Administrator | Admin    |

   
