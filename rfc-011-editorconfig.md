# Editorconfig

## Summary

Introduce use of [editorconfig][1] across projects.

## Problem

Not all editors are alike. In some circumstances, an editor will insert a space instead of a tab. Some will remove whitespace, others won't. The most common issue faced is the absense of a newline character at the end of a file, or when writing a Makefile while your editor is set up for other languages without tabs.

## Proposal

All projects going forward **MUST** include a .editorconfig file in the root of the project.

All people **SHOULD** be familiar with the rules of a .editorconfig.

The .editorconfig **MUST** include rules for common styles across the project and company.

An example .editorconfig **SHOULD** be used as a starting point:

```ini
root = true

[*]
charset = utf-8

end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true

indent_style = space
indent_size = 2

[{Makefile,*.mk}]
indent_style = tab

[*.py]
indent_size = 4
```

The .editorconfig **MAY** evolve over time to cover more usecases, and projects **SHOULD** be updated accordingly.

A project **MAY** define additional rules, but **SHOULD NOT** change the base rules.

If the base rules of a .editorconfig are changed, they **MUST** be justified with an inline comment.

Developers **SHOULD** install a plugin for editorconfig when one is available to them.

If you use an editor that does not support .editorconfig, then you **MUST** configure the editor in such a way that mirrors the project's .editorconfig rules


[1]: https://editorconfig.org/
