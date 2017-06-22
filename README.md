# RabbmitMQ Management PowerShell Script
RabbitMQ management related tools/scripts

### Delete all queues
PS> . .\rabbitmq-management.ps1
PS>DeleteAllQueues -serverUrl "https://local.rabbitmq.com" -port 443 -userName "user" -password "password" -vhost "myvhost"

You can call DeleteAllQueues without any arguments and in this case it defaults to server being 'localhost', port being '15672', username being 'guest', password being 'guest' and vhost being '/'.

### Export all queues matching given name and their consumers count to csv
PS> . .\rabbitmq-management.ps1
GetQueuesConsumersCount -match "MyApp*" |  Export-Csv C:\queueinfo.csv -NoTypeInformation

Note that RabbitMQ management plugin needs to be configured on the Rabbit server for this to work. 

More functions will be added using this same pattern.

It uses EasyNetQ Management plugin under the hood.
https://github.com/EasyNetQ/EasyNetQ.Management.Client

