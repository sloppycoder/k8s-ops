
### install Flux components

```
export GITHUB_TOKEN=ghp_cblah

# create a new repo
flux bootstrap github \
  --owner=owner \
  --repository=this_repo \
  --path=clusters/cluster \
  --branch master \
  --personal

# use an existing repo
flux bootstrap git \
  --url=<git_repo_url>
  --branch=master
  --path=cluster/<cluster>

```
