# OneRestroomAway Requirements

## API
- API must be able to store data on each bathroom’s geojson location, what floor(s) it is on, if it has disability access, if it requires a key, if it is male/female/gender neutral, what building it is in, what the address of that building is.
- Should be able to add, delete and edit data about each bathroom in this API
- Should be able to add new bathrooms and remove existing bathrooms from this api

## General Layout
- The website will feature a map and a right side panel
- The width ratio between map and the right side panel should be around 7:3 respectively. They will both span the height of the screen.
- The page should always have the “OneRestroomAway” name and logo on the top of the right side panel. It will span the width of the right side panel.
- In the right side panel, from the top to the bottom, there is a logo section, a filter section and a location cards section. The ratio of the height of the logo, filter, and location cards section is 1:1:3 respectively.
- The logo section in the right side panel will always display the app name, “OneRestroomAway” along with the logo.

## Asking for Location
- The website must prompt the user if we can use their current location every time the page refreshes (each times the user refreshes the tab) with a popup in the top left corner of the map.
- The popup will ask “www.OneRestroomAway.com wants to know your location” The user will be given two options: allow button and block button.
- When the page loads, before the user answers the popup, the map will start off as an overview of all of the UW Seattle campus, from Montlake cut to NE 45th st, with all bathrooms marked as markers on the map and in alphabetical order on the right side panel.
- If the user chooses “block”, the map remains as an overview of all of the UW Seattle campus, from Montlake cut to NE 45th st, with all bathrooms marked as markers on the map and in alphabetical order on the right side panel.
- If the user chooses “allow”, the map zooms in on their current location, which will be in the center of the map, showing at least a 100 feet radius around their current location, with bathrooms marked as markers on the map that are within 100 feet radius. The right side panel will show the list of all bathrooms from nearest to farthest from the user’s current location.

## Map
- User should be able to move the map via click and drag.
- There will be a legend in the top right of the map, notating the “bathroom” markers and “your location” marker.
- Map will always have a layer with all of the red markers notating bathroom, and always have a blue dot notating the user’s location (if user allows webpage to use their location).
   - The red markers and current location (if user allows webpage to use their location) will always be on the correct geojson locations even when the map moves.
   - All markers will never be further than 500 feet of their actual location
   - The user’s location will change on the map continuously when the user moves (given the user gave their location).

## Bathroom Markers / Popup
- When a user clicks on a red location marker or clicks on a location on the right side panel, there will be a popup with:
   - Information on the details about the bathroom will include the building the bathroom is located in, what floor(s) it is on, distance from your current location (if user shares location to the webpage), whether it allows for disabled access, whether it requires a key to enter, whether the bathroom is gender neutral/male/female, and a “get directions” button
- Clicking the “get directions” button allows the user to get directions from their current location to the bathroom they chose. (See “directions” requirements)
- Distance to the bathroom on the popup should be consistent with the distance information found on the sidebar.
- Information on whether it allows for disabled access, whether it requires a key to enter, and whether the bathroom is gender neutral/male/female on the popup should stay consistent with the icons found on the sidebar location cards (view cards / icon section)
- Pop up must show the correct building name as the bathroom the user selects from either the side panel or from the bathroom marker on the map
- If there is no information on features at a specific bathroom (such as disabled access, key required, gender neutral/male/female bathroom), then the corresponding feature icons should be displayed in grey with “Information unavailable” text.
- If the user clicks anywhere outside of the marker’s popup, the popup will go away
   - This is unless another marker is clicked, in which case, the initial marker’s popup will go away while the new marker’s popup will display

## Filtering
- The user will need to click on the “filter bathrooms” tab to view the drop down list
- The user will need to click on the “filter bathrooms” tab to close the drop down list
- All filtering options are unchecked by default.
- Users should be able to check both single and multiple filtering options.
- The user has the ability to filter bathrooms by whether it offers disability access, whether it requires a key, what gender it can accomodate (male, female, gender neutral).
- If any checked filtering standards are not met by the bathrooms, then the unqualified bathroom markers should not be displayed on the map or in the location cards.
- If all checked filtering standards are met, then the markers should be displayed on the map and in the location cards.

## Location Cards / Right Side Panel
- The distance information on each bathroom location card from the bathroom should update as the user’s current location changes.
- Each card in the bathroom location card section should indicate whether a bathroom is accessible to disabled people, what gender options it has, and whether it requires a key with associated identifiers.
- The bathroom location cards on the sidebar must be sorted by the shortest distance to the current user, considering the user provided their current location.
- The side panel with the list of restroom includes the names of the restroom, what floor the bathroom is on, the approximate distance from your location (in miles/feet), and the street that the building the bathroom is located in.
- The location cards should be scrollable.

## Directions
- If the user clicks on the get directions button, the right side panel will show two stacked input boxes and a button with a right arrow below. The bottom input box (final destination box) will be pre populated with the marker bathroom’s address.
- If the user allows their location to be used, the top input box will be pre-populated with their current location information
- If the user does not allow their location to be used, the top input box will be initially empty, the user will need to fill that out.
- The right arrow button cannot be clicked unless both input boxes are filled with valid addresses or building names.
- If the user clicks the right arrow button, the right side panel will update into a list of walking directions from the starting location to the destination location.
- Users must be given walking directions from their starting location to the bathroom selected.
- The map will show the path of the directions to the building where the bathroom is located from the user’s current location marker with a blue line.
- There will be a left arrow for users to exit the directions functionality in the right side panel. When clicked, the view must return to the initial view of displaying bathrooms.
- If the user gave their location, the map will be centered on the user’s location with at least a 150 ft radius. As the user follows the path, the blue path line will start disappearing so that the blue line only connects the destination and the user’s current location.
- If the user takes a different path than the one given to them, the directions will recalibrate and show them a new list of instructions from their new location to the destination.
- If the user did not give their location, the map must show the starting location the user inputted, the bathroom destination, and the full path.

## Icons
- Wheelchair icon on a specific bathroom card in the side panel denotes that the restroom allows for disability access. This must be on every card panel that represents a bathroom with disability access.
- Key icon on a specific bathroom card in the side panel denotes that the restroom requires a key to enter the bathroom and/or the building. This must be on every card panel that represents a bathroom that requires a key to enter.
- Male icon on a specific bathroom card in the side panel denotes that the restroom is a male restroom. This must be on every card panel that represents a male bathroom.
- Female icon on a specific bathroom card in the side panel denotes that the restroom is a female restroom. This must be on every card panel that represents a female bathroom.
- Male and Female icon together on a specific bathroom card in the side panel denotes that the bathroom is a gender neutral bathroom. This must be on every card panel that represents a gender neutral bathroom.
- A red marker on the map denotes a bathroom location
- A blue circle on the map denotes user’s current location (if user provides their location to the webpage). If the user does not provide their location to the webpage, then their location (the blue dot) will not be present on the map.
- The icons on a marker’s pop up should match those that are used for the marker’s respective location card in the right side panel
- The legend in the upper right hand corner of the map should include the image of the red marker icon and blue circle icon and show what each denotes (depending on if the user allows for location tracking). This legend should be present at all times on the map

## Performance
- The page should be able to fully load in at least 3 minutes.
- Anytime when a new filter is applied or an existing filter is removed, the map and the location cards should be refreshed within at least 1 minute.
- Any click on the marker should respond with the details of the restroom in at least 1 minute.
- Moving the map should move correspondingly within 1 minute
- Scrolling down the card list should occur within 1 minute
- Zooming should occur within 1 minute
- Directions should load within minute
-  When click outside of bathroom pop up, it should remove pop up within 1 minute

## Map zooming
- Users must be able to zoom the map by performing pinch to zoom gestures on the touchpad.
