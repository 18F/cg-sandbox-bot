# cg-sandbox-bot
[![Code Climate](https://codeclimate.com/github/18F/cg-sandbox-bot/badges/gpa.svg)](https://codeclimate.com/github/18F/cg-sandbox-bot)

Monitor CF cloud controller users and create a sandbox space for known domains.

The sandbox bot monitors the Cloud.gov UAA (User Account and Authentication) server for new accounts.
If a new account is created with a .gov or .mil email, it will automically create a user space within that
organization in Cloud.gov - creating a new organization if one does not already exist.

## Creating UAA client

```shell
uaac client add [your-client-id] \
	--name "UAA Sandbox Monitor" \
	--scope "cloud_controller.admin, cloud_controller.read, cloud_controller.write, openid, scim.read" \
	--authorized_grant_types "authorization_code, client_credentials, refresh_token" \
	-s [your-client-secret]
```

## Public domain

This project is in the worldwide public domain. As stated in CONTRIBUTING:

> This project is in the public domain within the United States, and copyright
> and related rights in the work worldwide are waived through the CC0 1.0
> Universal public domain dedication.

All contributions to this project will be released under the CC0 dedication. By
submitting a pull request, you are agreeing to comply with this waiver of
copyright interest.
