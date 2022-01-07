[comment]: # "Auto-generated SOAR connector documentation"
# NGINX

Publisher: Splunk  
Connector Version: 2\.0\.2  
Product Vendor: F5  
Product Name: NGINX  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 4\.9\.39220  

This app integrates with an NGINX instance to manage upstreams and servers

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a NGINX asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**base\_url** |  optional  | string | Base URL of NGINX Instance \(Required for test connectivity\)
**verify\_server\_cert** |  optional  | boolean | Verify server certificate
**username** |  required  | string | NGINX Username
**password** |  required  | password | NGINX Password

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[remove server](#action-remove-server) - Remove a server from an upstream  
[add server](#action-add-server) - Add a server to an upstream  
[disable server](#action-disable-server) - Disable a server  
[enable server](#action-enable-server) - Enable a server  
[describe server](#action-describe-server) - Get information about an upstream server  
[list servers](#action-list-servers) - List servers under an upstream  
[list upstreams](#action-list-upstreams) - List all configured upstreams  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'remove server'
Remove a server from an upstream

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  optional  | URL of NGINX instance | string |  `url` 
**upstream\_name** |  required  | Name of the upstream | string |  `nginx upstream name` 
**server\_id** |  required  | ID of the server to remove | numeric |  `nginx server id` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.server\_id | numeric |  `nginx server id` 
action\_result\.parameter\.upstream\_name | string |  `nginx upstream name` 
action\_result\.parameter\.url | string |  `url` 
action\_result\.data | string | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'add server'
Add a server to an upstream

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  optional  | URL of NGINX instance | string |  `url` 
**upstream\_name** |  required  | Name of the upstream | string |  `nginx upstream name` 
**ip** |  required  | IP of the server to add | string |  `ip` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.ip | string |  `ip` 
action\_result\.parameter\.upstream\_name | string |  `nginx upstream name` 
action\_result\.parameter\.url | string |  `url` 
action\_result\.data\.\*\.backup | boolean | 
action\_result\.data\.\*\.down | boolean | 
action\_result\.data\.\*\.fail\_timeout | string | 
action\_result\.data\.\*\.id | numeric |  `nginx server id` 
action\_result\.data\.\*\.max\_conns | numeric | 
action\_result\.data\.\*\.max\_fails | numeric | 
action\_result\.data\.\*\.route | string | 
action\_result\.data\.\*\.server | string | 
action\_result\.data\.\*\.slow\_start | string | 
action\_result\.data\.\*\.weight | numeric | 
action\_result\.summary\.server\_id | numeric |  `nginx server id` 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'disable server'
Disable a server

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  optional  | URL of NGINX instance | string |  `url` 
**upstream\_name** |  required  | Name of the upstream containing the server | string |  `nginx upstream name` 
**server\_id** |  required  | ID of the server to disable | string |  `nginx server id` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.server\_id | string |  `nginx server id` 
action\_result\.parameter\.upstream\_name | string |  `nginx upstream name` 
action\_result\.parameter\.url | string |  `url` 
action\_result\.data\.\*\.backup | boolean | 
action\_result\.data\.\*\.down | boolean | 
action\_result\.data\.\*\.fail\_timeout | string | 
action\_result\.data\.\*\.id | numeric |  `nginx server id` 
action\_result\.data\.\*\.max\_conns | numeric | 
action\_result\.data\.\*\.max\_fails | numeric | 
action\_result\.data\.\*\.route | string | 
action\_result\.data\.\*\.server | string | 
action\_result\.data\.\*\.slow\_start | string | 
action\_result\.data\.\*\.weight | numeric | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'enable server'
Enable a server

Type: **correct**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  optional  | URL of NGINX instance | string |  `url` 
**upstream\_name** |  required  | Name of the upstream containing the server | string |  `nginx upstream name` 
**server\_id** |  required  | ID of the server to enable | string |  `nginx server id` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.server\_id | string |  `nginx server id` 
action\_result\.parameter\.upstream\_name | string |  `nginx upstream name` 
action\_result\.parameter\.url | string |  `url` 
action\_result\.data\.\*\.backup | boolean | 
action\_result\.data\.\*\.down | boolean | 
action\_result\.data\.\*\.fail\_timeout | string | 
action\_result\.data\.\*\.id | numeric |  `nginx server id` 
action\_result\.data\.\*\.max\_conns | numeric | 
action\_result\.data\.\*\.max\_fails | numeric | 
action\_result\.data\.\*\.route | string | 
action\_result\.data\.\*\.server | string | 
action\_result\.data\.\*\.slow\_start | string | 
action\_result\.data\.\*\.weight | numeric | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'describe server'
Get information about an upstream server

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  optional  | URL of NGINX instance | string |  `url` 
**upstream\_name** |  required  | Name of the upstream containing the server | string |  `nginx upstream name` 
**server\_id** |  required  | ID of the server to describe | string |  `nginx server id` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.server\_id | string |  `nginx server id` 
action\_result\.parameter\.upstream\_name | string |  `nginx upstream name` 
action\_result\.parameter\.url | string |  `url` 
action\_result\.data\.\*\.backup | boolean | 
action\_result\.data\.\*\.down | boolean | 
action\_result\.data\.\*\.fail\_timeout | string | 
action\_result\.data\.\*\.id | numeric |  `nginx server id` 
action\_result\.data\.\*\.max\_conns | numeric | 
action\_result\.data\.\*\.max\_fails | numeric | 
action\_result\.data\.\*\.route | string | 
action\_result\.data\.\*\.server | string | 
action\_result\.data\.\*\.slow\_start | string | 
action\_result\.data\.\*\.weight | numeric | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'list servers'
List servers under an upstream

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  optional  | URL of NGINX instance | string |  `url` 
**upstream\_name** |  required  | Name of upstream | string |  `nginx upstream name` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.upstream\_name | string |  `nginx upstream name` 
action\_result\.parameter\.url | string |  `url` 
action\_result\.data\.\*\.active | numeric | 
action\_result\.data\.\*\.backup | boolean | 
action\_result\.data\.\*\.downstart | string | 
action\_result\.data\.\*\.downtime | numeric | 
action\_result\.data\.\*\.fails | numeric | 
action\_result\.data\.\*\.header\_time | numeric | 
action\_result\.data\.\*\.health\_checks\.checks | numeric | 
action\_result\.data\.\*\.health\_checks\.fails | numeric | 
action\_result\.data\.\*\.health\_checks\.last\_passed | boolean | 
action\_result\.data\.\*\.health\_checks\.unhealthy | numeric | 
action\_result\.data\.\*\.id | numeric |  `nginx server id` 
action\_result\.data\.\*\.name | string |  `nginx server name` 
action\_result\.data\.\*\.received | numeric | 
action\_result\.data\.\*\.requests | numeric | 
action\_result\.data\.\*\.response\_time | numeric | 
action\_result\.data\.\*\.responses\.1xx | numeric | 
action\_result\.data\.\*\.responses\.2xx | numeric | 
action\_result\.data\.\*\.responses\.3xx | numeric | 
action\_result\.data\.\*\.responses\.4xx | numeric | 
action\_result\.data\.\*\.responses\.5xx | numeric | 
action\_result\.data\.\*\.responses\.total | numeric | 
action\_result\.data\.\*\.selected | string | 
action\_result\.data\.\*\.sent | numeric | 
action\_result\.data\.\*\.server | string | 
action\_result\.data\.\*\.state | string | 
action\_result\.data\.\*\.unavail | numeric | 
action\_result\.data\.\*\.weight | numeric | 
action\_result\.summary\.num\_servers | numeric | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'list upstreams'
List all configured upstreams

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  optional  | URL of NGINX instance | string |  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.url | string |  `url` 
action\_result\.data\.\*\.keepalive | numeric | 
action\_result\.data\.\*\.zombies | numeric | 
action\_result\.data\.\*\.zone | string |  `nginx upstream name` 
action\_result\.summary\.num\_upstreams | numeric | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 