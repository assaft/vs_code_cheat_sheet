# Cheat Sheet for VS Code

## Keyboard Bindings
* The bindings are configurable in the JSON file `keybindings.json` opened by CMD + SHIFT + P, and then selecting `Performance: Open Keyboard Shortcuts (JSON)`
* Below are the settings I added to the file. The main ones are:
  * Jump to previous/next cursor position by `CMD+OPTION+Left/Right`
  * Open file section by a double Shift press (based on [this](https://alexisvigoureux.medium.com/double-shift-key-in-visual-studio-code-eaef156b493f))

```json
[
    {
        "key": "alt+cmd+left",
        "command": "-workbench.action.previousEditor"
    },
    {
        "key": "alt+cmd+left",
        "command": "-workbench.action.terminal.focusPreviousPane",
        "when": "terminalFocus && terminalHasBeenCreated || terminalFocus && terminalProcessSupported"
    },
    {
        "key": "alt+cmd+right",
        "command": "-workbench.action.nextEditor"
    },
    {
        "key": "alt+cmd+right",
        "command": "-workbench.action.terminal.focusNextPane",
        "when": "terminalFocus && terminalHasBeenCreated || terminalFocus && terminalProcessSupported"
    },
    {
        "key": "alt+cmd+right",
        "command": "-quickInput.acceptInBackground",
        "when": "cursorAtEndOfQuickInputBox && inQuickInput && quickInputType == 'quickPick' || inQuickInput && !inputFocus && quickInputType == 'quickPick'"
    },
    {
        "key": "alt+cmd+left",
        "command": "workbench.action.navigateBack",
        "when": "canNavigateBack"
    },
    {
        "key": "ctrl+-",
        "command": "-workbench.action.navigateBack",
        "when": "canNavigateBack"
    },
    {
        "key": "alt+cmd+right",
        "command": "workbench.action.navigateForward",
        "when": "canNavigateForward"
    },
    {
        "key": "ctrl+shift+-",
        "command": "-workbench.action.navigateForward",
        "when": "canNavigateForward"
    },
    {
        "key": "shift shift",
        "command": "workbench.action.quickOpen"
    }
]

```
* It is also possible to set some of the bindings by the menu opened by `CMD + K, S` but not all of them (e.g. double shift)

## TouchPad Pinch in/out
Based on [this](https://stackoverflow.com/questions/30192884/is-it-possible-to-configure-control-scroll-wheel-to-increase-decrease-zoom-in), to make the font-size in the editor/console controlled by pinching in/out on the touch-pad:
* Press `CMD + SHIFT + P`, and then select `Performance: Open User Settings (JSON)`
* Add:
```json
    "editor.mouseWheelZoom": true,
    "terminal.integrated.mouseWheelZoom": true
```
