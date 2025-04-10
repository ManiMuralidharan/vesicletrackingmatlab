# vesicletrackingmatlab
# Author : Muralidharan Mani 
# Affiliation : University of Wisconsin-Madison
vesicletrackingmatlab
This MATLAB code for a particle tracking GUI step-by-step.

1. Save the Code as a MATLAB Function:

Open MATLAB.
Create a new script (File > New > Script).
Copy and paste the entire code into the script.
Save the script as particle_tracking_GUI.m. Make sure the filename matches the function name.
2. Run the Function:

In the MATLAB command window, type:
Matlab

particle_tracking_GUI
Press Enter. This will launch the particle tracking GUI.
3. Understanding the GUI:

Load Image Button:
Click this button to select a multi-frame, multi-channel TIFF image file (.tif).
The first frame of the image will be displayed in the axes.
The "Select ROI" button will become enabled.
Select ROI Button:
Click this button to draw a freehand region of interest (ROI) on the displayed image.
The ROI defines the area where particle intensities will be measured.
Once the ROI is defined, the "Track & Plot" button will become enabled.
Track & Plot Button:
Click this button to analyze the image stack and plot the intensity changes over time.
The code assumes the image stack contains alternating frames for two channels (e.g., frame 1 is channel 1, frame 2 is channel 2, frame 3 is channel 1, and so on).
It calculates the mean intensity within the selected ROI for each channel in each frame.
The intensities are normalized.
A new figure will open, displaying the intensity plots for both channels.
The "Save Data" button will become enabled.
Save Data Button:
Click this button to save the intensity data (mean intensities for each channel over time) to a CSV file.
Axes:
This area displays the loaded image.
4. Step-by-Step Usage:

Load Image:
Click the "Load Image" button.
Navigate to and select your multi-frame, multi-channel TIFF image file.
The first frame of the image will be displayed in the axes.
Select ROI:
Click the "Select ROI" button.
Draw a freehand region of interest (ROI) around the area you want to analyze.
Double-click to finish drawing the ROI.
Track & Plot:
Click the "Track & Plot" button.
Wait for the analysis to complete.
A new figure will appear, showing the intensity plots for both channels over time.
Save Data:
Click the "Save Data" button.
Choose a filename and location to save the intensity data as a CSV file.
Close the GUI and Plots:
Close the GUI and the intensity plot figure when you are finished.
Key Code Details:

Global Variables: The code uses global variables (imgStack, ROI, mask, intensities) to share data between the callback functions.
Image Loading: The loadImage function uses uigetfile to select a TIFF file and imfinfo and imread to load the image stack.
ROI Selection: The selectROI function uses drawfreehand to allow the user to draw an ROI and createMask to create a binary mask from the ROI.
Tracking and Plotting: The trackAndPlot function iterates through the image stack, calculates the mean intensity within the ROI for each channel, normalizes that data, and plots the results.
Saving Data: The saveData function uses uiputfile to select a save location and csvwrite to save the intensity data to a CSV file.
Error Handling: The code includes try-catch blocks to handle potential errors during file loading, ROI selection, tracking, and saving.
Multi-Channel Assumption: The code assumes that the multi-frame tiff has alternating channels. If channel 1 is frame 1, channel 2 is frame 2, channel 1 is frame 3, and so on.
Important Notes:

Image Processing Toolbox: This code relies on the MATLAB Image Processing Toolbox for functions like imfinfo, imread, drawfreehand, and createMask.
Multi-Channel TIFF: Make sure your TIFF image file is formatted with multiple frames and alternating channels as the code expects.
ROI Selection: The accuracy of the tracking results depends on the quality of the ROI selection.
Error Messages: Pay attention to any error messages that appear. They can help you troubleshoot issues.
Data Normalization: The intensity data is normalized to a range of 0 to 1, which can be useful for comparing different experiments.
File Permissions: Make sure MATLAB has the necessary read/write permissions for the files and folders you are working with.
