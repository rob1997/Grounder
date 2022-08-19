# Grounder
Ik Grounder Based on Unity's Package Animation Rigging
## Setup
1. Import Animation Rigging Package From the Package Manager <br />
![image](https://user-images.githubusercontent.com/36323674/185576882-38e531f1-6f07-496b-b79b-d2507ffc4ddc.png)
2. Put a Rig Builder Component on Your Bipedal GameObject <br />
![image](https://user-images.githubusercontent.com/36323674/185576773-55a0748a-8668-4c49-95a2-41a36f8ba9f8.png)
3. Set Up Ik Rig <br />
One Ik Rig (Child of Bipedal GameObject) with Three Constraints as Children <br />
![image](https://user-images.githubusercontent.com/36323674/185577494-3a9944a3-819f-47e9-8b30-9fb15d2bc12e.png) <br />
![image](https://user-images.githubusercontent.com/36323674/185577419-9b9184c2-bca3-4499-8bf3-6b1376235bac.png) <br />
Reference Foot Ik Rig in Rig Builder from Step 2
4. Set Up Two Bone Constraints for Each Leg <br />
![image](https://user-images.githubusercontent.com/36323674/185577673-d3f7f290-86a9-4915-bfb3-7db7b6b16bab.png) <br />
![image](https://user-images.githubusercontent.com/36323674/185577708-d8faa40f-e90d-467f-990c-b827bab6f68e.png) <br />
![image](https://user-images.githubusercontent.com/36323674/185577746-01f49ce1-45e0-4933-bdc5-cda54bd13676.png) <br />
**THE ORDER OF COMPONENTS AND GAMEOBJECTS MUST MATCH FOR THE CORRECT ORDER OF EXECUTION** <br />
Extact Transform Constraint Must Always Preceed Two Bone/Multi Position Constraint and Pelvis Constraint GameObject Must Always Preceeed Two Bone Ik Constraints Objects, This Matters because of the Burst Compiler Execution Order <br />
Set Hint Weight on Both Two Bone Ik Component to 0, to stop Leg Bending in unwanted way <br />
5. Set Foot Forward For Feet (Create A Transform Under Each Ik Constraint Facing the Forward of Foot, Used for Relative IK Rotation) <br />
![image](https://user-images.githubusercontent.com/36323674/185579266-171c9769-57f9-4e30-bc95-7dbc0f8051c6.png)<br />
![image](https://user-images.githubusercontent.com/36323674/185579315-8b20f593-df76-4ec8-9990-1775187e51b8.png)<br />
6. Set Up Grounder on Bipedal Object (where Animator Component is) <br />
![image](https://user-images.githubusercontent.com/36323674/185579534-0a8c8e0f-5207-4a00-8167-0780f132bc0a.png) <br />
**Bonus**. You Can setup Animation Curves of "LeftFootUp" and "RighFootUp" for optimal Ik Rotation, Foot only rotates to Surface When It's on Ground! <br />
![image](https://user-images.githubusercontent.com/36323674/185580086-1127a1a5-4c53-4e95-9d07-e3d4bc1a2cd3.png) <br />
![image](https://user-images.githubusercontent.com/36323674/185580258-80019459-22fe-47d7-96eb-2c0d37a5c976.png) <br />
