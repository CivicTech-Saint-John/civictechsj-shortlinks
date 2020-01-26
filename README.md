# CivicTechSJ: Shortlinks

**Important:** This repo is an unofficial demonstration, and not actively used yet.

For creating/updating our `link.civictechsaintjohn.com` shortlinks.

Shortlinks are viewed and edited via a Google Spreadsheet at https://link.civictechsaintjohn.com/shortlinks

Changing the above file results in updates to the shortlinks themselves.
The updates aren't reflected immediately, but happen every 30 minutes.

This repo contains documentation and the automated scripts for syncing the shortlinks from the spreadsheet.

## Terminology

- **shortlink.** The shortened url. Example: https://link.example.com/my-shortlink
- **base URL.** The base for the shortened urls. Example: `https://link.example.com`
- **keyword.** (a.k.a. **slashtag**) The human-readable string that
  makes up the path of the shortlink, and is appended to the base URL.
Example: `my-shortlink`

## Technology Used

- [**Rebrandly.**][rebrandly] A hosted shortlink service usable via API.
- [**Google Sheets.**][sheets] For easily storing and editting shortlinks without logging into Rebrandly.
- [**GitHub Actions.**][actions] For running automated scripts in the cloud. This syncs the shortlinks from the GSheet.

   [actions]: https://help.github.com/en/actions
   [rebrandly]: https://www.rebrandly.com/
   [sheets]: https://zapier.com/learn/google-sheets/google-sheets-tutorial/

## :muscle: Contributing

tl;dr - simply edit [`shortlinks.csv`](/shortlinks.csv)!

- **Creating** a new shortlink? Add a new line.
- **Changing** an existing shortlink? Change the `destination_url`.
- **Removing** an existing shortlink? Clear the `destination_url` field, leaving the `keyword` field as-is.

As example: Say you want to create a new shortlink pointing
https://link.civictechsaintjohn.com/my-shortlink to
https://some-website.com/asfjaflnadsesljarmdkasdjasd. Just add a new line to
the spreadsheet with `my-shortlink` as the `keyword` and your complicated
URL as the `destination_url`.

Shortlinks are **updated every 30 minutes** via Github Actions.
