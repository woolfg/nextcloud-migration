# Nextcloud Migration (WIP)
Migration guide and tools to migrate an old nextcloud instance to a managed [hetzner storage share](https://www.hetzner.com/storage/storage-share) instance. As you can't just copy the database due to the limited permissions on the managed host, we have to migrate data manually:

## What we cover in this migration guide
- Files
- Users
- Shares

## What we do not cover and what you will lose
- Deleted files
- File versions
- Any other file metadata that is storen in the nextcloud DB and not in the files
- Maybe other stuff that we not aware of (feel free to add/edit by sending a PR)

## Prerequisites
- You need root access to the old nextcloud instance (Maybe you can also achieve it without by using the [OCC Web](https://apps.nextcloud.com/apps/occweb) app)


## Files


## Shares

Before important your shares to the new instance, make sure that you have imported all users and files before.

### Export Shares of the old instance

- Install the app [Share Listing](https://apps.nextcloud.com/apps/sharelisting) to be able to list all shares on the command line. (Make sure to run `occ` using the [right user/permissions](https://docs.nextcloud.com/server/13.0.0/admin_manual/configuration_server/occ_command.html#http-user-label))
- Login to your old instance and run `./occ sharing:list` to get a json file including all shares

## TODO:
- create script to create shares y reading the json and send commmand to API https://docs.nextcloud.com/server/16/developer_manual/client_apis/OCS/ocs-share-api.html
