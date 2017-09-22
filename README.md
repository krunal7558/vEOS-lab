# vEOS-lab
Arista vEOS lab
$ git clone https://github.com/krunal7558/vEOS-lab
Cloning into 'vEOS-lab'...
remote: Counting objects: 12, done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 12 (delta 1), reused 7 (delta 0), pack-reused 0
Unpacking objects: 100% (12/12), done.
Checking connectivity... done.
$ cd vEOS-lab/
/vEOS-lab $ ls -la
-rw-rw-r-- 1 krunal krunal 933341884 Sep 15 21:47 vEOS-lab-4.18.1F-virtualbox.box
/vEOS-lab $ vagrant box add vEOS-lab-4.18.1F vEOS-lab-4.18.1F-virtualbox.box
/vEOS-lab $ vagrant box list
vEOS-lab-4.18.1F (virtualbox, 0)
/vEOS-lab $ vagrant init vEOS-lab-4.18.1F
A `Vagrantfile` has been placed in this directory. You are now
ready to `vagrant up` your first virtual environment! Please read
the comments in the Vagrantfile as well as documentation on
`vagrantup.com` for more information on using Vagrant.
/vEOS-lab $ vagrant up


