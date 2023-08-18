# Personal Access Tokens

SPE will be using fine-grained access tokens.
Classic tokens are only available for migration purposes and will be disabled once migration is over.

An [explanation](https://docs.github.com/en/enterprise-cloud@latest/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#fine-grained-personal-access-tokens) of fine-grained access tokens.

A [reference](https://docs.github.com/en/enterprise-cloud@latest/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-fine-grained-personal-access-token) to create fine-grained personal access tokens.

## Permission Access

Make you read the previous [section's links](#personal-access-tokens) before proceeding on creating the PATs.

### Basic Permissions to do work

>Repository Access
  `All repositories`

>Permissions
  Repository Permissions
    `Access: No access` for all permissions by default
    Contents: `Access: Read and write`
    Metadata: `Access: Read-only` (should be set once Contents is set to Read and write)
  Account Permissions
    `Access: No access` for all permissions by default

### Expert Permissions for CLI wizards

>Repository Access
  `All repositories`

>Permissions
  Repository Permissions
    `Access: No access` for all permissions by default
    Contents: `Access: Read and write`
    Issues: `Access: Read and write`
    Metadata: `Access: Read-only` (should be set once Contents is set to Read and write)
    Pull-Requests: `Access: Read and write`
  Account Permissions
    `Access: No access` for all permissions by default

## Multiple PATs

For experts (as in do not seek support from DevOps or anyone in SPE), these [directions](https://docs.github.com/en/enterprise-cloud@latest/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-your-personal-account/managing-multiple-accounts) allow you to manage multiple organization PATs.
