# Ansible playbooks for Spark standalone cluster

Ansible playbooks for the deployment of an Spark standalone cluster.

## Usage

### Defining the inventory file

Create a new ansible inventory containing the IP addresses of the master and worker instances:

```{shell}
$ cat > hosts << EOL
[master]
<YOUR_MASTER_IP>

[worker]
<YOUR_WORKER_IP_1>
<YOUR_WORKER_IP_2>
<YOUR_WORKER_IP_3>
EOL
```

### Execute the playbooks

To setup the spark cluster, execute:

```{shell}
$ ansible-playbook -i hosts setup-cluster.yml'
```

To start the spark cluster, execute:

```{shell}
$ ansible-playbook -i hosts start-cluster.yml'
```

To stop the spark cluster, execute:

```{shell}
$ ansible-playbook -i hosts stop-cluster.yml'
```

### Configuring the deployment

| Variable | Description | Default value |
|:---------|:------------|:--------------|
| spark_version | | 3.1.1 |
| spark_hadoop_version | | 3.2 |
| spark_force_install | | false |
| spark_install_dir | | /opt/spark |
| spark_eventlog_dir | | file:/tmp/spark-events |
| spark_history_port | | 18080 |
| spark_user_name | | spark |
| spark_user_group | | spark |
| java_openjdk_version | Version of OpenJDK to be installed | 11 |
| java_home | Home of OpenJDK installation | /etc/alternatives/jre_openjdk |