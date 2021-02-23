[![peribolos-sync-status](https://img.shields.io/travis/com/baloise-incubator/org/master?label=peribolos%20sync "periblos sync status")](https://travis-ci.com/github/baloise-incubator/org)

# org

We are using [Peribolos](https://github.com/kubernetes/test-infra/tree/master/prow/cmd/peribolos) to manage our GitHub org settings, teams and memberships in a [yaml file](config.yaml).

## Automation

*peribolos* runs on every push to master and every PR to master (dry-run).

## Initial Config Dump

```bash
docker run --rm -v ~/peribolos-github-token:/etc/github/oauth gcr.io/k8s-prow/peribolos:latest \
  --dump baloise-incubator \
  --dump-full \
  --github-token-path /etc/github/oauth \
  > config.yaml 
```

## Peribolos Help

```bash
docker run --rm gcr.io/k8s-prow/peribolos:latest --help
```
