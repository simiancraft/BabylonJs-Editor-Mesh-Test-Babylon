# BabylonJs-Editor-Mesh-Test-Babylon
A repo to capture the work done from testing the importation of a .babylon file into the editor


**Test 1: Babylon File**
-----
Expected Dude.babylon:

![image|684x288,75%](https://discourse-cloud-file-uploads.s3.dualstack.us-west-2.amazonaws.com/standard10/uploads/babylonjs/original/2X/d/d89a5a3297c4014aaf9e67e9a20b0113f1bb8cfc.jpeg) 

(clearing/ new scene in between each action)


Importing
---
**1. Frist action: Drag `.babylon` file right in:**

![image|690x294,75%](https://discourse-cloud-file-uploads.s3.dualstack.us-west-2.amazonaws.com/standard10/uploads/babylonjs/original/2X/5/590abdf3ce2eb23c1c82ef4a62a8c2c42943b313.png)  


It's not immediately obvious that the textures needed to be added separately. Some other filetypes don't require this. You can drag the textures in later, and clicking the refresh on the Materials Viewer will update the materials, but the scene will be out of sync. there's not really a way to 'refresh' the scene here, so it looks wrong unless you know what is happening.


![image|552x500,75%](https://discourse-cloud-file-uploads.s3.dualstack.us-west-2.amazonaws.com/standard10/uploads/babylonjs/original/2X/8/81043c18176a05d84f4c325310314937e136dd96.png) 


**2. Second Action: Drag all files in simultaneously:**

![image|518x500,75%](https://discourse-cloud-file-uploads.s3.dualstack.us-west-2.amazonaws.com/standard10/uploads/babylonjs/original/2X/8/88efe2a3c6ba92e3310f3d42ac9a8f0818dead29.jpeg) 
This mostly works, with two minor exceptions:
1. The materials view didn't update quite right:
![image|690x294,75%](https://discourse-cloud-file-uploads.s3.dualstack.us-west-2.amazonaws.com/standard10/uploads/babylonjs/original/2X/8/8d50baa842470962f76c71884250c9119ad50dc4.png) 
Clicking Refresh doesn't fix this, but clicking the individual material does, thankfully seem to help.
2. There is an error thrown in the console.
`Uncaught (in promise) TypeError: Cannot read property 'name' of null
    at preview.html:101` is thrown in the console.
![image|690x93,75%](https://discourse-cloud-file-uploads.s3.dualstack.us-west-2.amazonaws.com/standard10/uploads/babylonjs/original/2X/f/f5735932979dd8189b39c545f8cf625ec677b97f.png) 

**3. Third Action: Drag textures and THEN model in that order:**
- Identical results to Action #2.
![image|690x354,75%](https://discourse-cloud-file-uploads.s3.dualstack.us-west-2.amazonaws.com/standard10/uploads/babylonjs/original/2X/a/a03e1030aea84612f26891b025ccf6561efaec72.png) 

**Reloading Editor Project**
--
I chose the final state to save and reload.
1. save project
![image|690x282](upload://tmuIjiOZlCbFbzFe5uOJPK5YGT5.png) 
2. close editor.
3. doubleclick the `scene.editorproject`
![image|690x304,75%](https://discourse-cloud-file-uploads.s3.dualstack.us-west-2.amazonaws.com/standard10/uploads/babylonjs/original/2X/a/a1d4f79f88dea634f069fd0f4e6360353554ac46.jpeg) 
**Success.** The mesh loads completely correctly, and even the materials viewer is in the right state now.
![image|246x386](https://discourse-cloud-file-uploads.s3.dualstack.us-west-2.amazonaws.com/standard10/uploads/babylonjs/original/2X/4/4d67a9f9112cf8c94951abc822e15be81f728b69.png) 
A seemingly non-crashing error is in the console: 
`Uncaught (in promise) TypeError: Cannot read property 'name' of null
    at preview.html:101`
This is the same error from before in steps 2 and 3 of importing.

**In a Web Project**
--
Loads, no errors (awesome!)
![image|690x297](https://discourse-cloud-file-uploads.s3.dualstack.us-west-2.amazonaws.com/standard10/uploads/babylonjs/original/2X/b/b62c271b4fc91b458891d6bc6b86592af6c96280.png) 


