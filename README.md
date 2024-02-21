# ansible_execution_environments

This repo contains execution and decision environment definitions and dependencies for the Ansible Automation Platform.

## Execution Environments

| Name | Description |
|-|-|
| k8s-ee | EE with suppport for Kubernetes and Openshift |
| wwt-de | Event-Driven Ansible DE with support for wwt.eda Collection |
| arista_netbox_ee | with eos and netbox collection and required python pkgs |

## Building an Execution Environment


1. Change into the directory of the EE you want to build

    ```shell
    cd <ee-directory>
    ```

2. Build the EE

    ```shell
    ansible-builder build --tag=<automation-hub-hostname>/<ee-name>
    ```

3. Log in to your automation hub instance

    ```shell
    podman login --tls-verify=false <automation-hub-hostname>
    ```

4. Push EE to your automation hub

    ```shell
    podman push --tls-verify=false <automation-hub-hostname>/<ee-name>
    ```

## Contributors

Bob Longmore
