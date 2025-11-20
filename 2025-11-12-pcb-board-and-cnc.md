---
title: "PCB Board & CNC"
---

## Workflow
### **MakeraCam**
#### **Preparing the Design**

1. **Start a New Project**
   * Open a new 3D project.
   * Set the material to PCB via **Edit → Material → PCB**.
   * Enter the material dimensions:
     * X: 127 mm
     * Y: 101 mm
     * Z: 1.7 mm

2. **Download Required Files from the Fab Drive (Blue Folder: “Dubick”)**
   * Resistance1-F_Cu.gbr
   * Resistance1-PTH.drl
   * Resistance1-Edge_Cuts.gbr

3. **Import Files into MakeraCAM**
   * **File → Import PCB** → Downloads → Resistance1-Edge_Cuts.gbr → Open
   * Repeat for:
     • Resistance1-PTH.drl
     • Resistance1-F_Cu.gbr

4. **Set the Anchor Point (Lower Left Corner)**
   * Select the entire design (drag to highlight everything).
   * Press the **“m”** key.
   * In the anchor pop-up, select the lower-left corner in the diagram (top right of the screen).
   * Under **Location**, enter:
     * X: 6
     * Y: 6
   * The design should shift to align with the axes and be offset from the material edge.

<img alt="MakeraCam 1 - everything selected" src="https://github.com/user-attachments/assets/0239808e-1188-4e53-b6b0-8023ebe57168" />

---

#### **Toolpath Creation**

##### **Copper Removal (2D Pocket)**

1. In the **2D Layers** panel, hide:
   * Resistance1-F_Cu.gbr_pad
   * Resistance1-PTH.drl_0.900 mm
   * Resistance1-PTH.drl_1.400 mm
2. Go to **2D Path → 2D Pocket**.
3. Select all visible parts of the design.
4. Set **End Depth** to **0.05 mm**.
5. Add the following tools:
   * 8 mm Corn
   * 0.2 mm × 30° Engraving (Metal)
6. Click **Calculate**.

<img alt="MakeraCam 2 - drilling" src="https://github.com/user-attachments/assets/3c6c48d5-8ad8-407c-b86e-234a91c118fe" />



##### **Drilling Holes**

1. Go to **2D Path → 2D Drilling**.
2. In **2D Layers**, hide all but the layer with drill holes.
3. Set **End Depth** to **1.7 mm**.
4. Add tool: **8 mm Corn**.
5. Click **Calculate**.

<img alt="MakeraCam 3 - Drilling" src="https://github.com/user-attachments/assets/06870a58-8bcf-4835-b385-67e2d4d1711e" />


##### **Cutting the Outline**

1. Go to **2D Path → 2D Contour**.
2. In **2D Layers**, only show **Resistance1-Edge_Cuts.gbr**.
3. Set:
   * **End Depth**: 1.7 mm
   * **Strategy**: Outside
4. Under **Tabs**, select:
   * Type: Custom
   * Shape: Triangle
   * Click **Add**, then place 3 tabs evenly spaced along the board outline.
5. Add tool: **8 mm Corn**.
6. Click **Calculate**.

<img alt="MakeraCam 4 - Contour" src="https://github.com/user-attachments/assets/781ef867-875e-47b8-9546-3a9ce09f02bb" />

---

<img alt="MakeraCam 5 - full board" src="https://github.com/user-attachments/assets/9b8382f1-d685-4f5c-b205-15c2aaaa77c5" />
<img alt="MakeraCam 6 - Preview" src="https://github.com/user-attachments/assets/7e0a352e-050d-472e-b2f9-ce5bbd98c7cd" />


---

#### **Exporting the File**
* To export the toolpath directly: **Path → Export → Export**
  or
* To edit later on the milling machine computer:
  **File → Save As**, choose .mkc format and save in Downloads.
* Upload the final file to your folder in the Fab Google Drive.
You can download my G-code file here: [BlackSResistorPracticegcode](https://github.com/user-attachments/files/23658036/BlackSResistorPracticegcode.zip)




### **Using the CNC Machine**
#### **Installing the Material**

1. Slightly loosen all bolts on the machine bed except the three that are fully inside the metal jig/holder.
  *(Use the screwdriver on the right side of the machine.)*
2. If there’s already a copper board on the bed with a design in the lower-left corner:
   * Remove and reposition it if possible, or replace it with a new board.
3. Place the PCB on the CNC bed so your design will be located in the bottom-left corner, matching the orientation from MakeraCAM.
4. Adjust the rectangular metal clamps:
  * Keep the bolts in place.
  * Slide and rotate each rectangular holder so the PCB can be placed under the loosened bolts.
  * Once the PCB is in position, rotate/move the rectangular holders back so the short end with the slot is pressing against the material, securing it.
5. Tighten all loosened bolts so the PCB is held firmly in place—secure, but not overly tight.

---

#### **Running the File**

1. Download your `.nc` G-code file from the Fab Google Drive.
2. Open Cavera Controller on the milling machine.
3. Upload the file:

   * Click **Open File (top left)** → **Upload File** → choose your file from Downloads → **Upload & Select**.
4. Set the machine to idle:

   * Click **Idle (top left)** → choose the correct **COM Port**.
5. Open additional options:

   * **Top right dropdown → Display Manual Controls → Home**.
6. Under **Tool Status**, make sure the **Voltage is above 3.6V**.
7. On the bottom bar, second icon from the right:

   * Check **Auto Vacuum**
   * Check **Auto-Levelling**
   * Click **Run**
8. The machine will probe the surface at **25 points** for auto-leveling, then automatically begin milling your design.

---

## Images

<img alt="boardpremill" src="https://github.com/user-attachments/assets/9225cf24-09af-43e2-934d-37c71910cf24" />

* This shows the copper in the CNC machine before being milled

<img alt="postmill" src="https://github.com/user-attachments/assets/2a6c2cf6-0b3c-4d10-94fb-bbf76bc6f8ca" />

* This is a photo of my board after milling while it was still in the CNC machine

<img alt="finishedpcb" src="https://github.com/user-attachments/assets/1b7b8d81-4ae0-475d-a6ea-02333ca68a5b" />

* Board after milling and removing it from the machine



## Issues
I did not experience any issues while working on this project.
