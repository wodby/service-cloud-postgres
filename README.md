# Cloud PostgreSQL service for Kubernetes on Wodby

Connect Wodby Kubernetes applications to an externally managed Cloud PostgreSQL
service.

This repository defines the Wodby service manifests and operational
configuration for Cloud PostgreSQL.

- [Browse Wodby services](https://wodby.com/services)
- [Wodby service documentation](https://wodby.com/docs/2.0/services/)
- [Service manifest reference](https://wodby.com/docs/2.0/services/template/)

## Wodby stacks using this service

- [Cloud PostgreSQL application stack](https://github.com/wodby/stack-cloud-postgres)
- [Django application stack](https://github.com/wodby/stack-django)
- [FastAPI application stack](https://github.com/wodby/stack-fastapi)
- [Flask application stack](https://github.com/wodby/stack-flask)
- [Go application stack](https://github.com/wodby/stack-go)
- [Node.js application stack](https://github.com/wodby/stack-node)
- [Python application stack](https://github.com/wodby/stack-python)
- [Rails application stack](https://github.com/wodby/stack-rails)
- [Ruby application stack](https://github.com/wodby/stack-ruby)

## Service overview

| Property | Manifest configuration |
| --- | --- |
| Service name | `cloud-postgres` |
| Type | Database; external connection with no in-cluster workload |
| Versions | `13` by default; also available: `12`, `11`, `10`, `9.6` |
| Configuration | 1 generated or fixed tokens |

## Use this service

Use this service through one of the Wodby application stacks listed above, or
reference `cloud-postgres` from a custom Wodby stack.

A service is a reusable component and does not deploy by itself. The stack
defines its links, settings, versions, resources, and relationship to the rest
of the application.

## Maintain a custom version

1. Fork this repository.
2. Edit the service manifest and referenced files.
3. Import the repository as a [Git-backed service](https://wodby.com/docs/2.0/services/create/#create-a-git-backed-service).
4. Reference the service from a stack manifest.

Keep service, workload, container, endpoint, link, volume, config, and
derivative names stable unless dependent stacks and app-level overrides are
updated at the same time.

Validate the manifests with:

```bash
wodby service validate-manifest service.yml --org <org-id>
```

See the [service manifest reference](https://wodby.com/docs/2.0/services/template/) and the [managed services index](https://github.com/wodby/services).
