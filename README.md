# NCEAS GSuite Tool

Simple example script showing how to use the Google GSuite AdminAPI for
managing users and groups.  The current tool performs three simple operations:

- list users in domain
    - `./ngt --list`
- list groups for a user
    - `./ngt --list matt@magisa.org`
- update a users email for all of their groups
    - `./ngt --update matt@magisa.org mbjones.89@gmail.com`


## Installation

The tool uses several python libraries, which need to be installed first via `pip`:

```bash
$ sudo pip install --upgrade google-api-python-client google-auth-httplib2 google-auth-oauthlib
```

## Authentication

Authentication is provided via a `credentials.json` file that provides the
client id and client secret to be used for all operations.  These can be
configured through the [Google API
Dashboard](https://console.developers.google.com/apis/credentials).  You will
need to configure an `OAuth 2.0 client ID` and with sufficent privledges for the
necessary authentication scopes to be granted:

SCOPES 

- `https://www.googleapis.com/auth/admin.directory.user`
- `https://www.googleapis.com/auth/admin.directory.group`
- `https://www.googleapis.com/auth/admin.directory.group.member`

Once the client id is created on the dashboard, download the file to the
directory containing `ngt` and name it `credentials.json`.  The first time you
run the tool, you will be requested to authenticate with Google, and allow the
requested scopes.  The authorization is cached in a local file so you don't have
to log in again.

