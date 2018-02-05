# Pupil 
Unity assets for low-impact image optimizations for low-powered VR hardware. 

# Getting Started
## PupilCamera.cs
Dynamically adjusts the camera to account for variable inter-pupillary distance (IPD) based on how far away an object is from the player.
Simply place the Prefabs/StereoScaling prefab into the hierarchy to trigger adjustments.


## PupilImageBlur.cs
Using the PupilImageBlur class, materials using the Shaders/BlurEdges shader will have the blur effect occur at a variable rate depending on the movement of the HMD.

*Example Script: Blur.cs*
```
using UnityEngine;
using Pupil;

public class Blur : MonoBehaviour {
	void Start () {
		PupilImageBlur.renderer = GetComponent<Renderer>();
		PupilImageBlur.camera = GameObject.FindGameObjectWithTag("MainCamera");
		PupilImageBlur.SetEdgeShader(); 
	}
	void Update () {
		PupilImageBlur.AutoBlur();
	}
}
```

## Prefabs/PupilCameraRig.prefab
VR camera rig that supports dynamic IPD adjustments.  

## Prefabs/PupilInitializer.prefab
Loads the VR device for Unity
