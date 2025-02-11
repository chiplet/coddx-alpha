# Generate Files

### Features

- Work with any programming languages.
- Templating syntax.
- Store templates as a single file (can be committed to git, shared with others).
- Auto-create sub-directories.
- Built-in params (fileName, date, time, etc.).
- Custom params.
- Context menu to generate files/directories from anywhere.

#### Usage:

- Open Coddx panel:
  - Bring up the Command Palette (F1), type and select: Coddx: Generate Files.
  - Or: right-click on a directory, select: Generate files.
- Verify Template to suit your needs. (See <a href="https://bit.ly/2WHprLW">Docs</a> for syntax)
- Verify the output path (relative to Project root), a new directory will be created if not existed.
- Enter the new file name to generate file(s).

<img src="docs/media/coddx-demo.gif" />
  
<img src="docs/media/panel.png" height="280" />

### How does it work?

Coddx uses Mozilla's Templating Engine called <a href="https://github.com/mozilla/nunjucks">nunjucks</a>. Nunjucks is a powerful library, supports more advanced use cases like parameters, custom filters, etc.

### Templating Syntax

Example:

```
// -------------->> {{fileName}}.tsx
// created time: {{YYYY}}-{{MM}}-{{DD}} {{HH}}:{{mm}}
// file1 content...

// -------------->> __test__/{{fileName}}.test.tsx
// file2 content... (sub-directory will be created)
```

Built-in Template Variables:

- {{fileName}} - will be replace with the value of "File Name" field.
- {{YYYY}}, {{MM}}, {{DD}}, {{HH}}, {{mm}} - year, month, day, hours (24), minutes.

Read more: <a href="https://mozilla.github.io/nunjucks/templating.html">Nunjucks Templating Syntax</a>

### Custom Variables

You can declare custom variables (Params field) in JSON format, for example:

- { "myVar": "value" } - declare `myVar`, then use it in your template like `{{myVar}}`

### Custom filters

(Coming soon)
