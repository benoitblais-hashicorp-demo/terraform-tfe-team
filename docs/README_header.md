# HCP Terraform Teams Terraform module

HCP Terraform Teams module which manages configuration and life-cycle of
your HCP Terraform teams.

## Permissions

To manage the agent pool resources, provide a user token from an account with 
appropriate permissions. This user should have the `Manage organization access` permission. 
Alternatively, you can use a token from a team instead of a user token.

## Authentication

The HCP Terraform provider requires a HCP Terraform/Terraform Enterprise API token in 
order to manage resources.

There are several ways to provide the required token:

- Set the `token` argument in the provider configuration. You can set the token argument in the provider configuration. Use an
input variable for the token.
- Set the `TFE_TOKEN` environment variable. The provider can read the TFE_TOKEN environment variable and the token stored there
to authenticate.

## Features

- Create and manage HCP Terraform teams.
- Manage team's organization access.
- Manage team's members.
- Generates a new team token and overrides existing token if one exists.
- Manage team's permissions on a project.
- Manage team's permissions on a workspace.

## Usage example
```hcl
module "team" {
  source  = "app.terraform.io/benoitblais-hashicorp/team/tfe"
  version = "0.0.0"

  name           = "Team Name"
  sso_team_id    = "Microsoft Entra Group Id"
  organization   = "Organization Name"
  token          = true
}
```