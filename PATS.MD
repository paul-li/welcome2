# Personal Access Tokens (PATS)

SPE will be using fine-grained personal access tokens.
Classic tokens are only available for migration purposes and will be disabled once migration is over.

An [explanation](https://docs.github.com/en/enterprise-cloud@latest/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#fine-grained-personal-access-tokens) of fine-grained access tokens.

A [reference](https://docs.github.com/en/enterprise-cloud@latest/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-fine-grained-personal-access-token) to create fine-grained personal access tokens.

## Quick Guide

If you can't read the short [GitHub blog post](https://github.blog/2022-10-18-introducing-fine-grained-personal-access-tokens-for-github/) about fine-grained PAT, here is some short steps you can follow:

1. Login into GitHub.com through Okta.
1. Click [here](https://github.com/settings/personal-access-tokens/new) to create new token.
1. Set the following:

> New fine-grained personal access token
> ---
>
> **Token name**: Something meaningful to the GitHub organization that it will be used in<br>
> **Expiration**: 90 days.  Don't get cute, you have 1 yr max.<br>
> **Description**: Something that will remind you what this token is used for<br>
> **Resource Owner**: DO NOT SELECT YOURSELF!  Select which Organization this token be used for<br>
>
> Repository Access
> ---
> (x) **All repositories**
>
> Permissions
> ---
>   Repository Permission (expand)
> ---
> **Contents**: Access: Read and write<br>
> **Issues**: Access: Read and write<br>
> **Metadata**: Access: Read-only<br>
> **Pull-Requests**: Access: Read and write<br>
>
> Account Permissions
> ---
> **Skip this section for now**
>

4. Click `Generate token`

Save the new token to your personal password/key management software.

**TO CHANGE THE `Permissions` OF ANY PAT, YOU WILL NEED TO CREATE A NEW ONE!**

## Multiple PATs

For experts (as in do not seek support from DevOps or anyone in SPE), these [directions](https://docs.github.com/en/enterprise-cloud@latest/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-your-personal-account/managing-multiple-accounts) allow you to manage multiple organization PATs.

