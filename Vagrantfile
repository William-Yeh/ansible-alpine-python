Vagrant.configure(2) do |config|

    # main & default: normal OS series...
    config.vm.define "main", primary: true do |node|
        node.vm.box = "maier/alpine-3.4-x86_64"
        #node.vm.box = "maier/alpine-3.3.1-x86_64"

        node.vm.synced_folder '.', '/vagrant', disabled: true

        node.vm.provision "ansible" do |ansible|
            ansible.playbook = "test.yml"
            ansible.verbose = "vvv"
            ansible.extra_vars = { alpine_python_fix_repo: true }
        end
    end


    # docker: for auto build & testing (e.g., Travis CI)
    config.vm.define "docker" do |node|
        node.vm.box = "williamyeh/ubuntu-trusty64-docker"

        node.vm.provision "shell", inline: <<-SHELL
            cd /vagrant
            docker build  -f test/Dockerfile  -t alpine_python   .
        SHELL
    end

end
