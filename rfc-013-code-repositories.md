# Code repository standards

## Summary

A set of standards to be used for projects that will be shared within Made Tech or the greater technology community. These are projects hosted on GitHub, Bitbucket, Gitlab or similar public source control management.

## Problem

Made Tech code repositories (to be referred to as repos herein) do not have a common look and feel.

## Visibility

The visibility of your project **SHOULD** mean the following:

- You **MUST** set your repo to **Private to creator**  if code isn’t ready for wide consumption.
- You **MUST** set your repo to **Private to the organisation** when the code is propriety or NDA bound.
- You **SHOULD** set your repo to **Public**  if it can be used by the community at large. It **MUST** also come with `README.md` and `LICENSE`

## Files in the Repository

### README.md

It **MUST** exist for **Private to the organisation** and **Public**.

#### Headers

The following **SHOULD** be considered the absolute minimum when making a project public.

- Purpose of project
- How to install and use
- How to contribute
- License / Copyright

Where possible create a separate `CONTRIBUTING.md` when adding the **How to contribute** header. Also consider the use of a Code of Conduct. An excellent example is provided by [Contributor Covenant][link_cc].

Create a separate `LICENSE` file to contain the license with your name and the creation date of the repo. 

Important: the absence of a license in a repo means that the software cannot be used (despite being publicly available). More information regarding the effect no license in a repo can be found on the [Choose a License][link_choose_a_license] site by GitHub.

#### Table of Contents

If the `README.md` scrolls i.e. the entire document is not visible on screen you **MUST** include a table of contents. This can be automated using the following editor extensions/plugins/layers:

- Visual Studio Code [Markdown TOC][link_vsc_markdown_toc]
- Atom [Markdown TOC][link_atom_markdown_toc]
- Sublime [Markdown TOC][link_sublime_markdown_toc]
- Vim [vim-markdown-toc][link_vim_markdown_toc]
- Spacemacs [spacemacs_markdown][link_spacemacs_markdown]

#### Linking

You **SHOULD** use [reference style links][link_daring_fireball] to avoid duplication and centralised location for all internal/external links.

Example

```markdown
This is an [example][link_example] document.

More text follows....

Until we reach the end.

[link_example]: https://example.com
```

### License

If the project is a derivative of an existing project, you **SHOULD** use the existing project’s license. Otherwise MIT or APACHE Version 2 **MAY** be good choices. A copy of the chosen license should existing in `LICENSE`.

[link_cc]: https://www.contributor-covenant.org/
[link_choose_a_license]: https://choosealicense.com/no-permission/
[link_vsc_markdown_toc]: https://marketplace.visualstudio.com/items?itemName=joffreykern.markdown-toc
[link_atom_markdown_toc]: https://atom.io/packages/markdown-toc
[link_sublime_markdown_toc]: https://packagecontrol.io/packages/MarkdownTOC
[link_vim_markdown_toc]: https://github.com/scrooloose/vim-markdown-toc
[link_spacemacs_markdown]: http://spacemacs.org/layers/+lang/markdown/README.html
[link_daring_fireball]: https://daringfireball.net/projects/markdown/syntax#link
