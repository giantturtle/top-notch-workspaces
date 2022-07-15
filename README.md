# top-notch-workspaces
Switches workspaces to horizontal layout, so workspace scrolling is like on macOS,
 moves the workspace indicator to the center of top bar and system date and time to the left side, 
 adds transparency to top bar, 
 puts an indicator on the panel signaling in which workspace you are, and give you the possibility of switching to another one and rearanging windows by dragging them to desiered workspace.
 This extension is based on built in GNOME extensions "horizontal-workspaces" and "workspace-indicator" by fmuellner https://gitlab.gnome.org/GNOME/gnome-shell-extensions


Default Ubuntu 20.04 top bar
![Default Ubuntu 20.04 top bar](https://github.com/giantturtle/top-notch-workspaces/blob/main/before-top-bar.png?raw=true)

After applying Top Notch Workspaces extension
![After applying extension](https://github.com/giantturtle/top-notch-workspaces/blob/main/after-top-bar.png?raw=true)


How it looks when using dark theme:
![After applying extension](https://github.com/giantturtle/top-notch-workspaces/blob/main/dark-theme-look.png?raw=true)


How it looks when using light theme:
![After applying extension](https://github.com/giantturtle/top-notch-workspaces/blob/main/light-theme-look.png?raw=true)


COnfiguration:

You can configure colors, borders and transparency by editing stylesheet.css

Example (current top bar transparency is set to 0.4):

.panel-transparency {
    background-color: rgba(0, 0, 0, 0.40);
} 


Or you can edit extension.js for more advanced changes.

For example, you want to move clock to be after system date-time indicator:

// only move the clock if it's in the centre box
    if ( children.indexOf(dateMenu.container) != -1 ) {
        centerBox.remove_actor(dateMenu.container);

        children = rightBox.get_children();
        rightBox.insert_child_at_index(dateMenu.container, children.length-1);
   } 
   
   
Or you can move notch indicator to be positioned right by changing lines:

//Workspace indicator in top bar    
    _indicator = new WorkspaceIndicator();
    Main.panel.addToStatusArea('workspace-indicator', _indicator,0, 'right');
