# Hedera Subgraph Example Project

The Hedera Subgraph Example Project demonstrates how to create and deploy a subgraph to a local graph node using The Graph Protocol. Based on the [Hedera Hardhat Example Project Repo](https://github.com/hashgraph/hedera-hardhat-example-project). For more information about subgraphs, check out The Graph Protocol documentation [here](https://thegraph.com/docs). 

> :fire: Check out the step-by-step tutorial [here](https://docs.hedera.com/hedera/tutorials/smart-contracts/deploy-a-subgraph-using-the-graph).

## Project Files and Folders

- `docker.compose.yaml` - The configuration file that's used by Docker Compose to define and run containers that make up your local graph node. This file specifies settings, including container images, environment variables, and network configuration.

- `subgraph.yaml` - The Graph configuration file to specify the schema and data that the subgraph indexes and makes available for querying. 

- `schema.graphql` - The GraphQL schema for the subgrapg, defining the types of data that can be queried, relationship between entities, and specifies the fields that can be queried.

- `mappings.ts` - The file that contains the mapping function that translates the events emitted by your smart contract into GraphQL entities that the subgraph can index.

- `/generated` - The auto-generated folder by The Graph's CLI tooling and contains JSON ABIs, a GraphQL schema, and TypeScript and AssemblyScript types used to interface with your smart contract and subgraph.

## Setup

1. Clone this repo to your local machine:

```shell
git clone https://github.com/hashgraph/hedera-subgraph-example.git
```

2. Once you've cloned the repository, open your IDE terminal and navigate to the root directory of the project and change directories:

```shell
cd hedera-subgraph-example
```

3. Once you've cloned the repository, open your IDE terminal and navigate to the root directory of your project. Run the following command to install all the necessary dependencies:

```shell
npm install
```

4. Rename the `subgraph.template.yaml` file to `subgraph.yaml`.

5. Add the deployed Greeter contract address to the `address` property and the start block number to the `startBlock` property in the `subgraph.yaml` file.

6. Add the Hashio Testnet API endpoint URL to the `ethereum` field under the `environment` object inside the `docker-compose.yaml` file.

7. Start the local graph node:

```shell
npm run graph-node
```

8. Generate the AssemblyScript types:

```shell
npm run graph-codegen
```

9. Create the subgraph: 

```shell
npm run create-local
```

10. Deploy the subgraph:

```
npm run deploy-local
```
Once the node finishes indexing, you will be able to access the GraphQL API at: http://localhost:8000/subgraphs/name/Greeter

# Contributing
Contributions are welcome. Please see the
[contributing guide](https://github.com/hashgraph/.github/blob/main/CONTRIBUTING.md)
to see how you can get involved.

# Code of Conduct
This project is governed by the
[Contributor Covenant Code of Conduct](https://github.com/hashgraph/.github/blob/main/CODE_OF_CONDUCT.md). By
participating, you are expected to uphold this code of conduct. Please report unacceptable behavior
to [oss@hedera.com](mailto:oss@hedera.com).

# License
[Apache License 2.0](LICENSE)
