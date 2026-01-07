



Features

Selection Catalog and "soft select"
- on the left side we currently show a single selected object e.g. an asteroid
	- if we have multiple objects selected, I want to see a list of all selected objects
	- clicking on one of these objects "soft selects" said object in the list and collapses it to show the same details a single selected object would show
	- by default the first opject in the list is "soft selected" and collapsed
	- only one object shall be "sof selected" and collapsed at a time
	- pressing c for context menu gives the usual list of kontext entries:
		- each object to single select
		- multi object interaction
		- and NEW single object interaktions for the soft selected object
			- using an interaktion on a soft selected object, does not clear the selection

Keybindings and other options
	- user should be able to freely configer his keybindings
		- standard
			- movement
				- move forward: w
				- move backwards: s
				- rotate left: a
				- rotate right: d
				- move to a specific point: RMB
				- interact: c
				- interact (hover): RMB
				- select: LMB
			- ui
				- open/close inventory: i
	- options
		- interact hover only for selected objects: yes/no (for example the player presses LMB while hovering over an unselected asteroid. Should the ship move to the asteroid oder open the context menu?)
		- 