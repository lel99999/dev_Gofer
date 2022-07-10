Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.memory = "1024"
    v.cpus = 2
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "70"]
  end
# config.trigger.after :up do |trigger|
#   run "subscription-manager register --username <username> --password <password> --auto-attach
#   trigger.name = "After-Up Trigger ..."
#   trigger.info = "Trigger Execution ..."
#   trigger.run = { path:"subscription-manager register --username <username> --password <password> --auto-attach"}
# end

  config.vm.define :roletester do |roletester|
#   roletester.vm.box = "bento/centos-6.10"
#   roletester.vm.box = "clouddood/RH7.5_baserepo"
    roletester.vm.box = "clouddood/RH7.9_infra"
    roletester.vm.host_name = "roletester.test.dev"

    roletester.ssh.forward_agent = true

    roletester.vm.provision "ansible" do |ansible|
#     ansible.playbook = "deploy_gocd.yml"
      ansible.playbook = "deploy_BaseSystem.yml"
      ansible.inventory_path = "vagrant_hosts"
#     ansible.tags = ansible_tags
#     ansible.verbose = ansible_verbosity
#     ansible.extra_vars = ansible_extra_vars
#     ansible.limit = ansible_limit
    end

#   roletester.vm.network :private_network, ip: "10.0.1.26"
    roletester.vm.network :private_network, ip: "192.168.60.25"
  end


#######################################################################################################################################

# config.vm.define "gocdRH7" do |gocdRH7|
#   gocdRH7.vm.box = "clouddood/RH7.5_baserepo"
#   gocdRH7.vm.hostname = "gocdRH7"
#   gocdRH7.vm.network "private_network", ip: "192.168.60.148"
#   gocdRH7.vm.provision "shell", :inline => "sudo echo '192.168.60.148 analyticsterminalRH7.local gocdRH7' >> /etc/hosts"

#   # Default 
#   # Main
#   gocdRH7.vm.provision "main", type: "ansible" do |ansible|
#     ansible.playbook = "deploy_gocdRH7.yml"
#     ansible.playbook = "deploy_gocdRH7Test.yml"
#     ansible.inventory_path = "vagrant_hosts"
#     #ansible.tags = ansible_tags
#     #ansible.verbose = ansible_verbosity
#     #ansible.extra_vars = ansible_extra_vars
#     #ansible.limit = ansible_limit
#   end
#   # Update
#   gocdRH7.vm.provision "update", type: "ansible" do |ansible|
#     ansible.playbook = "deploy_gocdPatchhRH7.yml"
#     ansible.inventory_path = "vagrant_hosts"
#     #ansible.tags = ansible_tags
#     #ansible.verbose = ansible_verbosity
#     #ansible.extra_vars = ansible_extra_vars
#     #ansible.limit = ansible_limit
#   end
# end
  ###########################
  ### PIPELINES COMPONENT ###
  ###########################

  config.vm.define :ci_server do |server|
#   server.vm.box = "bento/centos-6.10"
#   server.vm.box = "clouddood/RH7.5_baserepo"
    server.vm.box = "clouddood/RH7.9_infra"
    server.vm.host_name = "ci-server.test.dev"

    server.ssh.forward_agent = true

    server.vm.provision "ansible" do |ansible|
#     ansible.playbook = "deploy_gocd.yml"
      ansible.playbook = "deploy_gocdRH7_server_DEV.local.yml"
      ansible.inventory_path = "vagrant_hosts"
#     ansible.tags = ansible_tags
#     ansible.verbose = ansible_verbosity
#     ansible.extra_vars = ansible_extra_vars
#     ansible.limit = ansible_limit
    end

#   server.vm.network :private_network, ip: "10.0.1.26"
    server.vm.network :private_network, ip: "192.168.60.26"
  end

  config.vm.define :ci_agent_1 do |server|
#   server.vm.box = "bento/centos-6.10"
#   server.vm.box = "clouddood/RH7.5_baserepo"
    server.vm.box = "clouddood/RH7.9_infra"
    server.vm.host_name = "ci-agent-1.test.dev"

    server.ssh.forward_agent = true

    server.vm.provision "ansible" do |ansible|
#     ansible.playbook = "deploy_gocd.yml"
      ansible.playbook = "deploy_gocdRH7_agent_DEV.local.yml"
      ansible.inventory_path = "vagrant_hosts"
#     ansible.tags = ansible_tags
#     ansible.verbose = ansible_verbosity
#     ansible.extra_vars = ansible_extra_vars
#     ansible.limit = ansible_limit
    end

#   server.vm.network :private_network, ip: "10.0.1.27"
    server.vm.network :private_network, ip: "192.168.60.27"
  end

  config.vm.define :ci_agent_2 do |server|
#   server.vm.box = "bento/centos-6.10"
#   server.vm.box = "clouddood/RH7.5_baserepo"
    server.vm.box = "clouddood/RH7.9_infra"
    server.vm.host_name = "ci-agent-2.test.dev"

    server.ssh.forward_agent = true

    server.vm.provision "ansible" do |ansible|
#     ansible.playbook = "deploy_gocd.yml"
      ansible.playbook = "deploy_gocdRH7_agent_DEV.local.yml"
      ansible.inventory_path = "vagrant_hosts"
#     ansible.tags = ansible_tags
#     ansible.verbose = ansible_verbosity
#     ansible.extra_vars = ansible_extra_vars
#     ansible.limit = ansible_limit
    end

#   server.vm.network :private_network, ip: "10.0.1.28"
    server.vm.network :private_network, ip: "192.168.60.28"
  end

  config.vm.define :ci_agent_3 do |server|
#   server.vm.box = "bento/centos-6.10"
#   server.vm.box = "clouddood/RH7.5_baserepo"
    server.vm.box = "clouddood/RH7.9_infra"
    server.vm.host_name = "ci-agent-3.test.dev"

    server.ssh.forward_agent = true

    server.vm.provision "ansible" do |ansible|
#     ansible.playbook = "deploy_gocd.yml"
      ansible.playbook = "deploy_gocdRH7_agent_DEV.local.yml"
      ansible.inventory_path = "vagrant_hosts"
#     ansible.tags = ansible_tags
#     ansible.verbose = ansible_verbosity
#     ansible.extra_vars = ansible_extra_vars
#     ansible.limit = ansible_limit
    end

#   server.vm.network :private_network, ip: "10.0.1.29"
    server.vm.network :private_network, ip: "192.168.60.29"
  end

  config.vm.define :ci_terminal_1 do |server|
#   server.vm.box = "bento/centos-6.10"
#   server.vm.box = "clouddood/RH7.5_baserepo"
    server.vm.box = "clouddood/RH7.9_infra"
    server.vm.host_name = "ci-terminal-1.test.dev"

    server.ssh.forward_agent = true

    server.vm.provision "ansible" do |ansible|
      ansible.playbook = "deploy_gocd.yml"
      ansible.inventory_path = "vagrant_hosts"
#     ansible.tags = ansible_tags
#     ansible.verbose = ansible_verbosity
#     ansible.extra_vars = ansible_extra_vars
#     ansible.limit = ansible_limit
    end

#   server.vm.network :private_network, ip: "10.0.1.30"
    server.vm.network :private_network, ip: "192.168.60.30"
  end

#######################################################################################################################################

# config.trigger.before :destroy do |trigger|
#   run "rm -Rf /tmp/abc/*"
    # subscription-manager remove --all
    # subscription-manager unregister
    # subscription-manager clean
#   trigger.name = "Destroy Trigger ..."
#   trigger.info = "Destroy Trigger Execution ..."
#   trigger.run = { path: "subscription-manager remove --all"}
#   trigger.run = { path: "subscription-manager unregister"}
#   trigger.run = { path: "subscription-manager clean"}
# end
end


  ###########################
  ### PIPELINES COMPONENT ###
  ###########################

# config.vm.define :ci_server do |server|
#   server.vm.box = "bento/centos-6.10"
#   server.vm.host_name = "ci-server.test.dev"
#
#    server.ssh.forward_agent = true
#
#    server.vm.provision "ansible" do |ansible|
#      ansible.playbook = "deploy_gocd.yml"
#      ansible.inventory_path = "vagrant_hosts"
#      ansible.tags = ansible_tags
#      ansible.verbose = ansible_verbosity
#      ansible.extra_vars = ansible_extra_vars
#      ansible.limit = ansible_limit
#    end
#
#    server.vm.network :private_network, ip: "10.0.1.26"
#  end
#
#  config.vm.define :ci_agent_1 do |server|
#    server.vm.box = "bento/centos-6.10"
#    server.vm.host_name = "ci-agent-1.test.dev"
#
#    server.ssh.forward_agent = true
#
#    server.vm.provision "ansible" do |ansible|
#      ansible.playbook = "deploy_gocd.yml"
#      ansible.inventory_path = "vagrant_hosts"
#      ansible.tags = ansible_tags
#      ansible.verbose = ansible_verbosity
#      ansible.extra_vars = ansible_extra_vars
#      ansible.limit = ansible_limit
#    end
#
#    server.vm.network :private_network, ip: "10.0.1.27"
#  end
#
#  config.vm.define :ci_terminal_1 do |server|
#    server.vm.box = "bento/centos-6.10"
#    server.vm.host_name = "ci-terminal-1.test.dev"
#
#    server.ssh.forward_agent = true
#
#    server.vm.provision "ansible" do |ansible|
#      ansible.playbook = "deploy_gocd.yml"
#      ansible.inventory_path = "vagrant_hosts"
#      ansible.tags = ansible_tags
#      ansible.verbose = ansible_verbosity
#      ansible.extra_vars = ansible_extra_vars
#      ansible.limit = ansible_limit
#    end
#
#    server.vm.network :private_network, ip: "10.0.1.28"
#  end
