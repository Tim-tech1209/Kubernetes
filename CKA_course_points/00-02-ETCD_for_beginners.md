## What is an ETCD?
It is a distributed reliable key-value store that is Simple, Secure and Fast.
## Tabular/relational DB
We have tabular/relational DB, like below.
| Name | Age | Location | Salary | Grade |
| :- | :- | :- | :- | :- |
| John Doe | 45 | New York | 5000 |  |
| Dave Smith | 34 | New York | 4000 ||
| Aryan Kumar | 10 | New York | | A |
| Lauren Rob | 13 | London | | B |
| Jiayin Yao | 15 | Shanghai | | B |

The roll represents each person, and the column represents the type of information being stored. Now, say we want to add an additional details about these indivisuals, for example, saraly. so we add an additional column. Doing so, it impacts the entire table and all of the individuals in them. However, not all of them are working, so those cells remain empty, where they requires grade information. So, we need to add new columns, and update these students with theie respective grades. Again, only students have grades. So the corresponding cells of adults is empty. Every time, a new information needs to be added, the entire table will be affected, and leads to a lot of empty cells.

## key-value store
A key-value store stores information in form of documents or pages, so each indivisual gets a document, and all information about that individual is stored in a file. These files can be in any format and structure. And change in one file doesn't affect the others.

| Key | Value |
| :- | :- |
| Name | John Snow |
| Age | 35 |
| Location | The Great Wall of Westeros |
| Affiliation | Night's Watch |

| Key | Value |
| :- | :- |
| Name | Shikinami Asuka Langley |
| Age | 14 |
| Location | The Great Wall of Westeros |
| Affiliation | NERV |
| Occupation | EVA Unit-02 Pilot |
| Nationality | German / American |
| Status | Active Pilot |

While you can store and retrieve keys and values. when your data get complex, you typically end up transacting in data format, like json or yaml.

## Install ETCD
* Download Binaries
```
curl -L https://github.com/etcd-io/etcd/releases/download/v3.3.11/etcd-v3.3.11-linux-amd64.tar.gz -o etcd-v3.3.11-linux-amd64.tar.gz
```
* Extract
```
tar xzvf etcd-v3.3.11-linux-amd64.tar.gz
```

* Run ETCD Service
```
./etcd
```
when you run ETCD, it starts a service that listen to **port 2379** by default. you can then attach any client to ETCD service to store and retrieve information.

## Commands used in ETCD
Commands when api version is 2 will be like below.
```
./etcdctl set key1 value1
./etcdctl get key1
./etcdctl
```
It is very important to confirm the version of etcdctl because the API version might be different.
```
./etcdctl version --version
etcd version: 3.3.11
API version:2
```
As you can see the stcd itself is version 3, but the API version is still 2.
With the release of **version 3.4** the default API version is set to 3. the subcommands between the two versions may be different.
#### you can change the API version by the command below.
```
ETCDCTL_API=3 ./etcdctl version
etcdstl version: 3.3.11
API version: 3.3
``` 
## ETCDCTL v3
```bash
$ export ETCDCTL_API=3
$ ./etcdctl version
```
```text
etcdctl version: 3.3.11
API version: 3.3
```
```bash
$ ./etcdctl put key1 value1
```
```text
OK
```
```bash
$ ./etcdctl get key1
```
```
key1
value1
```

