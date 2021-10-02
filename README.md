# ALS Component

To make it more portable, easier to add ALSv4 to the existing project without any hassle I did decide to work on components that hold all ALS settings with some additional staff like a weapon system.

Overall it is only partly replicate Advanced Locomotion System v4. 

Youtube quick overview <a href="https://www.youtube.com/watch?v=s07VBy2uXqc">link</a>

Discussion regarding the replication effort of ALS should take place on the official discord for Advanced Locomotion System here: https://discord.gg/wYYMHFu

<p align="center">
  <a href="https://discord.gg/wYYMHFu"><img src="https://i.imgur.com/LP9bZQj.png"></a>
</p>

This repository will operate on a series of pull requests. You are free to download modify and pull request your modifications in. If it meets with the criteria of effectively replicating the project, it will be reviewed and merged in.

### Bug Reporting Template:
```
**Detailed description of issue**
Write a detailed explanation of the issue here.

**Steps To Reproduce:**
1: Detailed Steps to reproduce the issue 
2: Clear steps
3: Etc

**Expected Results:**
A description of what should happen.

**Actual Results:**
A description of what actually happens.
```

# Setting Up Your Project
- Clone the repository or download the latest release.
- Move `ALSReplicated\Content\ALS_Component` folder into your project's `Content` folder
- Add the lines below into your project's `DefaultInput.ini`, below `[/Script/Engine.InputSettings]` tag:
```
+ActionMappings=(ActionName="JumpAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=SpaceBar)
+ActionMappings=(ActionName="JumpAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=Gamepad_FaceButton_Bottom)
+ActionMappings=(ActionName="StanceAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=C)
+ActionMappings=(ActionName="SprintAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=LeftShift)
+ActionMappings=(ActionName="StanceAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=Gamepad_FaceButton_Right)
+ActionMappings=(ActionName="SprintAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=Gamepad_LeftThumbstick)
+ActionMappings=(ActionName="WalkAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=Gamepad_RightShoulder)
+ActionMappings=(ActionName="AimAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=RightMouseButton)
+ActionMappings=(ActionName="AimAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=Gamepad_LeftTrigger)
+ActionMappings=(ActionName="SwitchRotationMode",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=Four)
+ActionMappings=(ActionName="SwitchRotationMode",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=Gamepad_DPad_Left)
+ActionMappings=(ActionName="ShoulderSwap",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=R)
+ActionMappings=(ActionName="ShoulderSwap",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=Gamepad_RightThumbstick)
+ActionMappings=(ActionName="RagdollAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=X)
+ActionMappings=(ActionName="RagdollAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=Gamepad_Special_Left)
+ActionMappings=(ActionName="CycleOverlayUp",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=MouseScrollUp)
+ActionMappings=(ActionName="CycleOverlayDown",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=MouseScrollDown)
+ActionMappings=(ActionName="CycleOverlayUp",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=Gamepad_DPad_Up)
+ActionMappings=(ActionName="CycleOverlayDown",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=Gamepad_DPad_Down)
+ActionMappings=(ActionName="OpenOverlayMenu",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=Q)
+ActionMappings=(ActionName="OpenOverlayMenu",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=Gamepad_LeftShoulder)
+ActionMappings=(ActionName="AttackAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=LeftMouseButton)
+ActionMappings=(ActionName="InteractAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=E)
+ActionMappings=(ActionName="TargetLockAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=MiddleMouseButton)
+ActionMappings=(ActionName="RollAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=LeftAlt)
+ActionMappings=(ActionName="WalkAction",bShift=False,bCtrl=False,bAlt=False,bCmd=False,Key=LeftControl)
+AxisMappings=(AxisName="MoveForward/Backwards",Scale=1.000000,Key=W)
+AxisMappings=(AxisName="MoveRight/Left",Scale=1.000000,Key=D)
+AxisMappings=(AxisName="LookUp/Down",Scale=-1.000000,Key=MouseY)
+AxisMappings=(AxisName="LookLeft/Right",Scale=1.000000,Key=MouseX)
+AxisMappings=(AxisName="MoveForward/Backwards",Scale=-1.000000,Key=S)
+AxisMappings=(AxisName="MoveRight/Left",Scale=-1.000000,Key=A)
+AxisMappings=(AxisName="MoveForward/Backwards",Scale=1.000000,Key=Gamepad_LeftY)
+AxisMappings=(AxisName="MoveRight/Left",Scale=1.000000,Key=Gamepad_LeftX)
+AxisMappings=(AxisName="LookUp/Down",Scale=1.000000,Key=Gamepad_RightY)
+AxisMappings=(AxisName="LookLeft/Right",Scale=1.000000,Key=Gamepad_RightX)
```
- Add the lines below into your `DefaultEngine.ini`, below `[/Script/Engine.CollisionProfile]` tag (Create the tag if it doesn't exist):
```
+Profiles=(Name="ALS_Character",CollisionEnabled=QueryAndPhysics,bCanModify=True,ObjectTypeName="Pawn",CustomResponses=((Channel="Visibility",Response=ECR_Ignore),(Channel="Camera",Response=ECR_Ignore),(Channel="Climbable",Response=ECR_Ignore)),HelpMessage="Custom collision settings for the capsule in the ALS_BaseCharacter.")
+DefaultChannelResponses=(Channel=ECC_GameTraceChannel2,DefaultResponse=ECR_Block,bTraceType=True,bStaticObject=False,Name="Climbable")
```

# Known Issue:

# Current Features Added:
- ADS
- Target Lock
- Simple Weapon System
- Hit Reaction
- Interaction with CCDIK
- Footstep System
- Impact VFX 
- Melee CombatSystem
- Advanced Camera Manager
- added optional Top Down Camera
- Player Stats WiP (Shield/Health/Stamania)
