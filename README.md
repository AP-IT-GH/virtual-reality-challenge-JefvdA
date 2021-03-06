# Jef van der Avoirt - 3D painting challange

## Step 1
Open the broken challange scene (In the VR room project), the scene is located in following path: "Assets/Challanges/02_3DPainting/Scenes"


## Step 2
Fix the canvas that allow you to change the shape, currently it follows your camera, but we need to place it stationary.
When selecting the canvas (named "Canvas_Pedestal"), look for the "Canvas" component.
In here we want to change the render mode, select World Space.
![image](https://user-images.githubusercontent.com/13435783/163166126-6dd0f381-2c0d-469f-aa69-b6de5e0582c8.png)
<br>
After that, position the canvas around the room, choose a good spot, it will now stay here and won't follow the camera.


## Step 3
The palette should move with the left hand and, when you press the thumbstick or primary button on the right controller, the toggled ray should emit from the right hand.

### 1
If we inspect the LeftHand gameObject, under the Camera Offset of the XRRig, you will see that the input is linked to the right controller.
Change the references of the action to the correct (left) controller.

### 2
If we inspect the RightRay gameObject, you will see that the input is linked to the left controller.
Again, change the references of the action to the correct (right) controller.


## Step 4
Currently, the brush paints automatically, and stops when holding the trigger. This is backwards, we need to reverse it.

Under the Paintbrush gameObject, locate the "XR Interactable" component. Here change the actions for "Paintbrush (Create Trail)" for On Activate and On Deactivate, and switch them around.
<br>
![image](https://user-images.githubusercontent.com/13435783/163168078-4d5d7cc4-8398-4770-b622-e8763b5a5ec1.png)


## Step 5
Currently, the medium brush size button turns invisible when pressed and makes the trail gigantic.

Locate the "Canvas_Palette" located under the LeftHand gameObject. Next, find the "Buttons_size" and select the "Button_Medium".
<br>
![image](https://user-images.githubusercontent.com/13435783/163168729-806ad231-91a4-419e-96cd-fe883e927450.png)
<br>

Next, in the inspector, for Button_Medium, under the "Button" component:
- Change the "Pressed Color", the alpha is currently set to 0, change it to 255.
- Change the value for the onClick action "CreateTrail.SetWidth" to a value between 0.01 (small brush) and 0.05 (large brush). I chose 0.03.

![image](https://user-images.githubusercontent.com/13435783/163169333-45753898-0d87-4950-906b-30e3fa207ccf.png)


## Step 6
Currently, the paint brush sound effect stays the same, regardless of how far it is from you.

Locate the Paintbrush gameObject, and under the "Audio Source" component, change the "Spatial Blend" to 1 instead of 0.
![image](https://user-images.githubusercontent.com/13435783/163169687-5a06eadd-c36e-49b5-9fc8-e884df26d106.png)
