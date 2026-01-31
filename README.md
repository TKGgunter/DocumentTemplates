# DocumentTemplates
A Repo for document templates

Use [grip](https://pypi.org/project/grip/) to render the markdown.

If you clone this repository double check the git url. If the repo is linked to
the http url you will have trouble pushing updates to the repo. Check the ssh
key on your device and compare it to the keys in github. If they are not the
same you'll need to add it.
After adding your key update the local git url repo using the following command:

```bash
-> git remote  get-url --all origin
https://github.com/TKGgunter/DocumentTemplates.git
git remote set-url origin git@github.com:TKGgunter/DocumentTemplates.git
```

CR contributions: https://github.com/tokio-rs/tokio/blob/master/CONTRIBUTING.md


---

The templates in this repo are written in github extended markdown.  The
following are useful tools when writing documents.



This is a footnote[^1].

[^1]: This is the reference note for the footnote.


> [!NOTE]
> Here we tag this quote block as a note.


> [!TIP]
> Here it's tagged as a tip.

> [!IMPORTANT]
> This is very important.

> [!CAUTION]
> You could be careful when reading this one.


> The following will not show up when rendered.

[//]: # (
This is a comment to the writter.
)

---
In the future I would like to extend markdown to do the following
# Header {#custom-id}
Custom ids to headers

## Definition lists
Term1
: definition for term1.

Term2
: definition for term2.


```d2
a->b
```

[tag]: <> (#tag1, #tag2, #tag3)






