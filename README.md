# Vault docker dev setup

### Get started 
- Edit vault-config/vault-setup.sh (Line 29 onwards) to include all commands and keys required for your setup 
- optionally write them to env.json file at the bottom of vault-config/vault-setup.sh 
- docker-compose up -d : this should create files (vault-seed.sh, vault-seed-file-version and env.json)
- vault should be unsealed and available to use

### Setup includes
- UnSeal vault every 5s
- Create a vault seed config/keys that stays same for all developers 
- docker-compose up -d created all seed data and config which should be committed into repository to provide same keys to everyone
- data is persistent in docker volume

## To make changes later on
- Append change commands to vault-setup .sh
- docker-compose down -v : this should remove all local data
- docker-compose up -d: recreate from seed 
- run those commands sequentially inside vault-init container
- run `sh /data/vault-setup-create-zip.sh 1` 
- Commit to repository
