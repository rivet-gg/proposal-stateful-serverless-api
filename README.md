# Stateful Serverless API Proposal

This repository contains a proposal for a Stateful Serverless API specification.

This specification will need to be rewritten in a more official format. Its current form is temporary.

## Relevant Runtimes

- [Cloudflare Durable Objects](https://developers.cloudflare.com/durable-objects/)
- [Rivet Actors](https://rivet.gg/docs)
- [ActorCore](https://actorcore.org/introduction)
- [Agents](https://developers.cloudflare.com/agents/)

_If you wish to participate, add your runtime here_

## W3C & WinterTC

The end goal is for this proposal to become part of W3C or WinterTC. If you are familiar with this process, please reach out on [X](https://x.com/NathanFlurry) or [LinkedIn](https://www.linkedin.com/in/nathanflurry/) with next steps.

This repository is not intended to remain part of the `rivet-gg` org.

## More Thought Required

### Data Migrations

WinterTC is great specification for stateless serverless since migrating providers is as simple as updating a DNS record.

However, stateful serverless is significantly different since **this spec is effectively defining a database**, since `ServerlessWorker`s have persistent storage. 

If the whole point of defining a common specification for stateful serverless is to encourage companies to adopt new technologies, then they'll also need assurances on their ability to migrate between providers. For example, Postgres provides the ability to use <Link href="https://www.postgresql.org/docs/current/logical-replication.html" target="_blank">logical replication</Link> for live migrations and is used frequently.

### Storage

The storage is the most rough section of this spec. It probably justifies its own spec.

### Connection Interruptions

`SharedWorker` connections cannot be interrupted. Can `ServerlessWorker` connections be interrupted? What happens if they are?

