![[Pasted image 20240315102540.png]]
==Dev== 
Filebeat: Push logs to logstash
==Server==
Logstash: Parser logs
Elastic: Index, query 
Kibana: Visualize
## filebeat
Put filebeat folder on dev's computer. 
```yml
volumes:

- ./kis_server:/usr/share/filebeat/mylog

- ./filebeat.yml:/usr/share/filebeat/filebeat.yml
```
mount your log folder (./kis_server) and config for filebeat (filebeat.yml) reponsively to the position in filebeat container
```
--strict.perms=false //Disable strict permissions in Filebeat
```

### filebeat.yml
```yml
multiline.type: pattern
multiline.pattern: '((^\[)|(\*+.*System Startup.*\*+))|\*+.*New File.*\*+'
multiline.negate: true
multiline.match: after
```

Change the index name 
![[Pasted image 20240315145211.png]]
Send pattern after matching:
```
1. [
2.
***********************************************

****************** New File *****************

***********************************************
3. 
***********************************************

************** System Startup ***************

***********************************************
```
![[Pasted image 20240315110509.png]]
## ELK 
will save on server machine for other devs can use
### ecs-v1 folder
grok-patterns: have common patterns which already defined
I put it here to add some customize patterns:
```
# Log Levels
LOGLEVEL (INF|MSG|SQL|WRN|ERR)

#Customize
LOGINFO \[%{LOGLEVEL:loglevel} %{DATA:thread},%{MONTHNUM:month}-%{MONTHDAY:day} %{TIME:time}\]

NEWFILE \*+.*New File.*\*+
SYSTEM_STARTUP \*+.*System Startup.*\*+
```
Grok Debugger: https://grokdebugger.com/ 

-----------------------------------------------------------------------------------
# SET UP
Run below command in seperate terminal:
```
docker compose up elasticsearch
docker compose up kibana
```

Access http://localhost:5601?code=[code]
![[Pasted image 20240315133741.png]]

![[Pasted image 20240315134715.png]]

--------------------------------------------------------------------------
Open a new terminal, run the command: 
==docker exec -it \<elasticsearch-container-id> /bin/bash==
and then
==bin/elasticsearch-create-enrollment-token --scope kibana==
You will receive below token: 
![[Pasted image 20240315135257.png]]

==bin/elasticsearch-setup-passwords interactive==
![[Pasted image 20240315140157.png]]
set one password "youpassword" for all above

-----------------------------------------------------------------------------------

Back to the kibana UI, put the token above into and choose ==Configure Elastic==

![[Pasted image 20240315135516.png]]


After login, now you can start logstash
==docker compose up logstash==
and then start filebeat
==docker compose up filebeat==
------------------------------------------------------------------------------------------------------------
# HOW TO USE
![[Pasted image 20240315141904.png]]Create data view
![[Pasted image 20240315141958.png]]
Choose Save data view to Kibana
Watch this video to know how to discover with data view: https://www.youtube.com/watch?v=I8NtctS33F0
![[Pasted image 20240315142527.png]]

QueryBuilder: https://www.supermind.org/elasticsearch/query-dsl-builder.html
