* * *

id: docs_cli_team guide: docs_cli layout: guide

* * *

<p class="lead">Maintain team memberships</p>

##### `yarn team` [](#toc-yarn-team){#toc-yarn-team.toc}

Manage teams in organizations, and change team memberships.

### Commandes [](#toc-commands){#toc-commands.toc}

##### `yarn team create <scope:team>` [](#toc-yarn-team-create){#toc-yarn-team-create.toc}

Create a new team.

##### `yarn team destroy <scope:team>` [](#toc-yarn-team-destroy){#toc-yarn-team-destroy.toc}

Destroys an existing team.

##### `yarn team add <scope:team> <user>` [](#toc-yarn-team-add){#toc-yarn-team-add.toc}

Add a user to an existing team.

##### `yarn team rm <scope:team> <user>` [](#toc-yarn-team-rm){#toc-yarn-team-rm.toc}

Remove a user from a team they belong to.

##### `yarn team ls <scope>|<scope:team>` [](#toc-yarn-team-ls){#toc-yarn-team-ls.toc}

If performed on an organization name, will return a list of existing teams under that organization. If performed on a team, it will instead return a list of all users belonging to that particular team.

### Details [](#toc-details){#toc-details.toc}

yarn team always operates directly on the current registry, configurable from the command line using `--registry=<registry url>`.

In order to create teams and manage team membership, you *must be a team admin* under the given organization. Listing teams and team memberships may be done by any member of the organizations.

Organization creation and management of team admins and organization members is done through the npm website, not the CLI.

To use teams to manage permissions on packages belonging to your organization, use the yarn access command to grant or revoke the appropriate permissions.