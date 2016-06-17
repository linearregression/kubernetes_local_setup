## kubernetes_local_setup (On Ubuntu).
Step 1:
  Install the following packages in your Linux Machine.
    - vagrant (sudo apt-get install virtualbox)
    - virtualbox (sudo apt install vagrant)
    - nfs-server (sudo apt install nfs-server)
  Install kubectl.
    $ wget https://storage.googleapis.com/kubernetes-release/release/v1.0.1/bin/linux/amd64/kubectl
    $ chmod +x kubectl
    $ mv kubectl /usr/local/bin/
    
  After this you can start your own instance of virtual box.
  But before that we need the Vagrant file which contains all the configuration for our instance of VM
  Here I am using configuration files from a friend.
    --files will be uploaded soon
  So you node go into vagrant folder and do 
    $ vagrant up
  This starts our virtual box. 
  Configuring kubectl to interact to our kubernetes:
		# must be run from the same folder where the custom config file is present
		$ export KUBECONFIG="${KUBECONFIG}:$(pwd)/kubeconfig"
		$ kubectl config use-context vagrant-single

  Note #
		vagrant up # must be run from the same folder/sub-directory  where the vagrant     file is present


  
