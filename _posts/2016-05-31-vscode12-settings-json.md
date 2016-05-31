
---
layout: post
title:  "[vscode] Visual Studio Code Insiders 1.2 で settings.json に追加されたもの"
categories: vscode
---

Visual Studio Code stable 1.1.1 と Visual Studio Code Insiders 1.2.0 の settings.json 差分。
差分は、CLI (code or code-insiders) に --disable-extensions を付けてとったもの。

```
{
  // フォント ファミリを制御します。
  "editor.fontFamily": "Menlo, Monaco, 'Courier New', monospace",

  // フォント サイズを制御します。
  "editor.fontSize": 12,

    // Inserting and deleting whitespace follows tab stops
  "editor.useTabStops": true,

  // Remove trailing auto inserted whitespace
  "editor.trimAutoWhitespace": true,

  // Keep peek editors open even when double clicking their content or when hitting Escape.
  "editor.stablePeek": false,

  //-------- Integrated terminal configuration --------

  // The path of the shell that the terminal uses on Linux.
  "terminal.integrated.shell.linux": "/bin/bash",

  // The path of the shell that the terminal uses on OS X.
  "terminal.integrated.shell.osx": "/bin/bash",

  // The path of the shell that the terminal uses on Windows.
  "terminal.integrated.shell.windows": "cmd.exe",

  // The font family used by the terminal (CSS font-family format).
  "terminal.integrated.fontFamily": "Menlo, Monaco, Consolas, \"Droid Sans Mono\", \"Courier New\", monospace, \"Droid Sans Fallback\"",

  // Enable word based suggestions.
  "editor.wordBasedSuggestions": true
}
```