Terrain Choice: Maui, Hawaii

(Maui Terrain STL File)[https://drive.google.com/file/d/1zFuIcuqy5NvGFH_HfiYu-ng_1S_XGeXl/view?usp=share_link]

<img alt="Screenshot 2025-11-12 091917" src="https://github.com/user-attachments/assets/1240aa2c-9191-472f-b423-e7ad0e090962" />

<img alt="Screenshot 2025-11-12 091905" src="https://github.com/user-attachments/assets/1f006457-6520-410a-bc79-644cfad2c5ca" />

1st Print: 

![IMG_2435](https://github.com/user-attachments/assets/64e2a1f5-0fdb-4ed5-ab61-7d7ce31c33c7)
![IMG_2434](https://github.com/user-attachments/assets/6780b08e-9655-4859-a26c-ac1e0003cd72)



Issues: The issue with this print is that the base water is too thin. I fixed this issue by increasing the base height and decreasing the water drop on terrain2stl so the design looked the same while the base was less flimsy.

2nd Print: 

![IMG_2440](https://github.com/user-attachments/assets/1d5b3b6a-317f-44ee-966f-5f468bdbed80)
![IMG_2439](https://github.com/user-attachments/assets/221a523f-51b4-4fa9-8a4d-979b6c8c01a7)

# Topography Map of Breckendridge, Colorado 

[← Back to Main Page](README.md)

| | |
|---|---|
| ![](https://raw.githubusercontent.com/26wickhm/Wickham-Marisol-portfolio/main/assets/images/topography/finaltopo(1).jpg) | ![](https://raw.githubusercontent.com/26wickhm/Wickham-Marisol-portfolio/main/assets/images/topography/finaltopo(2).jpg) |
|


#### For this project, we utilized the MakeraCam machine to engrave topography maps into wood. I chose to do Breckendridge, Colorado. 
### FILES
[Download CNC Toolpath](https://github.com/26wickhm/Wickham-Marisol-portfolio/raw/main/assets/files/topography/breck_toolpath.zip)

[Download Aspire File (.crv3d)](https://raw.githubusercontent.com/26wickhm/Wickham-Marisol-portfolio/main/assets/files/topography/Aspire.crv3d)

---
_This workflow is inspired by one that Tom Dubick created_
## Workflow 
---
#### Terrain2STL (https://jthatch.com/Terrain2STL/)
1. Find location and define model area by creating a red box around the georgraphy wanted
2. Adjust water drop and base height (default of 1 to start)
3. Generate model to download stl as a zip file
#### Aspire
4. Open Aspire and create new file
- Job type: single side
- Width (x): 2.5 inches 
- Height (y): 3.5 inches
- Thickness (z): 1.0 inch
- Z Zero Position: Material surface (top)
- XY Datum Position: Bottom left
- Model Resolution: Standard
- Click "OK"
5. Import 3D Model
- Go to the modeling tab
- Click "Import a Component or 3D Model" and select your STL file
6. Orient 3D Model (Imported 3D Model > Transform)
- Rotation abouty Z axis: 0 degrees
- Unclick "lock XYZ ratio"
  - z = 1, x = 2.5, y = 3.5
  - Click apply and center model
  - Leave "Apply Perspective Along Z" unchecked
- Position and Import
7. Use Depth Below to ensure that it is equal to the Z's height size
- click import while on  Position Relative to the Modeling Plane
8. On the Component tab --> Component Properties
- Shape Height: 1.0
- Base Height: 0.25
- "Close"
9. Design tab --> 2D view
- click "Center" under the Alignment Tool
10. Design tab --> Create Vectors
- Draw rectangle around design (in this case, x = 2.5, y = 3.5)
  _need to do this to trim around the final product_
11. Toolpaths Tab
  - In the 2D view, click on the 3D model image
  - Click 3D roughing toolpath
    - Material: Hardwood
    - Tool: Large 25 mm End Flute Mill (Also known as a 1/8 End Mill)
    - Machine Limit Boundaries: Selected Vectors
    - Machining Allowance: 0.024
    - Strategy: 3D Raster
    - Name the Toolpath --> Calculate
   - 3D Finishing Toolpath
     - Material: Hardwood
     - Tool: 1/8 Ball Nose
     - Machine Limit Boundaries: Selected Vectors
     - Strategy: Raster, with a 0 degree input
     - Name the Toolpath --> Calculate
  - 2D Profile Toolpath Generation
      - Boundary: Select the rectangular boundary
      - Toolpath: 2D Roughing Toolpath
      - Start Depth: 0
      - Cut Depth: 0.5
      - Material: Hardwood
      - Tool: 1/8 End Mill
      - Machine Vectors: Select "On" and Direction "Climb"
      - Seperate Last Pass: leave unchecked
      - Name the Toolpath --> Calculate
  12. Preview all Toolpaths
        - save the G-code by clicking the Save Toolpath button
        - Machine: Carvera Desktop CNC machine
  #### MakeraCam
  13. After saving the toolpath to the Drive, download and import in on the PC next to the MakeraCam Machine
  - Upload the gcode after uploading the file
  - Offset (6,6) to allow for the wood to be cut in the middle
  - Run the gcode
 <p align="center">
  <img src="https://raw.githubusercontent.com/26wickhm/Wickham-Marisol-portfolio/main/assets/images/topography/makeracam_ss_beforemill.png" width="38%" />
  <img src="https://raw.githubusercontent.com/26wickhm/Wickham-Marisol-portfolio/main/assets/images/topography/toolpath.ss.beforeMakeraCam.png" width="38%" />
</p>




#### CHALLENGES
A struggle that I encountered was with the exportation of the Aspire files and loading them onto the machine. This was because I continued to export the gcodes and the file would be empty when I moved to the PC connected to the MakeraCam. This was because I was not exporting it as a cnc. I had tried multiple times as a .nc, but once I saved it as a .cnc, it uploaded very easily and all I had to do was home and offset the machine. 

### SUMMARY 
I think that the most important thing that I learned during this project is how to create the toolpath and navigate Aspire. I had to restart multiple times because of confusion, so I learned the process well and could do it without a workflow. If I were to change something, I think that I would make my zone more focused on the mountain range, and create more of a difference in the height. This would have added to the steepness of the mountain and pointed out each individual peak. In the future, I plan to stain this wood and mount it atop mulitple pieces of 1/8 inch wood. They will create a base slightly larger than the mountain. I will then engrave Breckenridge, Colorado on it and gift it to my parents. 
