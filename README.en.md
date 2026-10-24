# ProtoboardMaster

**[简体中文](README.md) | [English](README.en.md)**

**[Open online](https://shenyang8103.github.io/ProtoboardMaster/) · [Repository](https://github.com/shenyang8103/ProtoboardMaster) · [Download HTML](https://github.com/shenyang8103/ProtoboardMaster/blob/main/ProtoboardMaster.html)**

A browser-based breadboard and perfboard layout tool for electronics hobbyists. Place components, connect jumper wires, plan solder traces on the back, and inspect physical connectivity. The complete app runs offline from one HTML file, with no installation or network connection required.

It helps you plan assembly and check a layout before soldering. It does not simulate circuits or design PCBs. The application interface is currently in Chinese.

## Getting started

1. Download or keep the complete [ProtoboardMaster.html](ProtoboardMaster.html) file and open it in a desktop browser.
2. Click the gray hint next to the workbench title to switch between breadboard and perfboard modes.
3. Try the example, or create a blank board and click holes to place components.
4. Use Save Project to back up your work. Export images for assembly reference or sharing.

Only one editor runs at a time. Switching with unsaved changes offers Save and Switch, Discard and Switch, or Cancel. A failed or cancelled save keeps the current editor open. Discard clears that editor's current local draft, without deleting saved project files. Switching releases the previous editor's undo history and system file target; returning can restore a draft that was not discarded.

## Features

| Breadboard | Perfboard |
| --- | --- |
| 1–8 boards, drag to reorder, cross-board jumpers | Adjustable rows and columns, draggable resize preview and affected-object list |
| Configurable main rows, power rails and rail segments | Front/back views, design mirroring and faint opposite-side reference |
| Resistors, capacitors, diodes, transistors, DIP ICs and signal terminals | Standard components, DIP ICs, custom components and pin adjustments |
| Seven jumper colors, copy, single-pin reconnect and group movement | Red front jumpers, blue back jumpers and gray solder traces |
| Connected-hole highlighting, hole occupancy and conflict checks | Full-network hover highlighting, draggable straight solder segments with reconnecting traces |
| Full-layout PNG and per-board PNG/ZIP | Front/back PNG/ZIP and JSON/CSV connectivity lists |

Both modes support repeated placement, editable properties, direct dragging, one-step undo, project files and local drafts. Component internals do not automatically connect their pins. Matching signal-terminal labels do not create an electrical connection.

## Mouse and keyboard

| Action | Result |
| --- | --- |
| Left click | Select a hole/object or place a component |
| Drag a selected object | Move it; endpoint rings allow single-pin adjustment for two-pin components and jumpers |
| Drag on empty space / Ctrl+click | Box select / toggle selection; Ctrl+box select adds objects in perfboard mode |
| Short right click | During two-point placement, clear the first point while keeping the tool and settings; without a first point, exit the tool; in selection mode, clear selection |
| Right drag / mouse wheel | Pan / zoom; panning preserves the placement start point |
| Esc | Exit the current edit or clear selection |
| M / C / Del | Move / copy a single selected object / delete selected objects |
| Space | Change orientation for supported components during placement, movement or copying; swap diode polarity |
| Ctrl+Z / Ctrl+S | Undo one step / save the project |
| F in perfboard mode | Switch sides while in selection/view mode |

Text fields, dropdowns and dialogs retain their own input handling. Undo stores one completed edit. Cancelling a preview or clearing the first placement point does not consume that undo step.

## Perfboard connection rules

- Component pins and jumper endpoints physically occupy holes. One physical endpoint per hole is allowed, checked across both sides.
- Solder exists only on the back and does not occupy the hole. An empty hole with solder can accept a pin or jumper endpoint, or become a branch of another solder trace.
- Solder passing through the same pad is electrically connected; duplicate edges merge. Jumpers connect only at their endpoints, not where their bodies cross.
- The back design view defaults to unmirrored. Back image export defaults to mirrored for soldering reference. These settings are independent.

## Saving and compatibility

- Breadboard projects use `.breadboard.json`, supporting legacy single-board v1 and multi-board v2. Perfboard projects use `.perfboard.json`. Open each file in its matching editor; layouts are not converted automatically.
- Where supported, the system save dialog lets you choose a file location and later saves reuse that file within the current session. Other browsers use downloads. If you cancel the browser download, save again.
- Local drafts support recovery, not permanent backup. Drafts may not be shared across browsers, addresses, ports or offline file paths. When moving from the old filename to `ProtoboardMaster.html`, transfer your work using saved project files; automatic draft migration is not guaranteed.
- Drafts omit temporary previews, selections, undo history and system file handles. Keep project-file backups.
- Exported images are assembly references, not guaranteed physical-scale printouts. Connectivity lists describe physical connections and are not simulation files.

The first-release feature plan is implemented. Direct offline use in your regular browser, native file saving and comparison with a physical assembly still need user acceptance testing. This repository continues the original Breadboard_Tool project under the ProtoboardMaster name. The old project-site URL is not automatically redirected. Local drafts may not migrate between addresses; save project files and reopen them at the new URL.

## GitHub Pages

The site uses the root of the main branch. No installation or build is required. index.html and ProtoboardMaster.html contain the same complete application. Download ProtoboardMaster.html using GitHub’s raw-file download button for offline use.
