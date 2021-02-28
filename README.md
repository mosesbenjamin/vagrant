## Versioning Environments with Vagrant

#### Installation

- Install vagrant and virtualbox
- verify successful install
  - vagarant -v
  - vboxmanage -v
- Verify ssh (add ssh client to path on windows)

#### To spin up a virtualized ubuntu environment

- Make a directory
- cd /directory and run
  - vagrant init hashicorp/precise32
  - vagrant up
  - vagrant ssh
  - To play around
    - uname -a

#### To disable vagrant from running headless

- exit the ssh sesion
  - exit
- To list running vms
- vboxmanage list runningvms
- Uncomment lines in vagrantfile
- run
  - vagrant reload
- vagrant is the default username and password

#### Sharing files

- vagrant ssh
- Default location where vagrant shares files
  - cd /vagrant/
  - ls
  - cat filename

#### Suspending the VM

- exit the VM
- vagrant suspend
- Revive environment
  vagrant resume

#### Halting the VM

- vagrant halt
- To resume the VM
  - vagrant up

#### Destroying the VM

- First list all vms
  - vboxmanage list vms
- vagrant destroy

#### Web development environment and vagrant fundamentals

- mkdir nginx
- cd; run
  - vagrant init hashicorp/precise32
- To not display commented out codeblocks inside vagarantfile:
  - vagrant init hashicorp/precise32 --minimal
- After modifying the vagrantfile, run:
  - vagrant reload
  - vagrant provision
  - vagrant ssh
    - service nginx status
    - wget -qO- localhost
      - NB: q=keep process quiet, O- = write to stdout
