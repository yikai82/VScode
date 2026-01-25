## 🔧 Atom One Dark Customized Green  

### 1. Add the active tab highlight

1. Open Settings (JSON view):
    Press Ctrl + Shift + P (or Cmd + Shift + P on Mac).
    Type “Preferences: Open Settings (JSON)” → hit Enter.
    👉 This opens your settings.json file.
  
2. Find your "**workbench.colorCustomizations**" section and copy the section of **workbench.colorCustomizations** from snippet below to your section:  

```json
{
  // we try to make semantic highlighting look good
  "editor.semanticHighlighting.enabled": true,
  // prevent VSCode from modifying the terminal colors
  "terminal.integrated.minimumContrastRatio": 1,
  // make the window's titlebar use the workbench colors
  
  // ----- <<< Theme test: >>> -------
  // -->>> NOte: Need to turn off the normal text area <<<---
  // 1. Buzzokai GitHub Dark ---> looks good 
  // 2. Calmpuccin Nitro Cold Brew  -
  // ---> cannot fix the markdown text color, too blue-green
  // 3. Alt Catppuccin Mocha  
  // ---> The markdown rendered text is too white

  // Theme customization
  "workbench.colorTheme": "Buzzokai GitHub Dark",
  "workbench.colorCustomizations": {
  
      "[Buzzokai GitHub Dark]": {
          // Progress/Activity Indicator
          "progressBar.background": "#FF69B4",

          // 1) Set tab color 
          "tab.activeBorderTop": "#ff9898",       // pink top glow
          "tab.activeBorder": "#ff9898",          // pink bottom glow
          "tab.activeBackground": "#ff00bb3a",    // semi-transparent blue fill
          "tab.activeForeground": "#ffffff",       // white text stays crisp

          // 2) Dim the Explorer / side bar text
          "sideBar.foreground": "#cccccc",                // normal item text
          "sideBarSectionHeader.foreground": "#999999",   // folder/group headers
          "sideBarTitle.foreground": "#aaaaaa",           // panel title
          // "list.activeSelectionForeground": "#8b4999",    // keep selected item readable
          // "list.activeSelectionBackground": "#000000",
          // "list.inactiveSelectionForeground": "#e97aff",  // unselected item
          // deafult: when you hover, slightly brighter pink (#e97aff) with black background (#000000)
          "list.hoverForeground": "#e97aff",             
          "list.hoverBackground": "#000000",
          
          // 3) Accent color and Status Bar
          "button.background": "#7e4264",
          "statusBar.foreground": "#ff79c6",
          "statusBar.background": "#321a28",              // background color 
          // "statusBar.noFolderBackground": "#0a9396",      // when no folder is open
          // "statusBar.debuggingBackground": "#ae2012",     // during debugging
          // "statusBar.debuggingForeground": "#ffffff"      // text during debugging

          
          // 4) Scrollbar 
          "scrollbarSlider.background": "#ff79c650",     // accent with transparency
          "scrollbarSlider.hoverBackground": "#ff79c680", // hover state
          "scrollbarSlider.activeBackground": "#ff79c6",   // when dragging
        
          // 5) focus border color
          "focusBorder": "#ff79c650",                 
          // "editor.focusedStackFrameHighlightBackground": "#ff79c680", 
          // "editor.lineHighlightBorder": "#00000000" 
          
          // 6) Adjust Window title
          "titleBar.activeBackground": "#ff79c640",   // background when window is active
          "titleBar.activeForeground": "#ffffff",     // text color when active

          "titleBar.inactiveBackground": "#91627caf", // background when window is inactive
          "titleBar.inactiveForeground": "#eeeeee"    // text color when inactive

        }
  },
  //dim text brightness
  "editor.tokenColorCustomizations": {
    "[Buzzokai GitHub Dark]": {
      "textMateRules": [
        // { // the normal text area  
        // "scope": ["source", "variable", "keyword", "comment", "string"],
        // "settings": { "foreground": "#bbbbbb"} // foreground is the top layer --->
        // },
        { // improve comment  
        "scope": ["comment", "punctuation.definition.comment"],
        "settings": { "foreground": "#9e924e"}  //read comment: aa8888
        },        
        { // General Markdown text
        "scope": ["text.html.markdown", "markup.para", "markup.text"],
        "settings": { "foreground": "#999999"}  // soft gray for regular text 
        },
        { // Bold text + the asterisks
        "scope": ["markup.bold", "punctuation.definition.bold.markdown"],
        "settings": { "foreground": "#79aae5"}   // yellow-orange
        },
        { // Italic text
        "scope": ["markup.italic"],
        "settings": { "foreground": "#6c99ce"}   
        },
        { // For inline code snippets like `const example = true`.
        "scope": "markup.inline.raw.string.markdown",
        "settings": { "foreground": "#ff9f3f"}
        },
        { // Markdown headings
        "scope": ["markup.heading","entity.name.section.markdown", "markup.heading.markdown"], 
        "settings": { "foreground": "#b29b45"}   // soft orange
        },
        {         // For bullet points and numbered lists.
        "scope": [ "markup.list.unnumbered", "markup.list.numbered"],
        "settings": { "foreground": "#7da1e3"}
        },
        {"scope":"markup.fenced_code.block.markdown",  // The code blocks ``` ```
        "settings": { "foreground": "#e6e6e6"}
        },
        {        
        "scope": "markup.quote.markdown",          // for blockquotes >
        "settings": { "foreground": "#67b259"} 
        }
      ]
    }
  }
}
```

3. Save the file (Ctrl+S / Cmd+S).
👉 Your active tab should now have a clear green highlight bar and background tint.
