Vagrant.configure("2") do |config|
  servers=[
    {
      :hostname => "ansible-control",
      :box => "geerlingguy/centos7",
      :ip => "192.168.56.100",
      :ssh_port => '2215'
    },
    {
      :hostname => "node1",
      :box => "geerlingguy/centos7",
      :ip => "192.168.56.101",
      :ssh_port => '2210'
    },
  ]

  servers.each do |machine|

    config.vm.define machine[:hostname] do |node|
      node.vm.box = machine[:box]
      node.vm.hostname = machine[:hostname]
    
      node.vm.network :private_network, ip: machine[:ip]
      node.vm.network "forwarded_port", guest: 22, host: machine[:ssh_port], id: "ssh"

      node.vm.provider :virtualbox do |v|
        v.customize ["modifyvm", :id, "--memory", 2024]
        v.customize ["modifyvm", :id, "--name", machine[:hostname]]
      end
    end
  end

end