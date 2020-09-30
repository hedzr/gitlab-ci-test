# gitlab-ci-test

This repo will show you how we synchronize it to multiple sites in one pushing.

Once pushed to our main site, .gitlab-ci.yml would be invoked by 
a gitlab-runner. In step `deploy`, the runner will fetch the whole 
repo and push all refs to other sites one by one.

## For lite-user

If you're like doing all push actions locally (without gitlab-runner and pipeline supports),
here is it:

```bash

git remote add all git@your-gitalb-server:owner/repo.git

git remote set-url --add --push all git@github.com:owner/repo.git
git remote set-url --add --push all git@gitlab.com:owner/repo.git
git remote set-url --add --push all git@gitee.com:owner/repo.git

git push all --all
git push all --tags

```

