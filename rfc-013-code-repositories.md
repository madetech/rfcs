# Code repository standards

## Summary

A set of standards to be used for projects that will be shared within Made Tech or the greater technology community. These are projects hosted on GitHub, Bitbucket, Gitlab or similar public source control management.

## Problem

Made Tech code repositories (to be referred to as repos herein) do not have a common look and feel.

## Visibility

The visibility of your project **SHOULD** mean the following:

- You **MUST** set your repo to **Public** unless you have a reason not to.
- You **MUST** set your repo to **Private to the Customers organisation** if the customer owns the Intellectual Property and has a public source control management platform account.
- You **MUST** set your repo to **Private to the Made Tech organisation** if the customer owns the Intellectual Property and has a public source control management platform account.

## Files in the Repository

### README.md

The `README.md` **MUST** exist for all repos.

#### Headings

The following headings **SHOULD** be considered the absolute minimum to include in the `README.md` when making a project public.

- Purpose of project
- How to install and use
- How to contribute
- License / Copyright

#### Table of Contents

If the `README.md` scrolls i.e. the entire document is not visible on screen you **MAY** need to include a table of contents. 

This can be automated using the following editor extensions/plugins/layers:

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

Here's where we place the links for the document.

[link_example]: https://example.com
```

### LICENSE

You **MUST** define a license for the repo.

Important: the absence of a license in a repo means that the software cannot be used (despite being publicly available). More information regarding the effect no license in a repo can be found on the [Choose a License][link_choose_a_license] site by GitHub.

If the project is a derivative of an existing project, you **SHOULD** use the existing project’s license.

For code based projects [MIT][link_license_mit] **SHOULD** be a good choice. 

For non-code (artwork, music, documents, etc) Creative Commons [CC BY 4.0][link_license_ccby40] **SHOULD** be a good choice.

### CONTRIBUTING.md

This document **SHOULD** provide instructions on how to contribute to the project.

You **SHOULD** include the Code of Conduct that contributors should adhere too. An excellent example is provided by [Contributor Covenant][link_cc].

[link_cc]: https://www.contributor-covenant.org/
[link_choose_a_license]: https://choosealicense.com/no-permission/
[link_vsc_markdown_toc]: https://marketplace.visualstudio.com/items?itemName=joffreykern.markdown-toc
[link_atom_markdown_toc]: https://atom.io/packages/markdown-toc
[link_sublime_markdown_toc]: https://packagecontrol.io/packages/MarkdownTOC
[link_vim_markdown_toc]: https://github.com/scrooloose/vim-markdown-toc
[link_spacemacs_markdown]: http://spacemacs.org/layers/+lang/markdown/README.html
[link_daring_fireball]: https://daringfireball.net/projects/markdown/syntax#link
[link_license_mit]: https://choosealicense.com/licenses/mit/
[link_license_ccby40]: https://creativecommons.org/licenses/by/4.0/