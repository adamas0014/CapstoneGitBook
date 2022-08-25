# Freenove Kit Gait Generation

The Freenove Robot Dog Kit requires the user to clone their repository to the on-board raspberry py prior to attempting to control it.

This repository contains control code, user interfaces, and hardware interfaces to allow compatibility with the provided hardware.

Movement is achieved through string movement commands that are parsed and coordinated using a switch/case statement. In general, each case specifies the direction and axis to apply the gait function to.

![](<../.gitbook/assets/image (1).png>)

As we can see in the image below, the leg coordinates are clamped and translated by user configured values, but the general motion is determined by sine and cosine functions.

![](../.gitbook/assets/image.png)

Using sine and cosine on different axis of the same coordinate allows for elliptical movement.

![](<../.gitbook/assets/image (2) (1).png>)

This elliptical movement is used to position the tip of the legs.

However, it is noticed that side-stepping has a smaller amplitude of movement, which makes sense to keep the dog stable.

Balance, for this robot dog kit, is achieved using an on-board IMU sensor. This sensor information is used in the construction of transformation matrices.

![](<../.gitbook/assets/image (4).png>)

A matrix is used to define the plane made by the feet of the robot dog.&#x20;

![](<../.gitbook/assets/image (3).png>)

This footprint matrix is transformed using the rotation matrix.&#x20;

![](<../.gitbook/assets/image (2).png>)

