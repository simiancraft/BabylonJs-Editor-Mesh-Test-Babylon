# BabylonJs-Editor-Mesh-Test-Babylon
A repo to capture the work done from testing the importation of a .babylon file into the editor

**Test 1: Babylon File**
-----
Expected Dude.babylon:
![image|684x288,75%](upload://uU9PA5nAPIhoH7IxyrLy5rZvnEU.jpeg) 

(clearing/ new scene in between each action)

Importing
---
**1. Frist action: Drag `.babylon` file right in:**

![image|690x294,75%](upload://cHHvAwyVicYF4ymuWUsgGgtW95V.png)  

It's not immediately obvious that the textures needed to be added separately. Some other filetypes don't require this. You can drag the textures in later, and clicking the refresh on the Materials Viewer will update the materials, but the scene will be out of sync. there's not really a way to 'refresh' the scene here, so it looks wrong unless you know what is happening.

![image|552x500,75%](upload://ipkFklbm2QIK5bZq7bT2iHi4jOe.png) 

**2. Second Action: Drag all files in simultaneously:**

![image|518x500,75%](upload://jxoT33dihXqJTSoyKdu7lSfYSy5.jpeg) 
This mostly works, with two minor exceptions:
1. The materials view didn't update quite right:
![image|690x294,75%](upload://ka8hEn94YFGooPfpLJXsDTY9E3i.png) 
Clicking Refresh doesn't fix this, but clicking the individual material does, thankfully seem to help.
2. There is an error thrown in the console.
`Uncaught (in promise) TypeError: Cannot read property 'name' of null
    at preview.html:101` is thrown in the console.
![image|690x93,75%](upload://z1m70RvksmdlC5pgo229pQvX0tx.png) 

**3. Third Action: Drag textures and THEN model in that order:**
- Identical results to Action #2.
![image|690x354,75%](upload://mRzmDEZ9KQZuxuwSz9xeiv4QAj8.png) 

**Reloading Editor Project**
--
I chose the final state to save and reload.
1. save project
![image|690x282](upload://tmuIjiOZlCbFbzFe5uOJPK5YGT5.png) 
2. close editor.
3. doubleclick the `scene.editorproject`
![image|690x304,75%](upload://n5D9ufCgUr0AB6rA1C7OKcBXmyW.jpeg) 
**Success.** The mesh loads completely correctly, and even the materials viewer is in the right state now.
![image|246x386](upload://b2KRA5CgvEmnJwPDWSUBeqjRWOt.png) 
A seemingly non-crashing error is in the console: 
`Uncaught (in promise) TypeError: Cannot read property 'name' of null
    at preview.html:101`
This is the same error from before in steps 2 and 3 of importing.

**In a Web Project**
--
Loads, no errors (awesome!)
![image|690x297](upload://pZzuMrQzxJdz0OpX9eAk2GeX0ly.png) 


