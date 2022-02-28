# notifications-dependancies-dependabot
notify spike testing dependabot config


thoughts:

security warnings show up in top bar which is nice (https://github.com/alphagov/notifications-dependancies-dependabot/security/dependabot). this can be enabled separately to the dependency PRs, and is a one-click no-config repo setting. 

**i think we should probs turn the dependabot security scanning on regardless of what tool we use to manage actual dependencies**

has its own page, you cant do much from there though - https://github.com/alphagov/notifications-dependancies-dependabot/network/dependencies

it cant install pyproj and looks like it crashes as a result?

npm integration seems fine and works cleanly - not sure if it would update a package lock file for us though.

it doesn't handle pip-compile nicely it looks like - got confused by some diffs. i'd like it to re-run pip compile ideally to refreeze dependencies.

we see some errors that look like `git_dependencies_not_reachable {:"dependency-urls"=>["https://github.com/alphagov/notifications-utils.git"]}`. From googling, this often appears to be due to repos being private. however this isn;t the case this time as utils isn't private - but i worry maybe dependabot cant process that repo (possibly due to errors similar to pyproj), and then it misinterprets errors.

We can raise support tics with github or raise issues on https://github.com/dependabot/dependabot-core/ if we have problems.
