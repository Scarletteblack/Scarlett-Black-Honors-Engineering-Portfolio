# Topology Mountain - Maui, HI

## Files: 
[Maui Terrain STL - 3D Print](https://drive.google.com/file/d/1zFuIcuqy5NvGFH_HfiYu-ng_1S_XGeXl/view?usp=share_link)

[CNC Toolpath](https://drive.google.com/file/d/1YeP-Ajn_wwSX-puco9e1-VFG__rGq-zf/view?usp=share_link)

[Aspire Toolpath](https://drive.google.com/file/d/1NpE2JmzP8RSheH2KM_3RyPsRKdhBAGzk/view?usp=share_link)

---

##### The 3D print was used to determine the proper water and drop height before milling. 
<img alt="Screenshot 2025-11-12 091917" src="https://github.com/user-attachments/assets/1240aa2c-9191-472f-b423-e7ad0e090962" />

<img alt="Screenshot 2025-12-19 at 12 20 02 AM" src="https://github.com/user-attachments/assets/3cebf860-6819-4c69-82f4-470dbf3d7cbf" />

![IMG_2580](https://github.com/user-attachments/assets/f7dfc375-c198-4e6e-b90a-b0cf66724588)

![IMG_2579](https://github.com/user-attachments/assets/6803d5a0-1823-4d35-8dc1-98cd03557aca)

---

## Milled Maui Topology 

![IMG_1810](https://github.com/user-attachments/assets/e965546a-5c23-4ca7-8bf8-b27e04fea91a)

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

---

## Issues Encountered 
 The only issue I encountered while working on this project was in the setup of MakeraCam prior to milling on the CNC machine. From a previous mill, Auto Set by Offset had been set to **Anchor 2** when it should have been set to **Anchor 1**. This caused the drill to go into the baseplate and off the toolpath. After stopping the machine and editing the settings, I restarted the mill. The second time the CNC machine successfully ran the g-code. Below is a photo of the setting after editing and where the drill went into the baseplate of the CNC machine.

 ![IMG_1798](https://github.com/user-attachments/assets/95928721-ea86-4592-9245-0363c961d46f)
 
![IMG_1799](https://github.com/user-attachments/assets/5d60df5a-fde3-42db-a005-52825a53aaba)

---

### Reflection 
My biggest takeaways from this project were learning how to create toolpaths in Aspire and using MakeraCam with the CNC machines. Due to trying multiple variations of Maui with various water and base heights, I not only became more comfortable with the Aspire and the various toolpaths, but also reinforced my skills on the 3D printers. Due to my issue with the setup in MakeraCam, I am much more familiar with the  processes in the software as well as the physical setup in the CNC machine. If I were to redo this project, I would want a larger square piece of wood. As my design was a square and I did not want extra space filled by just water, I was constrained to a smaller area for my mill. I plan on building a base out of small wood pieces and engraving the Island name into the wood.
