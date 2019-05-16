
## Verification Plan

### Map
* Manually check if the map moves in the same direction of a mouse drag when a user clicks and drags (check 20 times)
* Manually check if there is a legend in the top right of the map notating the correct markers (a red marker for bathroom, blue circle notating user’s location) (check 20 times)
* Manually check if every marker shows up, is in its correct location (within a 10 feet error margin), and displays the correct information based on the information from the API (check 20 times)
* Manually check if every marker, including location marker, stays in the correct location within 10 feet even when the map moves (check 20 times)
* Manually check if the user location is correct within 10 feet and updates at least every second (check 20 times)
* Manually check the user is able to zoom the map using pinch to zoom gestures. 

### Directions

* Manually check that if the get directions button is clicked, the right side panel will show two stacked input boxes and a button with a right arrow below. (check 20 times)
* Manually check that the bottom input box is pre-populated with the marker bathroom’s address. (check 20 times)
* If the user allows their location to be used, manually check that the top input box is pre-populated with their current location information (check 20 times)
* If the user does not allow their location to be used, manually check that the top input box is empty.  (check 20 times)
* Manually check that the right arrow button cannot be clicked until both input boxes are filled with valid addresses or building names. (check 20 times)
* If the right arrow button is clicked, manually check that the right side panel updates into a list of walking directions from the starting location to the destination location. (check 20 times)
* Manually check that the walking directions start on the starting location and end on the bathroom selected (check 20 times)
* Manually check that the map shows the path of the directions from the bathroom marker to the user’s current location marker with a blue line. (check 20 times)
* Manually check that there is a left arrow for users to exit the directions functionality in the right side panel. Also check that when clicked, the view returns to the initial view of displaying bathrooms. (check 20 times)
* If the user gave their location, manually check that the map will be centered on the user’s location with a 1000 ft radius. (check 20 times)
* Manually check that when the user follows the path, the blue path line starts disappearing so that the blue line only connects the destination and the user’s current location. (check 20 times)
* Manually check that if the user takes a different path than the one given to them and is 30 ft away from any part of the path, the directions will recalibrate and show them a new list of instructions from their new location to the destination. (check 20 times)
* If the user did not give their location, manually check that the map shows the starting location, the destination, and the full path. (check 20 times)
* Manually check that when within 20 feet of their destination, the right side panel changes back to the location card decks and the blue line goes away. (check 20 times)

### Location Ask 
* The website must prompt the user if we can use their current location every time the page refreshes (each times the user refreshes the tab) with a popup in the top left corner of the map.
* If the user chooses “block”, the map remains as an overview of all of the UW Seattle campus, from Montlake cut to NE 45th st, with all bathrooms marked as markers on the map and in alphabetical order on the right side panel. 
* If the user chooses “allow”, the map zooms in on their current location, which will be in the center of the map, showing a 1000 feet radius around their current location, with bathrooms marked as markers on the map that are within that 1000 feet radius. The right side panel will show the list of all bathrooms from nearest to farthest from the user’s current location.
* Manual Testing and Integration Test: To test these requirements, we will be running manual tests. We will refresh the page multiple times in order to test if a popup appears prompting the user to use their current location. We can choose either to block or allow, and test if the correct results appear on the website. Then we can refresh the page and choose the other option to test the other result. 


### Filter
* The user will need to click on the “filter bathrooms” tab to view the drop down list
    * Manual testing: When dropdown list is not displayed, click on the “filter bathrooms” tab, pass if the drop down list appears, failed otherwise. (Check 20 times)
* The user will need to click on the “filter bathrooms” tab to close the drop down list
    * Manual testing: When dropdown list is  displayed, click on the “filter bathrooms” tab, pass if the drop down list appears, failed otherwise. (Check 20 times)
* All filtering options are unchecked by default.
    * Manual testing: When dropdown list is opened by a click, check if all filtering options are unchecked. (Check 20 times)
* Users should be able to check both single and multiple filtering options. When the user “checks” a filter, it should update the available bathrooms in the location cards and on the map within 1 second
    * Manual testing: When dropdown list is opened by a click, it should be available to click on both single and multiple filtering options. (Check 20 times)
    * Manual testing: When a filter option is setted, record the performance time if the available list and map update within a second. (Check 20 times)
* The user has the ability to filter bathrooms by whether it offers disability access, whether it requires a key, what gender it can accomodate (male, female, gender neutral). 
    * Manual testing: Visually spot all available filtering options in the dropdown list and the options should contain  whether it offers disability access, whether it requires a key, what gender it can accomodate (male, female, gender neutral). (Check 20 times)
* If any checked filtering standards are not met by the bathrooms, then the unqualified bathroom markers should not be displayed on the map or in the location cards.
    * Unit testing: Apply a set of random filtering standards, manually compare the returned results on map and in location cards with pre-made list of bathrooms with certain standards met. (Check 5 times)
* If all checked filtering standards are met, then the markers should be displayed on the map and in the location cards.
    * Unit testing: Apply a set of random filtering standards, manually compare the returned results on map and in location cards with pre-made list of bathrooms with certain standards met. (Check 5 times)

### General layout 
* The website will feature a map and a right side panel
    * Manual test: Load the website, observe if the website is in the stated structure. (Check 20 times)
The width ratio between map and the right side panel should be 7:3 respectively. They will both span the height of the screen. 
    * Code inspection: Load the page, inspect the code and check if the ratio is correct. (Check once a week)
* The page should always have the “OneRestroomAway” name and logo on the top of the right side panel. It will span the width of the right side panel and take up 1/7 of the height of the right side panel.
    * Code inspection manual testing: Load the page, spot the logo position, inspect the code and check for the height and width. (Check once a week)
* In the right side panel, from the top to the bottom, there is a logo section, a filter section and a location cards section. The ratio of the height of the logo, filter, and location cards section is 1:1:5 respectively. 
    * Code inspection and manual testing: Load the page, visually spot and check the locations, inspect the code and check for the height. (Check once a week)
* The logo section in the right side panel will always display the app name, “OneRestroomAway” along with the logo.
    * Manual testing: Load the page, visually spot the logo location. (Check 20 times)


### Location Cards/Right Side Panel
* The distance information on the each bathroom location card from bathroom should update as the user’s current location changes.
    * Manual testing: We can move the user’s current location physically and the distance should update on the location card. 
* The bathroom location cards on the sidebar must be sorted by the shortest distance to the current user, considering the user provided their current location.
    * Manual testing and code inspection: With code inspection, ensure bathrooms will be sorted in the correct order by checking code logic. 
* The side panel should be scrollable.
* The location cards should show the subsequent cards (farther restrooms) in the list as the user scrolls down.
    * * Manual testing: Ensure the side panel allows for scrolling of the location cards and farther restrooms are displayed. 

### API’s
* API must be able to store data on each bathroom’s geojson location, what floor(s) it is on, if it has disability access, if it requires a key, if it is male/female/gender neutral, what building it is in, what the address of that building is.
    * Every bathroom entry in the API should contain the bathroom’s geojson location, what floor(s) it is on, whether it has disability access, if it requires a key, the gender (male/female/neutral), what building it is in, and what the address of that building is. It should have “NA” if no information is available for a given feature.
* The only people who can access or change this API are admins with specific API tokens (keys)
    * Make sure no  one without API tokens (keys) can access the API. Try on 5 different laptops from the TE lab.  
* This API should be able to handle 5000 calls every 30 seconds from at most 1000 sources
    * Write a for loop test that will run 1000 times, within that for-loop it will call 5000 various random bathroom calls from the API. Do this 5 times to ensure. 
* Admins should be able to add, delete and edit data about each bathroom in this API
    * Manually test that admins (people with the API tokens) are able to add, delete, and edit information about any given bathroom from the API. Try all 3 things 10 times each. 
* Admins should be able to add new bathrooms and remove existing bathrooms from this api
    * Manually have admin delete a random bathroom from the existing bathrooms in the API
    * Manually have admin add the bathroom they just deleted in the previous verification to the existing bathrooms in the API
* Do the above 10 times, each with a randomly selected bathroom from the API

### Bathroom Marker/pop-up
* When a user clicks on a red location marker or clicks on a location on the right side panel, there will be a popup with:
Information on the details about the bathroom will include the building the bathroom is located in, what floor(s) it is on, distance from your current location (if user shares location to the webpage), whether it allows for disabled access, whether it requires a key to enter, whether the bathroom is gender neutral/male/female, and a “get directions” button
    * Clicking the “get directions” button allows the user to get directions from their current location to the bathroom they chose. (See “directions” requirements)
    * Click on a random red location marker and check that a popup appears with information about the bathroom will include the building the bathroom is located in, what floor(s) it is on, distance from your current location (if user shares location to the webpage), whether it allows for disabled access, whether it requires a key to enter, whether the bathroom is gender neutral/male/female, and a “get directions” button. Try this 20 times. 
    * Click on a random location card and check that a popup appears with information about the bathroom will include the building the bathroom is located in, what floor(s) it is on, distance from your current location (if user shares location to the webpage), whether it allows for disabled access, whether it requires a key to enter, whether the bathroom is gender neutral/male/female, and a “get directions” button. Try this 20 times. 
* When a user clicks on a red location marker or clicks on a location on the right side panel, that specific bathroom marker will turn into the same color as the pop up overlay.
    * Click on a red location marker, make sure that the bathroom marker color and the background color of the popup are the same. Try doing this on random bathroom location markers (about 20).
    * Click on a bathroom location card from the right side panel, make sure that the bathroom marker color and the background color of the popup are the same. Try doing this on random bathroom location markers (about 20).
* The map will NOT change and will remain the same as it was before the user clicked the red location marker
    * Click on a random red bathroom location marker and ensure that the map behind it remains the same as it was before the red marker was clicked. Try this 20 times. 
* Distance to the bathroom on the popup should be consistent with the distance information found on the sidebar.
    * Click on a random bathroom marker, the distance displayed on the popup from the user’s current location to the bathroom should be the same as the distance displayed on the sidebar. Try this 20 times. 
* Information on whether it allows for disabled access, whether it requires a key to enter, and whether the bathroom is gender neutral/male/female on the popup should stay consistent with the icons found on the sidebar location cards (view cards / icon section)
    * Click on a random bathroom marker, the features displayed on the popup should be the same as the features displayed on the sidebar bathroom location cards. Try this 20 times. 
* Pop up must show the correct building name as the bathroom the user selects from either the side panel or from the bathroom marker on the map
    * Manually click on a few random bathroom markers (about 20) from the map and check if the associated building is the same as what is shown in the popup
    * Manually click on a few random bathroom location card  (about 20) from the side panel and ensure if the associated building is the same as what is shown in the popup
*  If there is no information on features at a specific bathroom (such as disabled access, key required, gender neutral/male/female bathroom), then the corresponding feature icons should be displayed in grey with “Information unavailable” text.
* Ensure that feature icons information that has “NA” in the API is displayed in grey color and has “information unavailable” text for explanation
* If the user clicks anywhere outside of the marker’s popup, the popup will go away and the marker will go back to its regular red color.
This is unless another marker is clicked, in which case, the initial marker’s popup will go away and the initial marker will go back to its regular red color while the new marker’s popup will display and the new marker will change color to match the popup color.
    * Manually test by clicking outside of the marker’s popup area to ensure that the popup disappears and the bathroom marker goes back to its red color. Try clicking on various portions outside of the popup window to ensure this works. 
    * Manually test by clicking on another random bathroom marker on the map and ensuring that the new marker’s popup displays and the selected marker changes color to match that of the popup color. Also ensure that the previously selected bathroom marker returns to the red color. Try this 20 times. 


### Performance
* The page should be able to fully load in 30 seconds.
    * Manual testing: Record the time from the click on the link to when the browser shows the page is fully load. Compare the time with the setted 30 seconds goal. (Check 20 times)
* Anytime when a new filter is applied or an existing filter is removed, the map and the location cards should be refreshed within 1 second. (in filter section)
* Any click on the marker should respond with the details of the restroom in 5 seconds.
    * Manual testing: Record the time from the click on the marker to when the details of the restroom is shown. Compare the time with the setted 5 seconds goal. (Check 20 times)
* Moving the map should move correspondingly within 1 second
    * Manual testing: Record the time from the click and drag on the map to when the info is updated. Compare the time with the setted 1 second goal. (Check 20 times)
Scrolling down the card list should occur within 1 second
    * Manual testing: Record the time from the scrolling on the list to when the location cards are updated. Compare the time with the setted 1 second goal. (Check 20 times)
* Zooming should occur within 1 second
    * Manual testing: Record the time from the zooming action on the map to when the maps is updated. Compare the time with the setted 1 second goal. (Check 20 times)
* Directions should load within 10 seconds
    * Manual testing: Record the time from the click on the get direction button to when the directions to the selected bathroom is given. Compare the time with the setted 10 seconds goal. (Check 20 times)
* When click outside of bathroom pop up, it should remove pop up within 1 second
    * Manual testing: Record the time from the click outside of bathroom popup to when popup is removed. Compare the time with the setted 1 second goal. (Check 20 times)
* All of the above performance should be able to be completed on 5 different computers at the TE Lab.
    * Perform all above tests on 5 different TE Lab computer
