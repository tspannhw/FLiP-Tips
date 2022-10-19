# FLiP-Tips


#### delete a topic

````

deletetopic.sh
# persistent://public/default/electric

echo "Delete topic $1"
bin/pulsar-admin schemas delete "$1"
bin/pulsar-admin topics delete "$1" --force
bin/pulsar-admin topics unload "$1"

bin/pulsar-admin schemas delete "$1-partition-0"
bin/pulsar-admin topics delete "$1-partition-0" --force
bin/pulsar-admin topics unload "$1-partition-0"

````
