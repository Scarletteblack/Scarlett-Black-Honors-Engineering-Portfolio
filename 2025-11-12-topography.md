# Topology Mountain - Maui, HI

## Files: 
[Maui Terrain STL - 3D Print](https://drive.google.com/file/d/1zFuIcuqy5NvGFH_HfiYu-ng_1S_XGeXl/view?usp=share_link)

[CNC Toolpath](https://drive.google.com/file/d/1YeP-Ajn_wwSX-puco9e1-VFG__rGq-zf/view?usp=share_link)

---

##### The 3D print was used to determine the proper water and drop height before milling. 
<img alt="Screenshot 2025-11-12 091917" src="https://github.com/user-attachments/assets/1240aa2c-9191-472f-b423-e7ad0e090962" />

<img alt="Screenshot 2025-12-19 at 12 20 02 AM" src="https://github.com/user-attachments/assets/3cebf860-6819-4c69-82f4-470dbf3d7cbf" />


---

## Workflow
* *inspired by the workflow made by Tom Dubick*
### Terrain2STL  
[Terrain2STL Website](https://jthatch.com/Terrain2STL/)

1. Find the desired terrain and define the model area by drawing a red box around the selected terrain
2. Adjust the scale and dimensions of the red box as necessary
3. Adjust the water depth and base height 
4. Generate the model and download the STL file as a ZIP

### Aspire

**New File Setup**
1. Open Aspire and create a new file  
2. Set **Job Type** to *Single Sided*  
3. Enter the following dimensions:  
   - **Width (X):** 2.5 inches  
   - **Height (Y):** 3.5 inches  
   - **Thickness (Z):** 1.0 inch  
4. Set **Z Zero Position** to *Material Surface (Top)*  
5. Set **XY Datum Position** to *Bottom Left*
6. Choose **Model Resolution** to *Standard* 
7. Click **OK**

#### Importing and Orienting the 3D Model
1. Go to the **Modeling** tab  
2. Click **Import a Component or 3D Model** and select the STL file  
3. Open **Transform** under Imported 3D Model settings  
4. Set **Rotation about Z axis** to *0 degrees*  
5. Uncheck **Lock XYZ Ratio**  
6. Set dimensions to:  
   - **Z** = 1  
   - **X** = 2.5  
   - **Y** = 3.5  
7. Click **Apply** and center the model  
8. Leave **Apply Perspective Along Z** unchecked  


#### Positioning and Component Settings
1. Ensure **Depth Below** matches the Z height of the model  
2. While set to **Position Relative to the Modeling Plane**, click **Import**  
3. Go to the **Component** tab and open **Component Properties**  
4. Set:  
   - **Shape Height:** 1.0  
   - **Base Height:** 0.25  
5. Click **Close**

#### Design Setup
1. Switch to the **Design** tab and select **2D View**  
2. Click **Center** under the Alignment Tool  
3. Go to **Design → Create Vectors**
4. Draw a rectangle around the design with dimensions:  
   - **X** = 2.5  
   - **Y** = 3.5  

#### Toolpaths

##### 3D Roughing Toolpath
1. In the 2D view, select the 3D model image  
2. Click **3D Roughing Toolpath**  
3. Set:  
   - **Material** to Hardwood  
   - **Tool** to Large 25 mm End Flute Mill (1/8 End Mill)  
   - **Machine Limit Boundaries** to Selected Vectors  
   - **Machining Allowance** to 0.024  
   - **Strategy** to 3D Raster  
4. Name the toolpath and click **Calculate**

##### 3D Finishing Toolpath
1. Select **3D Finishing Toolpath**
2. Set:  
   - **Material** to Hardwood  
   - **Tool** to 1/8 Ball Nose  
   - **Machine Limit Boundaries** to Selected Vectors  
   - **Strategy** to Raster with a 0 degree angle  
3. Name the toolpath and click **Calculate**

##### 2D Profile Toolpath
1. Select the rectangular boundary  
2. Choose **2D Roughing Toolpath**  
3. Set:  
   - **Start Depth** to 0  
   - **Cut Depth** to 0.5  
   - **Material** to Hardwood  
   - **Tool** to 1/8 End Mill  
   - **Machine Vectors** to On  
   - **Direction** to Climb  
   - Leave **Separate Last Pass** unchecked  
4. Name the toolpath and click **Calculate**

##### Final Steps
1. Preview all toolpaths  
2. Save the G-code using **Save Toolpath**  
3. Select **Machine** as Carvera Desktop CNC Machine

### MakeraCam
1. Save the toolpath to the Fab Lab drive
2. Download and import it into MakeraCam on the PC by the CNC machine 
3. Upload the G-code  
4. Set the offset to **(6, 6)** to center the cut on the wood
5. Watch the toolpath preview
6. Run the G-code

<img alt="Screenshot 2025-12-19 at 1 00 00 AM" src="https://github.com/user-attachments/assets/60d5d363-f00d-47c4-92ad-80b0211627c2" />

<img alt="Screenshot 2025-12-19 at 12 59 36 AM" src="https://github.com/user-attachments/assets/746065af-faf5-4b71-8de9-ed8ac6535512" />


#### CHALLENGES
A struggle that I encountered was with the exportation of the Aspire files and loading them onto the machine. This was because I continued to export the gcodes and the file would be empty when I moved to the PC connected to the MakeraCam. This was because I was not exporting it as a cnc. I had tried multiple times as a .nc, but once I saved it as a .cnc, it uploaded very easily and all I had to do was home and offset the machine. 

### SUMMARY 
I think that the most important thing that I learned during this project is how to create the toolpath and navigate Aspire. I had to restart multiple times because of confusion, so I learned the process well and could do it without a workflow. If I were to change something, I think that I would make my zone more focused on the mountain range, and create more of a difference in the height. This would have added to the steepness of the mountain and pointed out each individual peak. In the future, I plan to stain this wood and mount it atop mulitple pieces of 1/8 inch wood. They will create a base slightly larger than the mountain. I will then engrave Breckenridge, Colorado on it and gift it to my parents. 
