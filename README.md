# rabbitmqmanagement
RabbitMQ management related tools/scripts

PS> . .\rabbitmq-management.ps1
DeleteAllQueues -serverUrl "https://local.rabbitmq.com" -port 443 -userName "user" -password "password" -vhost "myvhost"

You can call DeleteAllQueues without any arguments and in this case it defaults to server being 'localhost', port being '15672', username being 'guest', password being 'guest' and vhost being '/'.

Note that RabbitMQ management plugin needs to be configured on the Rabbit server for this to work. 

It uses EasyNetQ Management plugin under the hood.
https://github.com/EasyNetQ/EasyNetQ.Management.Client

