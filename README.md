# RobustPupilDetection
Readme
Objectives
This research is part of our research in computer vision application in biomedical engineering. The aim of this research is to detect the pupil in robust condition such as low and high light intensity.
In this research we used some devices as follow:
1.	Jetson nano
2.	ArduCam HQ IR_CUT camera 12 MP
3.	IR Light Source
4.	Arducam CSI USB UVC Camera Adapter Board
Data Preparation:
We collected dataset based on some condition, with glasses, without glasses, normal light intensity and low light intensity. Figure 1 shows the dataset categories.

 ![image](https://user-images.githubusercontent.com/106336723/170565170-6f5f6f3e-0236-41a2-912a-4db99e8c2e79.png)

Figure 1. Dataset
 ![image](https://user-images.githubusercontent.com/106336723/170565195-6bb66021-bd5a-41ef-a692-96745ba37191.png)

Figure 2. Pupil Detection Devices



Instructions:
•	Prepare the jetson nano based on dusty-nv/jetson-inference: Hello AI World guide to deploying deep-learning inference networks and deep vision primitives with TensorRT and NVIDIA Jetson. (github.com).
•	Copy or clone the repo and place into jetson inference folder
•	Place the model into your installation based on my project, it is located on 
models/eye/labels.txt
models/eye/ssd-mobilenet.onnx
•	Place the test image into jetson-inference/data/images/pupil_0.jpg
•	To test the model based on images 
detectnet –model=models/eye/ssd-mobilenet.onnx –labels=models/eye/labels.txt –input-blob=input_0 –output-cvg=scores –output-bbox=boxes “/jetson-inference/data/images/pupil_0.jpg” /jetson-inference/data/images/test
  test images:



![image](https://user-images.githubusercontent.com/106336723/170565229-8f27fcbf-9fa2-4bb4-ad8b-f0a9494d59da.png)




Result :

     
![image](https://user-images.githubusercontent.com/106336723/170565253-237728a8-24f7-4042-afd9-7d9ef56e2208.png)


•	Real time by using camera: 
•	detectnet –model=models/eye/ssd-mobilenet.onnx –labels=models/eye/labels.txt –input-blob=input_0 –output-cvg=scores –output-bbox=boxes /dev/video0

the video of this pupil models 
https://drive.google.com/file/d/11R5GL4-o3RMGC_Ty0u8bgQntCHPVvDhF/view?usp=sharing
![image](https://user-images.githubusercontent.com/106336723/170565953-9a3a7619-cfb4-4ef2-ac75-647f481771c8.png)
![image](https://user-images.githubusercontent.com/106336723/170566007-1c535dfe-a6eb-45ed-8208-003602c70494.png)
![image](https://user-images.githubusercontent.com/106336723/170566109-ed4526e9-3f19-446d-beb7-308eb3094ef7.png)




