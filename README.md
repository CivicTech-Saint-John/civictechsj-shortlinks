# CivicTechSJ: Shortlinks

**Important:** This repo is an unofficial demonstration, and not actively used yet.

For creating/updating our `link.civictechsaintjohn.com` shortlinks.

Shortlinks are viewed and edited via a Google Spreadsheet at https://link.civictechsaintjohn.com/shortlinks

Changing the above file results in updates to the shortlinks themselves.
The updates aren't reflected immediately, but happen every 30 minutes.

This repo contains documentation and the automated scripts for syncing the shortlinks from the spreadsheet.

## Why Use Shortlinks

Surprisingly, shortlinks main value isn't their shortness (though that's sometimes helpful).

Shortlinks are a way for a **group of people** working with online tools and resources to **more intuitively navigate their digital environment**. They can slowly grow a set of "keywords" amongst themselves (e.g., the "gdrive" in `link.example.com/gdrive`) that map directly to the places they use most online.

Some perks of this approach:
- Keywords are **memorable**, because the group decides them. Find the business plan at `link.example.com/bizplan` instead of some long Google Doc URL.
- Resource locations are **changeable**, without taxing people to keep track of these changes. You revised and moved the business plan? No prob! Just update the shortlink, and everyone knows where it is without learning.
- Keywords make for more **humane onboarding**. It can be demoralizing to keep up with a group that's already learned where everything is. Shortlinks help new people keep up just as easily, with less hand-holding (that we sometimes forget to offer).
- Keywords are **communicable** in spoken conversations. You can speak of a resource, and know that everyone automatically knows how to get to it, without special guidance. In a sense, the spoken keyword actually _resolves_ to the resource itself.
- Similarly, keywords help shared language become **convergent**. Amongst a few people, they might separately call the same resource "the most recent proposal doc" or "the google doc" or "the ACME proposal". This can be confusing. Shortlinks help folks converge on a clear way of speaking, because one chosen term becomes materially more useful.

In short, you should use shortlinks **because working on the internet is _so much more confusing_ than physical space**.

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

tl;dr - simply edit [this spreadsheet](https://link.civictechsaintjohn.com/shortlinks)!

- **Creating** a new shortlink? Add a new line.
- **Changing** an existing shortlink? Change the `destination_url`.
- **Removing** an existing shortlink? Clear the `destination_url` field, leaving the `keyword` field as-is.

As example: Say you want to create a new shortlink pointing
https://link.civictechsaintjohn.com/my-shortlink to
https://some-website.com/asfjaflnadsesljarmdkasdjasd. Just add a new line to
the spreadsheet with `my-shortlink` as the `keyword` and your complicated
URL as the `destination_url`.

Shortlinks are **updated every 30 minutes** via Github Actions.

## ProTip

Shortlinks work on their own in the address bar, but for even easier access on
your own computer, you can **add a "custom search engine" keyword to your
browser.**

This allows you to type something like `ctsj<tab>shortlinks` into the search bar,
and get https://link.civictechsaintjohn.com/shortlinks

Here's a screencast showing how it works (for another domain) in Chrome ([full instructions](https://www.techrepublic.com/article/pro-tip-add-custom-search-engines-in-chrome-for-more-efficient-searching/)):

![screenshot of adding/using shortlinks as keywords with custom search engine set in browser](https://i.imgur.com/2D8B7kS.gif)
