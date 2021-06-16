# [Containerize SuiteCloud CLI for Node.js](https://hub.docker.com/r/skumail/suitecloud-cli)

SuiteCloud Command Line Interface (CLI) for Node.js is a SuiteCloud SDK tool to manage SuiteCloud project components and validate and deploy projects to your account. CLI for Node.js is an interactive tool that guides you through all the steps of the communication between your local project and your account.

For CLI usage visit Oracle NetSuite official [npm package](https://www.npmjs.com/package/@oracle/suitecloud-cli).

## docker usage
You don't need to have node and JDK  installed on your system in order to use suitecloud-cli.

```shell
docker run \
       --rm -it \
       -v $(pwd):/usr/src/app \
       skumail/suitecloud-cli
```

`--rm` removes the container after running, `-it` makes it interactive, `-v $(pwd):/usr/src/app` mounts current directory inside the container. If you want to store the config in another place, mount another directory: 
 
 ```shell
 docker run \
        --rm -it \
        skumail/suitecloud-cli
 ```

... or use a Docker volume **(Highly Recommended)**:

```shell
docker volume create suitecloud-cli-config

docker run \
       --rm -it \
       -v suitecloud-cli-config:/home/node/.suitecloud-sdk \
       -v $(pwd):/usr/src/app \
       skumail/suitecloud-cli
```

## CLI Examples 
### project:create
Creates a SuiteCloud project, either a SuiteApp or an account customization project.
```shell
docker run \
       --rm -it \
       -v suitecloud-cli-config:/home/node/.suitecloud-sdk \
       -v $(pwd):/usr/src/app \
       skumail/suitecloud-cli \
       project:create -i
```
### account:setup
Sets up an account to use with the SuiteCloud CLI for Node.js.
```shell
docker run \
       --rm -it \
       -v suitecloud-cli-config:/home/node/.suitecloud-sdk \
       -v $(pwd):/usr/src/app \
       skumail/suitecloud-cli \
       account:setup -i
```

### project:deploy
Deploys the folder containing the project.
```shell
docker run \
       --rm -it \
       -v suitecloud-cli-config:/home/node/.suitecloud-sdk \
       -v $(pwd):/usr/src/app \
       skumail/suitecloud-cli \
       project:deploy -i
```

## docker-compose Examples
Put docker-compose.yml in our existing project. By using docker-compose you do not need to specify the volumes in run command.
### run
```shell
docker-compose run \
       --rm \
       suitecloud-cli \
       project:create -i
```