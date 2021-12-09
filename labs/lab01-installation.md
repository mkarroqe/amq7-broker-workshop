# Lab 1. Installation

## Installation
1. Download zip file from Red Hat Customer Portal here: [Red Hat AMQ Broker 7.8.0](https://developers.redhat.com/download-manager/file/amq-broker-7.8.0-bin.zip)

   > You will need to login into the portal using your Red Hat developer or customer account.

2. Install the software by unzipping the file into the designated workshop path (`$HOME/workshop-amq`)

   ```sh
   $ unzip amq-broker-[version]-bin.zip
   ```

   > The directory created by extracting the archive will be referenced now on as **AMQ_HOME**

## Directory Structure

```sh
$ tree -L 1
|-- bin
|-- etc
|-- examples
|-- lib
|-- schema
└-- web
```

| Folder | Description |
| ------ | ----------- |
| `bin`    | AMQ scripts and native journal lib |
| `etc`    | Red Hat branding and extra configuration |
| `examples` | Full set of runnable JMS and Java EE examples |
| `lib`    | The AMQ 7 runtime jars and libraries |
| `schema` | XML Schema to validate the AMQ configuration files |
| `web`    | Web loaded with hawt.io console, jolokia |

End of Lab 1.
