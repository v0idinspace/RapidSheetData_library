# Overview
The Rapid Sheet Data Unity3D client library sends WWW requests to the web service and deserializes the returned JSON string into the desired C# class instances. The core functionality of the library is contained within the Rapid Sheet Data Asset which can be created using Unity’s create menu, much like all other assets, and can be easily configured in the inspector.

For more information check the complete Rapid Sheet Data documentation at http://www.voidinspace.com/rapid-sheet-data/.

# Install the library
To install the library to your project, simply copy the ‘RapidSheetData’ folder under ‘Assets’ to your project. You can also import the library from the .unitypackage located under Builds (/Builds/RapidSheetData_v1.0.0.unitypackage).

# Setup the Google sheets for your data
Create a new sheet and share it with your service e-mail address (you'll have that if you setup a service account ID for the Rapid Sheet Data service. https://github.com/dotv0id/RapidSheetData_service).
Add some data in your sheet. The first row or column will be the name of the properties or variables your data will be deserialized to in your target classes. 

# Create some data classes
These are the classes where Rapid Sheet Data will deserialize your data to. Make sure the classes' public variables or properties have the same name as the fields in the first row or column in the Google sheet. Add the [RSDObject] attribute to your classes.

# Configure the Rapid Sheet Data Asset
Create a new Rapid Sheet Data asset using the standard create menu in the Unity3D editor. You can configure the asset in the inspector. Add your Server URL and the ID of your Google spreadsheet. Add your sheet configurations in the list. The first field is the name of the sheet. The second defines which class to use to deserialize the data to and the last field defines if the data should be read by column or row.

# Initialize the asset
Add a reference to your asset in the script you want to use it. Call the Init() function to initialize it and the PullData() function to pull data from your sheets in run time. Use the GetSheet<T>() and GetFromSheet<T>() functions to get the data.

Take a look at the example provided in the library for more details.