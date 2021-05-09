# corpus-search-data-private

Data to be used in the Manx Corpus where any of:

* Copyight is unknown and needs further research
* Permission has been granted, but no formal license 
* Permission has been granted, but not for the data to be included in the open data repository.

## Deployment

This repository uses [GitHub Deploy Keys](https://docs.github.com/en/developers/overview/managing-deploy-keys#deploy-keys). \[[Additional Info](https://docs.github.com/en/developers/overview/managing-deploy-keys#deploy-keys)\]

To load: as user: `david2` on the corpus search server, execute 

`git clone git@github.com-corpus-search-data-private-01:david-allison-1/corpus-search-data-private.git`  
`cp` the `ClosedData` folder somewhere useful

## Setup on a new server

### Generate a Deploy Key

Replace `david2` with your username

* `ssh-keygen -t ed25519 -C "github - corpus-search-data-private"`
  *  Comment is variable
*  Select a location, typically inside .ssh (example: `/home/david2/.ssh/repo-corpus-search-data-private-2021-05-09`)
*  No passphrase
*  Obtain the public key (`pub`) : `head /home/david2/.ssh/repo-corpus-search-data-private-2021-05-09.pub`
*  Add this to GitHub Deploy Keys for the Repo: [/settings/keys](https://github.com/david-allison-1/corpus-search-data-private/settings/keys)
*  Setup a custom host using the ssh key:
*  `nano ~/.ssh/config`
```
Host github.com-corpus-search-data-private-01
        Hostname github.com
        IdentityFile=/home/david2/.ssh/repo-corpus-search-data-private-2021-05-09
```
### Test: 
```
ssh -T git@github.com-corpus-search-data-private-01
Hi david-allison-1/corpus-search-data-private! You've successfully authenticated, but GitHub does not provide shell access.
```

* clone: `git clone git@github.com-corpus-search-data-private-01:david-allison-1/corpus-search-data-private.git`
