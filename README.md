The deployment procedure has been implemented with ansible and tested on Vagrant VM : ubuntu/xenial64
using VirtualBox as VM provider and MacOSX 10.10 as control host.

To implement B/G Deployment easy-deploy tool has been used. For more information : https://github.com/lazamar/easy-deploy

Both redis and mekkatorque instances have been dockerized. 

On main.yml you can find the vars declaration about paths, ports, app_version etc.

To deploy mekkatorque application you have to clone the deployment code, create an ansible inventory
that should contain the connection info of the target host and execute :

ansible-playbook -i <inventory_file> main.yml

I faced some issues with the application (I did not ask for an help as today is a holiday..), the most
significant was : npm ERR! 404 Not Found: event-stream@3.3.6
( https://stackoverflow.com/questions/53578201/npm-err-404-not-found-event-stream3-3-6 )

event-stream@3.3.6 seems to be marked as vulnerable so it has been depricated. I following the
instructions from the stackoverflow link I added and issue resolved. 

Regarding B/G Deployment, easy-deploy (based on nginx for proxying) automatically tags deployed containers
as blue or green to ensure high availability.
