## 🔧 Monokai Dimmed Customized:  

### 1. Add the active tab highlight

1. Open Settings (JSON view):
    Press Ctrl + Shift + P (or Cmd + Shift + P on Mac).
    Type “Preferences: Open Settings (JSON)” → hit Enter.
    👉 This opens your settings.json file.
  
2. Find your "**workbench.colorCustomizations**" section and copy the section of **workbench.colorCustomizations** from snippet below to your section:  

```json
{
    "security.workspace.trust.untrustedFiles": "prompt",  
    // settting option: "open", "preview", "newWindow", "prompt"
    // "open" → VS Code will open files right away, no questions asked.
    // "preview" → VS Code will open them in a safe preview mode (read-only, limited features).
    // "newWindow" → Files open in a separate window that runs with restrictions.
    // "prompt" (default) → VS Code asks you what you want to do.

    "window.commandCenter": false,
    "git.openRepositoryInParentFolders": "never",
    "workbench.colorTheme": "Monokai Dimmed",
    "editor.fontVariations": false,
    "editor.fontWeight": "normal",
    "editor.fontLigatures": false,
    "workbench.preferredDarkColorTheme": "Monokai Dimmed",
    "json.schemas": [],
    /// ---> Semantic tokens must be **outside** and will be applied globally <---
    "editor.semanticTokenColorCustomizations": {
        "enabled": true,
        "rules": {
            "module": {"foreground": "#af9edf", "fontStyle": ""},  
            // note the modifier syntax
            "class": {"foreground": "#9b86d8","fontStyle": ""},
            }          
        },
    "workbench.colorCustomizations": {
        "[Monokai Dimmed]": {
            // Progress/Activity Indicator
            // "progressBar.background": "#FF69B4",
            
            // 1) Make tab more vivid  --> Set it to bright blue with semi-tranparaent blue fill
            "tab.activeBorderTop": "#74b9ff",       // Dodger Blue top glow --> to dimmed: #53a8ff
            "tab.activeBorder": "#74b9ff",          // Dodger Blue bottom glow
            "tab.activeBackground": "#188afd30",    // semi-transparent blue fill
            "tab.activeForeground": "#ffffff",      // white text stays crisp 
            // "tab.inactiveForeground": "#356255",    // inactive tab 
            "tab.inactiveBackground": "#3a3a3a",    // inactive tab 
            
            
            // 2) Explorer / side bar text
            "activityBar.foreground": "#52a8ff",             // activity bar icons (the vertical bar on the far left side)
            "activityBar.inactiveForeground": "#3975b2",
            "sideBarTitle.foreground": "#52a8ff",            // sidebar title             
            "sideBar.foreground": "#cccccc",                 // normal item text - slightly dim to #cccccc
            "list.activeSelectionForeground": "#ffffff",     // keep selected item readable
            "list.activeSelectionBackground": "#116bf3b0",   // keep selected item readable
            "list.inactiveSelectionForeground": "#aaaaaa",   // unselected dim
        
            // "list.inactiveSelectionBackground": "#000000" 

            // 3) Accent color in Explorer/side bar text
            "list.hoverForeground": "#ffffff",         // when you hover, slightly brighter
            "list.hoverBackground": "#116bf3b0",            

            // 4) Scrollbar 
            "scrollbarSlider.background": "#359aff54",     // accent with transparency
            "scrollbarSlider.hoverBackground": "#359aff54", // hover state
            "scrollbarSlider.activeBackground": "#359aff ,             

            // 5) Notebook background --> lighter:#26292f  <> darker: #24272d 
            "notebook.editorBackground":"#26292f",  
            "notebook.cellEditorBackground": "#1b1b1b",  // Optional: cell background
            // "notebook.outputContainerBackgroundColor": "#202020", // Optional: output background
            // "notebook.cellBorderColor": "#3C3C3C"    // Optional: cell border highlight
           
            // 6) Adjust Window title
          
            "titleBar.activeBackground": "#203f66",   // background when window is active
            "titleBar.activeForeground": "#ffffff",   // text color when active
            "titleBar.inactiveBackground": "#3975b280", // background when window is inactive
            "titleBar.inactiveForeground": "#eeeeee"  // text color when inactive
        },
    },

    "editor.tokenColorCustomizations": {
        "[Monokai Dimmed]": {
            "textMateRules": [
                // -->> For markup language <<-- //
                { // Bold text + the asterisks
                "scope": ["markup.bold", "punctuation.definition.bold.markdown"],
                "settings": { "foreground": "#79aae5"} 
                },
                { // Italic text
                "scope": ["markup.italic", "punctuation.definition.italic.markdown"],
                "settings": { "foreground": "#6c99ce"} 
                },   
                { // For inline code snippets like `const example = true`.
                "scope": "markup.inline.raw.string.markdown",
                // "settings": { "foreground": "#ff79c6"}      // bright orange
                "settings": { "foreground": "#ff79c6"}    // bright pink                                               
                },
                {  // for blockquotes >>>>
                "scope": "markup.quote.markdown",        
                "settings": { "foreground": "#7da1e3"}                     
                },
            ],
        }
    },        
    "explorer.confirmDelete": false,
    "editor.wrapOnEscapedLineFeeds": true,
    "workbench.editor.enablePreview": false,
    "chat.promptFilesRecommendations": {}
}               
 
```

3. Save the file (Ctrl+S / Cmd+S).
👉 Your active tab should now have a clear green highlight bar and background tint.

