# vagrant_master_slaves_configuration_debian
Vagrantfile for master and worker nodes cluster

1. Download box for virtualbox [here](https://app.vagrantup.com/bento/boxes/debian-11).
2. Create project folder

``mkdir vagrant_debian``

3. Move downloaded box to folder with name "debian":

``mv a22d1053-8311-450b-a740-6e3017c087f8 vagrant_debian/debian``

4. Add box to vagrant configuratiuons:

``cd vagrant_debian && vagrant box add bento/debian-11 debian``

5. Initializate vagrant configuration:

``vagrant init -m bento/debian-11 debian``

6. Run project:

``vagrant up --provider=virtualbox``
