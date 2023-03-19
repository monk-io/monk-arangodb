# Arango DB & Monk

This repository contains Monk.io template to deploy Arango DB either locally or on cloud of your choice (AWS, GCP, Azure, Digital Ocean).

## Prerequisites

- [Install Monk](https://docs.monk.io/docs/get-monk)
- [Register and Login Monk](https://docs.monk.io/docs/acc-and-auth)
- [Add Cloud Provider](https://docs.monk.io/docs/cloud-provider)
- [Add Instance](https://docs.monk.io/docs/multi-cloud)

## Make sure monkd is running

```bash
foo@bar:~$ monk status
daemon: ready
auth: logged in
not connected to cluster
```

## Clone Repository

```bash
git clone https://github.com/monk-io/monk-arangodb
```

## Load Template

```bash
cd monk-arangodb
monk load MANIFEST
```

## Let's take a look at the themes I have installed

```bash
foo@bar:~$ monk list arangodb
✔ Got the list
Type      Template  Repository  Version  Tags
runnable  arangodb/db  local       -        -
```

## Deploy Stack

```bash
foo@bar:~$ monk run arangodb/db
```

## Variables

| Variable      | Description          | Default                      |
|---------------|----------------------|------------------------------|
| db_port       | Arango database port | 7687                         |
| image         | Docker image tag     | latest                       |
| volume_local  | Volume path          | ${monk-volume-path}/arangodb |
| root_password | Root password        | monk                         |

## Stop, remove and clean up workloads and templates

```bash
monk purge -a
```
