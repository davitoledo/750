Vagrant.configure("2") do |config|
## Escolhendo a box do CentOS 7 
	config.vm.box = "centos/7"

	## Definindo IP Fixo para a VM dentro da rede virtual
	config.vm.network "private_network", ip: "192.168.56.40"
	## Definindo um redirecionamento da porta 80 da Vm para a porta 8080 da maq fisica.
	config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1", protocol: "tcp"

## Definindo uma execucao ao provisionar a maq atraves de sequenci do shell. 

	config.vm.provision "shell", 
	inline: <<-SHELL
	yum install -y cowsay
	yum install -y links
	yum install -y httpd
	SHELL

end
	 

