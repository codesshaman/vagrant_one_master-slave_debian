# -*- mode: ruby -*-
# vi: set ft=ruby :

MASTER_NODE_HOSTNAME = 'master'
WORKER_NODE_HOSTNAME = 'worker'
MEM = 512
CPU = 1

# create machines config
Vagrant.configure("2") do |config|
	config.vm.box = "bento/debian-11"
	config.vm.provider "virtualbox" do |v|
		v.memory = MEM
		v.cpus = CPU
		id_rsa_pub = File.read("#{Dir.home}/.ssh/id_rsa.pub")
		config.vm.provision "copy ssh public key", type: "shell",
		inline: "echo \"#{id_rsa_pub}\" >> /home/vagrant/.ssh/authorized_keys"
	end
  # master node 1
	config.vm.define 'Master1' do |master1|
		master.vm.hostname = MASTER_NODE_HOSTNAME
		master.vm.network :private_network, ip: '192.168.56.10'
		master.vm.provider "virtualbox" do |v|
			v.name = 'Master1'
		end
	end
  # master node 2
	config.vm.define 'Master2' do |master2|
		master.vm.hostname = MASTER_NODE_HOSTNAME
		master.vm.network :private_network, ip: '192.168.56.20'
		master.vm.provider "virtualbox" do |v|
			v.name = 'Master2'
		end
	end
  # master node 3
	config.vm.define 'Master3' do |master3|
		master.vm.hostname = MASTER_NODE_HOSTNAME
		master.vm.network :private_network, ip: '192.168.56.30'
		master.vm.provider "virtualbox" do |v|
			v.name = 'Master3'
		end
	end

  # worker node 1
	config.vm.define 'Worker1' do |worker1|
		worker.vm.hostname = WORKER_NODE_HOSTNAME
		worker.vm.network :private_network, ip: '192.168.56.110'
		worker.vm.provider "virtualbox" do |v|
			v.name = 'Worker1'
		end
	end
  # worker node 2
	config.vm.define 'Worker2' do |worker2|
		worker.vm.hostname = WORKER_NODE_HOSTNAME
		worker.vm.network :private_network, ip: '192.168.56.120'
		worker.vm.provider "virtualbox" do |v|
			v.name = 'Worker2'
		end
	end
  # worker node 3
	config.vm.define 'Worker3' do |worker3|
		worker.vm.hostname = WORKER_NODE_HOSTNAME
		worker.vm.network :private_network, ip: '192.168.56.130'
		worker.vm.provider "virtualbox" do |v|
			v.name = 'Worker3'
		end
	end
end
