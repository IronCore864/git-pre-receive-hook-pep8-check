# GitHub Pre-Receive Hook for PEP8 Environment

## Build

```
docker build -f Dockerfile.alpine-3.3 -t pre-receive.alpine-3.3 .
docker create --name pre-receive.alpine-3.3 pre-receive.alpine-3.3 /bin/true
docker export pre-receive.alpine-3.3 | gzip > alpine-3.3.tar.gz
```

## Upload

`scp -P 122 ./alpine-3.3.tar.gz admin@github.kigroup.de:~/`

## Create Env

`ghe-hook-env-create AlpineTestEnv ./alpine-3.3.tar.gz`

## More Info

See [HERE](https://help.github.com/enterprise/2.13/admin/guides/developer-workflow/creating-a-pre-receive-hook-environment/)

## Local Test

See [HERE](https://help.github.com/enterprise/2.13/admin/guides/developer-workflow/creating-a-pre-receive-hook-script/#testing-pre-receive-scripts-locally)
