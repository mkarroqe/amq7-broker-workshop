# Lab 2. Creating a Broker Instance

The `artemis` script located in the `bin` folder is the starting point to manage our AMQ installation.

## Use the script to create a new broker instance

1. Create the `instances/mybroker` directory within `<AMQ_HOME>`.

   ```sh
   $ mkdir -p instances/mybroker/
   ```

3. Execute the following command to create a new broker in the instances folder.

   ```sh
   $ <AMQ_HOME>/bin/artemis create <AMQ_HOME>/instances/mybroker/
   ```

1. The command will ask a series of questions in order to configure the broker instance:

   * Use `admin` as username and password for the mandatory user
   * Add the `admin` role to the admin user
   * Allow anonymous access by typing `Y` when asked
   
   <br/>
   
   > As the AMQ Broker requires to persist messages, we need to have enough free space in the disk to store the messages, please check that there is at least 10% available.

## Directory Structure

```sh
$ cd instances/mybroker
$ tree -L 1
|-- bin
|-- data
|-- etc
|-- log
└-- tmp
```

| Folder | Description |
| ------ | ----------- |
| `bin`    | AMQ instance command line scripts to launch and manage |
| `etc`    | Broker instance configuration files |
| `lib`    | Extra libraries                                        |
| `log`    | Instance log files |
| `data`   | Journal files storage for persistent messages          |
| `tmp` | Temporary files |

End of Lab 2.
