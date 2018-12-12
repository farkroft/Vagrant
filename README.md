# Vagrant
- Install vagrant
  https://www.vagrantup.com/
- setup ubuntu
  - 
  - edit file di folder yang diinstall vagrant, ada file Vagrantfile
  - edit file di bagian vm.box ganti dengan box yang diinstall
    ```
    config.vm.box = "ubuntu/trusty64"
    ```
- setup forwarder port
  - edit Vagrantfile, di bagian vm.network forwarder port (uncomment)
    ```
    # Create a forwarded port mapping which allows access to a specific port
    # within the machine from a port on the host machine. In the example below,
    # accessing "localhost:8080" will access port 80 on the guest machine.
    # NOTE: This will enable public access to the opened port
    config.vm.network "forwarded_port", guest: 80, host: 8080
    ```   
- setup private ip
  - edit Vagrantfile, di bagian private ip
    ```
    config.vm.network "private_network", ip: "192.168.33.10"
    ```
# Setup rails app
- install ruby, install rails, install postgresql
  https://gorails.com/setup/ubuntu/14.04
 
# Setup Puma
- Install puma
- file puma sockets

# Setup nginx
- install nginx
- setup nginx proxy

- ssh vagrant | vagrant ssh
- masuk root | sudo su
- create user | adduser <yourname>
- root privilege | usermod -aG sudo <yourname>
- change user to your user | su - <yourname>
- create folder .ssh | mkdir .ssh
- add permission to folder | chmod 700 ~/.ssh
- create file authorized keys | vim authorized_keys atau bisa juga nano authorized_keys
- copy your local keys into authorized_keys file | chmod 600 authorized keys
- testing ssh with your username from local machine | ssh <yourname>@127.0.0.1 -p 2222

tail -f shared/log/puma.stdout.log >> untuk melihat log puma dari app
ps aux >> untuk melihat history background process
ps aux | grep puma >> untuk melihat history background process puma
bundle exec puma >> untuk jalanin puma
bundle exec puma --daemon >> untuk jalanin puma di background process
RACK_ENV=production bundle exec puma -C config/puma.rb >> jalanin puma lewat config puma.rb
