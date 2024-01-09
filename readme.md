# VMAgent Operator Preconfigured for Levitate

## Installation

### Step 1: Prerequisites

Make sure you have the following prerequisites installed:

- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) - Kubernetes command-line tool.
- Clone this repository to your local machine:

    ```bash
    git clone https://github.com/last9/vmagent-operator-levitate.git
    cd vmagent-operator-levitate
    ```

### Step 2: Install Custom Resource Definitions (CRDs)

- Navigate to the `crds/` directory:

    ```bash
    cd ./crds/
    ```
- Check [readme.md](crds%2Freadme.md)

### Step 3: Install VM Operator

- Navigate to the `operator/` directory:

    ```bash
    cd ./operator/
    ```
- Check [readme.md](operator%2Freadme.md)

### Step 4: Install VMAgent

- Navigate to the `vmagent/` directory:

    ```bash
    cd ./vmagent/
    ```
- Check [readme.md](vmagent%2Freadme.md)

### Step 5: Install VMServiceScrape (i.e ServiceMonitor and PodMonitor)

- Navigate to the `vmservicescrape/` directory:

    ```bash
    cd ./vmservicescrape/
    ```
- Check [readme.md](vmservicescrape%2Freadme.md)

## Troubleshooting

Feel free to contact us through your preferred communication channels, or hop on
our [Discord](https://discord.gg/c3djBahzrh) and give us a ping.

We will certainly assist you.

## Contributions

We welcome and appreciate contributions from the community!

## Reporting Issues

If you encounter any issues or have suggestions for improvements, please submit an issue on the repository. Provide a
clear and detailed description, including steps to reproduce, if applicable.
