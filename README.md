# renovate-example
reproduction repo for discussion issue https://github.com/renovatebot/renovate/discussions/16176

This is an example repo to reproduce the following issue:  

As you can see the docker-compose.yml file has two dc services pointing to the same docker image with the same version (though the current versions can be different).
Because it is the same file and the same docker image (dependency), Renovate tries to update both images together in the same PR.

I, however, would like those two changes to be in two separate PRs.
The reason for that as you might be able to tell from the dc services names), one service is an "early adaptor" so I'd like it to have the newest version
as quickly as possible. The other service, will eventually be updated as well, but I don't wish for it to happen at the same time.
I'm aware that I could separate thos services into different files but I prefer to keep one file.

I was wondering if there is a way to separate those two updates into separate PRs, however I couldn't find a criteria for putting them in a different group.
I was thinking that if there was an option to group by service name (in the docker compose case) or by matchString for the regular expression case, then that could be a good criteria.

I hope this is helpful.
Thanks!
