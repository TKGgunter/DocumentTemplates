# DocumentTemplates
A Repo for document templates

Use [grip](https://pypi.org/project/grip/) to render the markdown.

If you clone this repository double check the git url. If the repo is linked to the http url you will have trouble pushing updates to the repo.
Check the ssh key on your device and compare it to the key in github. If they are not the same you'll need to add it.
Next update the local git url repo.

```bash
-> git remote  get-url --all origin
https://github.com/TKGgunter/DocumentTemplates.git
git remote set-url origin git@github.com:TKGgunter/DocumentTemplates.git
```

CR contributions: https://github.com/tokio-rs/tokio/blob/master/CONTRIBUTING.md


---
*Here are some helpful tools when writing docs in markdown. This follows github extension*


This is a footnote[^1].

[^1]: Comment reference

> [!NOTE]
> example


> [!TIP]
> example 

> [!IMPORTANT]
> Example

> [!CAUTION]
> example


> The following will not show up when rendered.
[//]: # (
This is a comment to the writter.
)

[tag]: <> (#tag1, #tag2, #tag3)
