# Volcanobot_Hardware
###>>>> Real-World Hardware Based Real-Time 3D Mapping Using 2 RP-Lidars in Vertical and Horizontal <<<<####

### Dedication

Specially this project is dedicated to my parants S.Mujahid hussain (My Father) and Kaneez Fatima Rizvi (My Mother), Institute of Industrial Electronics Engineering: IIEE and to the students of IIEE.

# Building For Hardware Setup

### 1) Proposed Solutuin

Main theme of “SLAM BASED 3D MAP BUILDING USING 2 LOW COST 2D LASER SCANNERS (RPLIDAR A1)” is an orthogonal combination of two RP-Lidar 2D laser scanners which has beed used on slam’s vehicle to build real-time 3D point cloud map of the explored region.

![image](https://user-images.githubusercontent.com/122727165/213647514-308d9fa9-696b-4b9e-b3d3-d3831a972ef5.png)

### 2) Real Robot Harware Setup

The rover selection is customize based on 4WD mobile platform model. There are two sections where we can mount our additional hardware. These sections may be called as lower section and upper section.

![image](https://user-images.githubusercontent.com/122727165/213649634-c42d7a74-7a51-4aee-b0e1-a57e40e96467.png)

Additionally, for the support of LIDARs, an acrylic stand in orthogonal shape has been designed and fabricated. Two surfaces have been developed on the stand 

![image](https://user-images.githubusercontent.com/122727165/213650407-4ea27207-b368-406d-a75b-a56d3bcb6197.png)
![image](https://user-images.githubusercontent.com/122727165/213650438-49017536-533d-4882-8743-e34cab36ce77.png)

Here, the use of 1000 Rpm encoder motors for getting the feedback from encoder for correct Rover's pose in the environment.

![image](https://user-images.githubusercontent.com/122727165/213650463-6cb6bc4f-6deb-4c1f-8bcd-3e4d9342c89f.png)
![image](https://user-images.githubusercontent.com/122727165/213650485-23970853-cd75-4a79-91bc-335eb83a9de2.png)

The hardware connection from motor to arduino through motor driver ln298 as follows:

![image](https://user-images.githubusercontent.com/122727165/213656125-75168a0c-d541-4a4c-b023-47bfcdc13efb.png)
![image](https://user-images.githubusercontent.com/122727165/213656150-c2485c87-d0ee-42ce-8311-168da7f5e068.png)

![image](https://user-images.githubusercontent.com/122727165/213656176-8ac662c6-365a-44de-9906-e678d080d97c.png)
![image](https://user-images.githubusercontent.com/122727165/213656199-a8adea89-67f3-4769-907e-c228583011be.png)







# Installation For Hardware Setup
 
(.) cd catkin_ws/src
 
(.) https://github.com/Murtazahussan/volcanobot_sim.git
 
(.) cd ..
 
(.) source devel/setup.bash
