---
layout: post
title: Add Zenodo metadata to a Github repository
date:   2021-12-16
comments: true
author: Will Usher
category: code
tags: interoperability reusability retrievability
---

You can include a JSON metadata file in your Github repository to automatically populate the
metadata associated with the archived deposit on Zenodo. This guidelines builds on material available
in the [Zenodo documentation](https://developers.zenodo.org/#add-metadata-to-your-github-repository-release).

To do this create a new file called `.zenodo.json` in the root folder of your Github repository.

The contents of the file should look something like this:

```json
{
  "title": "Adding zenodo metadata to a Github repository",
  "description": "The guideline document describes how to add metadata to a Github repository",
  "license": {"id": "CC-BY-4.0"},
  "creators": [
    {
      "affiliation": "KTH Royal Institute of Technology",
      "name": "Will Usher",
      "orcid": "0000-0001-9367-1791"
    },
  ],
  "access_right": "open",
  "upload_type": "publication",
  "publication_type": "other"
}

```

Once you've added the information to the file, save and commit the changes.

Now, create a new release on the Github repository, and the new metadata should appear in
the Zenodo deposit associated with the release.

More information on the fields you can include can be found in the Zenodo
[documentation](https://developers.zenodo.org/#representation).

You can verify your JSON metadata file with the
[Zenodo JSON schema](https://zenodo.org/schemas/deposits/records/legacyrecord.json)
