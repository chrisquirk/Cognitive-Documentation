<!-- 
NavPath: Face API
LinkLabel: Release Notes
Url: face-api/documentation/ReleaseNotes
Weight: 20
-->

# Face API Release Notes

This article pertains to Microsoft Face API Service version 1.0.

### Release changes in November 2016
* **Face Storage expansion**; Face Storage allows a Standard subscription to store additional persisted faces when using Person objects ([Person - Add A Person Face](https://dev.projectoxford.ai/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523b)) or Face Lists ([Face List - Add a Face to a Face List](https://dev.projectoxford.ai/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395250)) for identification or similarity matching with the Face API. The stored images are charged at $0.5 per 1000 faces and this rate is prorated on a daily basis. Free tier subscriptions continue to be limited to 1,000 total persons. 

### Release changes in October 2016
* **Error Message Change In Face List**: Add a Face to a Face List and Person - Add a Person Face APIs, the error message of more than 1 face in the targetFace changes from There are more than 1 face in the image to There is more than 1 face in the image.

### Release changes in July 2016
* **Face Verification API**: Face to Person object authentication is supported – previously Face Verification requests only supported Face to Face authentication. More details can be found: [Face - Verify](https://dev.projectoxford.ai/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523a).

* **Finding Similar Face API**: Added optional mode field enabling selection of two working modes, default matchPerson works the same as before, and new mode matchFace removes the same person filtering. If mode field is not specified, the behavior is the same as the past release. More details can be found: Face - Find Similar.

* **Face Identification API**: Optional user-specified confidenceThreshold is enabled for user to define the confidence threshold of whether one face belong to a person object. More details can be found: Face - Identify.

* **List person groups**: New optional start and top parameters in list person groups to support user specifying the start point and the total person groups number to list. More details can be found: Person Group - List Person Groups.

*Note*: All of these changes are compatible with the last version service, and using the default value for the newly added parameters will not cause any changes to users' code. 

### V1.0 changes from V0
* **API Signature**: In Face API V1.0, Service root endpoint changes from https://api.projectoxford.ai/face/v0/ to https://api.projectoxford.ai/face/v1.0/ There are several signature changes for API, such as Face - Detect, Face - Identify, Face - Find Similar, Face - Group.

* **Face sizes**: The previous version of Face API was not clear about the smallest face sizes the API could detect. With V1.0 the API correctly sets the minimal detectable size to 36x36 pixels. Faces smaller 36x36 pixels will not be detected.

* **Persisted data**: Existing Person Group and Person data which has been setup with Face V0 cannot be accessed with the Face V1.0 service. This incompatible issue will occur for only this one time, following API updates will not affect persisted data any more.

*Note*: The V0 endpoint of Face API was retired on 06/30/2016.