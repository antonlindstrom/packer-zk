# Example Packer Zookeeper instance

This is an example of a Zookeeper instance built by packer.

Note that this is a very simple install of ZK and it isn't started by default.
The instance should be managed by configuration management to do more advanced
stuff.

## Running

This section describes how to run this.

### EC2

Set environment variables for AWS:

    export AWS_ACCESS_KEY=myawskeyid
    export AWS_SECRET_KEY=myawsaccesskey

Build image on Amazon EC2:

    packer build -only=amazon-ebs zk.json

### VMWare

Build image for VMware Fusion:

    packer build -only=vwmare zk.json

### When the system is up

Run Zookeeper:

    cd zookeeper && bin/zkServer.sh start

Connect

    cd zookeeper && bin/zkCli.sh -server 127.0.0.1:2181 ls /
