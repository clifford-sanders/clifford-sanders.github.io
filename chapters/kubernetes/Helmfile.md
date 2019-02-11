# Helmfile

## Best Practices

[YouTube - Effortless Helm Chart Deployments][1]

* Use `helmfile.d/` directory to decompose helmfiles for maintainability
* Use prefixes for lexicographical  execution (e.g. 0100.ingress.yaml)
* Use GitHub [`CODEOWNERS`][2]
* Use lots of labels (great for `--selectors`)
* Use inline `values.yaml` (not `set`)
* Use `wait: true` to block until rollout complete (fail fast)

[1]:https://www.youtube.com/watch?v=WPflHwbZgHM
[2]:https://help.github.com/articles/about-code-owners/