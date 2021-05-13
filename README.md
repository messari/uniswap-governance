## Uniswap Governance Subgraph

Uniswap Governance is governed over GovernorAlpha - a set of proposals and votes. This subgraph aggregates the proposals in an easy to consume way.

Subgraph quickstart docs: https://thegraph.com/docs/define-a-subgraph

(H/t) Compound Governance subgraph: https://github.com/protofire/compound-governance-subgraph

## Development

### Implementation

1. Follow these steps to setup `graph-cli`: https://thegraph.com/docs/define-a-subgraph

2. Define the events to listen to inside `subgraph.yaml`, see example [here](https://thegraph.com/docs/define-a-subgraph#the-subgraph-manifest)

3. Define the GraphQL Schema inside `schema.graphql`, note this is the crux of the abstraction here. See example [here](https://thegraph.com/docs/define-a-subgraph#defining-entities)

4. Run `yarn codegen` to generate the corresponding Contracts (defined in `subgraph.yaml`) and Entities (defined in `schema.graphql`) into the `/generated` folder

5. Implement `mapping.ts` which maps the Contract events to the corresponding Entities - this acts as a bridge between the two set of generated types.

### Deploy

1. Goto https://thegraph.com/, login and click on "Add Subgraph"

2. Follow https://thegraph.com/docs/deploy-a-subgraph#create-the-subgraph and input the corresponding info

3. Retrieve access token from the created empty subgraph page

4. Authenticate to this specific subgraph: `graph auth https://api.thegraph.com/deploy/ <ACCESS_TOKEN>`

5. Build: `yarn build`

6. Deploy: `yarn deploy`
