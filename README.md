# lizard-build/build-push-action

A drop-in replacement for [`docker/build-push-action`](https://github.com/docker/build-push-action) that builds and pushes images with Docker's layer cache on
[Lizard](https://lizard.build) GitHub Actions runners (`runs-on: lizard-<n>vcpu-ubuntu-2404`).

```yaml
- uses: lizard-build/build-push-action@v1
```

On a Lizard runner the build uses the runner's own Docker, whose layers stay on the repository's cache
disk between runs (private repositories). On any other runner it runs `docker/build-push-action` unchanged, with the same
inputs and outputs, so a workflow works on both.
