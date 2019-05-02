# Architecture Specification

## Bathroom
The component that contains and displays the information about the bathroom.

####  Properties: 

| Name | Type | Description |
| ----- | ------| ------------|
|longitude | double | Signed decimal degree without compass direction, where negative indicates west |
|latitude | double | Signed decimal degree without compass direction, where negative indicates south |
|distanceToUser | int | Distance from the user to the bathroom |
| male | boolean | True if the bathroom is men’s |
| female  | boolean | True if the bathroom is women’s |
| genderNeutral | boolean | True if the bathroom is gender neutral |
| accessible | boolean | True if the bathroom has disability access |
| key | boolean | True if the bathroom requires key to enter |


#### Functionality:

| Name | Parameter | Return | Behavior |
| ---- | -----| -----| --- |
|isMale() | None | boolean | Check if the bathroom is men’s |
| isFemale() | None | boolean | Check if the bathroom is women’s |
| isGenderNeutral() | None | boolean | Check if the bathroom is gender neutral |
| isAccessible() | None | boolean | Check if the bathroom has disability access |
| isKey() | None | boolean | Check if the bathroom requires key | 
| getDistance() | Latitude and Longitude from the input, Separate parameters of double, double or an Array<double> | int | Calculate distance between the current location of the user and the bathroom |

#### Connection:
Input: 
Input -- provides the user’s precise location
API -- provides many bathroom information
Output: 
SidePanel -- display the bathroom info to the side panel

--------------------------
## Map
The component that renders the map with various bathroom locations that the user can see on the webpage. 

#### Functionality:
getBathroomLocation -> gets the bathroom location from the API component
createBathroomMarker -> creates a bathroom marker for the map
setBathroomLocation -> sets the bathroom locations on a new layer on the map

getBathroomDetails -> gets the bathroom details based on if the user clicks the bathroom marker
getDirections -> gets the directions from the getUserLocation to the getBathroomDetails, specifically the location from the getBathroomDetails, and uses google api to map out the directions (only if user shares their locaiton)
updateDirections -> updates the directions based on user movement while the web page is still open (only if user shares their location)

getUserLocation -> gets the user location (if provided) from the Input component
createUserLocationMarker -> creates the user location marker for the map
setUserLocation -> sets the user location (if provided) on a new layer on the map

generateMap -> generates the initial map layer based on the the base map layer from the Google Maps API and the OneRestroomAway API that we are creating

#### Connection: 
Input: provides the user’s precise location, the bathroom locations
Output: the map with the map base layer, bathroom markers layer, and user location marker layer (if user location is shared), bathroom details if called upon

--------------------------
## Input and Output
The input component manages the connection between the user interactivity and rendering the required information on the webpage. This component takes in all the user input on the web page and sends the user input to the corresponding component that is associated with the input, such as the Side Panel or Map. 

#### Functionality:
getUserClick -> gets the user click interaction from the web page 
getUserLocation -> gets the user location

renderMap -> renders the map on the user web page
renderSidePanel -> renders the side panel on the user web page
  
#### Connection:
Input: takes the user interaction from the web page and sends it to corresponding component
Output: renders the output on the web page

--------------------------
## Side Panel
The component that renders the sidebar containing information about each bathroom

#### Functionality:
getUserLocation -> gets the user location
getDistance -> gets the user current location and calculates the distance in feet/miles away between the user’s current location and the bathroom’s location
orderBy -> order location card by distance from user, or alphabetically
filters -> filter bathrooms based on features selected

#### Connection:
Input: User’s Current Location, data about each bathroom from bathroom component or API
Output: Render bathroom cards for each bathroom on the sidebar panel, each bathroom card will have all bathroom information, order will update based on user location, interacts with Input and Output component to render sidebar

------------------------

## API 

#### Retriever
* Location retriever - input is bathroom ID, output is the bathroom’s location
This will give back the bathroom’s geojson location
* Accessibility access retriver - input is bathroom ID, output is a boolean
Returns a boolean based on if the accessibility access is True / False
* Key access retriever  - input is bathroom ID, output is a boolean 
Returns a boolean based on if the key access is needed (True) or not (False)
* Gender retriever  - input is bathroom ID, output is a string 
Returns a string based on if the bathroom is “male”, “female”, or “neutral”

#### Add

Bathroom adder - Input is the ID, location, accessibility access, key access, and gender. The information is then saved in our api / database

#### Edit
* Location editor - input is bathroom ID
This will change the bathroom’s geojson location
* Accessibility access editor - input is bathroom ID 
This will change the bathroom’s accessibility access information
* Key access editor  - input is bathroom ID
This will change the bathroom’s key access information
* Gender editor  - input is bathroom ID 
This will change the bathroom’s gender information

#### Delete
Bathroom deleter - Input is the ID. All information about the bathroom is then deleted from our api / database
