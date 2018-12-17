# Blockchain Explorer for Quorum and Ethereum

![alt text](https://raw.githubusercontent.com/blk-io/blk-explorer-free/master/docs/source/ExplorerCaption.png "Blk-Explorer-Free")


## Introduction

This dockerized environment is designed for viewing private 
[Quorum](https://github.com/jpmorganchase/quorum) and [Ethereum](https://github.com/ethereum/go-ethereum) networks.

## Usage

Clone the repo, navigate to the cloned directory and run the instance with:
Make sure not to enter the port number, changed docker-compose to accept only IP address
```bash
NODE_ENDPOINT=http://<node_endpoint> docker-compose up
NODE_ENDPOINT=http://13.57.239.260 docker-compose up

```
Append the `-d` argument to run the containers in the backgroud

You will be able to access the Explorer UI via:

* http://localhost:5000

To stop the containers use:

```bash
docker-compose down
```

To connect to new network you need to delete one of the containers with:

```bash
docker rm blk-mongodb-free
```
 
### Local Quorum Networks

If you need to run a Quorum network locally, we recommend you use the following [4-node Quorum Docker image](https://github.com/blk-io/crux#4-node-quorum-network-with-crux), you can then start the Explorer via:

```bash
NODE_ENDPOINT=http://localhost:22001 docker-compose up
```

Alternatively there is a Vagrant version available [here](https://github.com/blk-io/quorum-examples).

## Limitations

 - Due to a [limitation](https://github.com/moby/moby/issues/1143) with Docker, you may only have one instance of the Explorer running at a time.
