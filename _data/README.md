# DRY (Don't Repeat Yourself)

Imagine another game designer makes a new monster book for Cairn that's CC BY-SA. Within days, someone submits an issue to this repository saying "please add the new monster book."

You contact the creator, who says "here's the PDF, the .afpub, Word file, idk here's all of it." So you get to work copy-pasting, adding octothorpes, and backspacing unwanted line breaks.

Then someone enters another issue, "add the new monster book to Foundry VTT!"

And another, "there's a typo in the Black Pudding description." Gah, that needs to be fixed in both repos!

And a pull request, "I updated the Italian translations because the last person didn't know what they were doing. No not the SRD, just Foundry."

#### Editing Markdown isn't fun. Copying and pasting everywhere is horrible. Having to fix things in more than one place makes me want to pull my hair out.

This is an answer to these problems.

## Sanity.io Cloud Content Storage

This repository has been hooked up to a cloud service that provides a way to easily edit statblocks and more using Sanity Studio, a cloud-enabled document editor. [Sanity.io](https://sanity.io) (the cloud provider) stores it in a way that's friendly for Jekyll to display however you want. Crucially, it's an [ndjson](http://ndjson.org/) document store, pretty much identitical to how Foundry VTT packs work.

## The `_data` Directory

This directory is a native feature of Jekyll. See [the docs on datafiles](https://jekyllrb.com/docs/datafiles/). Ignore the fact that there's no json example on there. It handles an array of json objects natively.

This directory's empty because we don't want to hand-edit this repository unless we absolutely need to. A GitHub Action will add the files whenever we want another update to the SRD.

## The GitHub Actions workflow

1. We trigger the workflow

## Portable Text

This repository is now "portable text"-enabled. This means that if you'd really like, you can put all of your formatting in the cloud too. It hasn't really been tested, but in theory you can edit a block of text with bold, italics, h1-h6, etc, and it will get updated in your PDF on itch.io, your SRD site, your character generator, and on Foundry VTT. If you want Alexa/Siri apps, you can indicate emphasis in the same places using the same formatting. Read more about [Portable Text](https://github.com/portabletext/portabletext).
