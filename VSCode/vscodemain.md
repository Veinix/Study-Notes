# VSCode Notes

Visual Studio Code, also commonly referred to as VS Code, is a source-code editor made by Microsoft with the Electron Framework, for Windows, Linux and macOS. Features include support for debugging, syntax highlighting, intelligent code completion, snippets, code refactoring, and embedded Git. Users can change the theme, keyboard shortcuts, preferences, and install extensions that add functionality.

[Back](../Index/index.md)

## Table of Contents

- [Shortcuts](#shortcuts)
  - [Display](#display)
  - [File Navigation](#file-navgiation)
  - [Search](#search)
- [Sources](#sources)

---

## Shortcuts

Here are all the different keyboard shortcuts built into VSCode.
If you want to add a key binding to an action or find out what command is bound to a specific key you can open the `Keyboard Shortcut` editor. Open the editor by going to the menu under `File > Preferences > Keyboard Shortcuts`. (Code > Preferences > Keyboard Shortcuts on macOS)

Find a rule that triggers the action in the Default Keyboard Shortcuts and write a modified version of it in your keybindings.json file.

For example:

```json
// Original, in Default Keyboard Shortcuts
{ "key": "ctrl+shift+k",          "command": "editor.action.deleteLines",
                                     "when": "editorTextFocus" },
// Modified, in User/keybindings.json, Ctrl+D now will also trigger this action
{ "key": "ctrl+d",                "command": "editor.action.deleteLines",
                                     "when": "editorTextFocus" },
```

If you only want a specific file type to have a specific keybinding, use the editorLangId context key in your when clause:

For example:

```json
{ "key": "shift+alt+a",           "command": "editor.action.blockComment",
                                     "when": "editorTextFocus && editorLangId == csharp" }
```

### Basic Editing

---

### Rich Languages Editing

---

### Navigation

---

### Editor/Window Management

---

### File Management

---

### Display

Toggle Full-Screen: `F11`

Toggle Sidebar: `ctrl +  B`

Show Explorer / Toggle Focus: `ctrl + shift + E`

Show Search: `ctrl + shift + F`

Show Source Control: `ctrl + shift + G`

Show Run: `ctrl + shift + D`

Show Extensions: `ctrl + shift + X`

Show Output: `ctrl + shift + U`

Quick Open View: `ctrl + Q`

---

### File Navgiation

Open recent file: `ctrl + R`

Quick open file: `ctrl +  P`

Go to Symbol in file: `ctrl + shift  + O`

Select all of highlighted: `ctrl + shift + L`

Navigate files opened in workspace: `ctrl (hold) + TAB`

Jump to definition: `ctrl + click`

Open definition to side: `ctrl + alt + click`

---

### Search

Search inside a file: `ctrl +  F`

Search workspace: `ctrl + shift + F`

### Search Editor

### Preferences

### Debug

### Tasks

### Extensions

---

## Sources

[VSCode Docs](https://code.visualstudio.com/docs/getstarted/keybindings)
