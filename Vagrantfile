# -*- mode: ruby -*-
# vi: set ft=ruby :

# two spine and 4 leaf in Leaf and spine topology
#

default_box = 'vEOS-lab-4.18.1F'

Vagrant.configure(2) do |config|
  config.vm.define 'spine01' do |spine01|
    spine01.vm.box = default_box
    spine01.vm.network 'private_network',
                       virtualbox__intnet: 's01l01',
                       ip: '169.254.1.11', auto_config: false
    spine01.vm.network 'private_network',
                       virtualbox__intnet: 's01l02',
                       ip: '169.254.1.11', auto_config: false
    spine01.vm.network 'private_network',
                       virtualbox__intnet: 's01s02',
                       ip: '169.254.1.11', auto_config: false
    spine01.vm.network 'private_network',
                       virtualbox__intnet: 's01l03',
                       ip: '169.254.1.11', auto_config: false
    spine01.vm.network 'private_network',
                       virtualbox__intnet: 's01l04',
                       ip: '169.254.1.11', auto_config: false
    spine01.vm.network 'forwarded_port', guest: 443, host: 8443
    spine01.vm.provision 'shell', inline: <<-SHELL
      sleep 30
      FastCli -p 15 -c "configure
      hostname spine01
      username eapiuser privilege 15 role network-admin secret icanttellyou
      management api http-commands
      no shutdown
      interface Management1
        ip address 192.168.56.101/24 secondary
      end"
    SHELL
  end

  config.vm.define 'spine02' do |spine02|
    spine02.vm.box = default_box
    spine02.vm.network 'private_network',
                       virtualbox__intnet: 's02l01',
                       ip: '169.254.1.11', auto_config: false
    spine02.vm.network 'private_network',
                       virtualbox__intnet: 's02l02',
                       ip: '169.254.1.11', auto_config: false
    spine02.vm.network 'private_network',
                       virtualbox__intnet: 's01s02',
                       ip: '169.254.1.11', auto_config: false
    spine02.vm.network 'private_network',
                       virtualbox__intnet: 's01l03',
                       ip: '169.254.1.11', auto_config: false
    spine02.vm.network 'private_network',
                       virtualbox__intnet: 's01l04',
                       ip: '169.254.1.11', auto_config: false
    spine02.vm.network 'forwarded_port', guest: 443, host: 8444
    spine02.vm.provision 'shell', inline: <<-SHELL
      sleep 30
      FastCli -p 15 -c "configure
      hostname spine02
      interface Management1
        ip address 192.168.56.102/24 secondary
      username eapiuser privilege 15 role network-admin secret icanttellyou
      management api http-commands
      no shutdown
      end"
    SHELL
  end

  config.vm.define 'leaf01' do |leaf01|
    leaf01.vm.box = default_box
    leaf01.vm.network 'private_network',
                       virtualbox__intnet: 's01l01',
                       ip: '169.254.1.11', auto_config: false
    leaf01.vm.network 'private_network',
                       virtualbox__intnet: 's02l01',
                       ip: '169.254.1.11', auto_config: false
    leaf01.vm.network 'private_network',
                       virtualbox__intnet: 'l01l02',
                       ip: '169.254.1.11', auto_config: false
    leaf01.vm.network 'forwarded_port', guest: 443, host: 9443
    leaf01.vm.provision 'shell', inline: <<-SHELL
      sleep 30
      FastCli -p 15 -c "configure
      hostname leaf01
      interface Management1
        ip address 192.168.56.103/24 secondary
      username eapiuser privilege 15 role network-admin secret icanttellyou
      management api http-commands
      no shutdown
      end"
    SHELL
  end

  config.vm.define 'leaf02' do |leaf02|
    leaf02.vm.box = default_box
    leaf02.vm.network 'private_network',
                       virtualbox__intnet: 's01l02',
                       ip: '169.254.1.11', auto_config: false
    leaf02.vm.network 'private_network',
                       virtualbox__intnet: 's02l02',
                       ip: '169.254.1.11', auto_config: false
    leaf02.vm.network 'private_network',
                       virtualbox__intnet: 'l01l02',
                       ip: '169.254.1.11', auto_config: false
    leaf02.vm.network 'forwarded_port', guest: 443, host: 9444
    leaf02.vm.provision 'shell', inline: <<-SHELL
      sleep 30
      FastCli -p 15 -c "configure
      hostname leaf02
      interface Management1
        ip address 192.168.56.104/24 secondary
      username eapiuser privilege 15 role network-admin secret icanttellyou
      management api http-commands
      no shutdown
      end"
    SHELL
  end

  config.vm.define 'leaf03' do |leaf03|
    leaf03.vm.box = default_box
    leaf03.vm.network 'private_network',
                       virtualbox__intnet: 's01l03',
                       ip: '169.254.1.11', auto_config: false
    leaf03.vm.network 'private_network',
                       virtualbox__intnet: 's02l03',
                       ip: '169.254.1.11', auto_config: false
    leaf03.vm.network 'private_network',
                       virtualbox__intnet: 'l03l04',
                       ip: '169.254.1.11', auto_config: false
    leaf03.vm.network 'forwarded_port', guest: 443, host: 9445
    leaf03.vm.provision 'shell', inline: <<-SHELL
      sleep 30
      FastCli -p 15 -c "configure
      hostname leaf03
      interface Management1
        ip address 192.168.56.105/24 secondary
      username eapiuser privilege 15 role network-admin secret icanttellyou
      management api http-commands
      no shutdown
      end"
    SHELL
  end

  config.vm.define 'leaf04' do |leaf04|
    leaf04.vm.box = default_box
    leaf04.vm.network 'private_network',
                       virtualbox__intnet: 's01l04',
                       ip: '169.254.1.11', auto_config: false
    leaf04.vm.network 'private_network',
                       virtualbox__intnet: 's02l04',
                       ip: '169.254.1.11', auto_config: false
    leaf04.vm.network 'private_network',
                       virtualbox__intnet: 'l03l04',
                       ip: '169.254.1.11', auto_config: false
    leaf04.vm.network 'forwarded_port', guest: 443, host: 9446
    leaf04.vm.provision 'shell', inline: <<-SHELL
      sleep 30
      FastCli -p 15 -c "configure
      hostname leaf04
      interface Management1
        ip address 192.168.56.106/24 secondary
      username eapiuser privilege 15 role network-admin secret icanttellyou
      management api http-commands
      no shutdown
      end"
    SHELL
  end
end
