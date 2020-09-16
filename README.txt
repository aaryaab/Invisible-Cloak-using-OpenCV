This is the Invisible Cloak project. Now, anyone can become invisible at home!

A thinkbuster for everyone is, "All we need to do is replace cloak in our FOREGROUND with STATIC BACKGROUND" 

The project is based on OpenCV. 

Libraries used for the project are:

- OpenCV  (pip install opencv-python)

- Numpy   (pip install numpy)

Hardware: 

- Laptop WebCamera

Normally RED and GREEN colored sheet.screen is used since it has high contrast with our skin and can give best results. Other shaded sheets may show distortions and may not make us totally invisible!




STEP1: Start recording video from webcamera

STEP2: Let the webcamera settle down for few seconds. 

        As soon as the webcamera starts don't pop in front of the         camera. The reason behind this is, as per the time mentioned us,         we are giving time              to             laptop to capture         background, which will help us to become invisible.

        If the time is not given and one directly pops in front of               webcamera, in the place of our cloak, instead of the background,         the face of user will               be              masked,         which will be quite hilarious and also polar opposite the use of         Invisible Cloak

STEP3: Capturing the Background 

STEP 4: Reading frames of the camera, till it is open

STEP 5: Highlighting the red colored cloth

STEP6:  Masking it with the background

STEP7: Generating the final output




Some important considerations:

we are using RED colored cloth, but at places there may be tweak in color because of lightening and maybe shadows. So we would not be directly using the threshold of RED color, and select it. We will transform it into HSV (HUE-SATURATION-VALUE). HSV represents color using three parameters

- Hue: Encodes color Information

- Saturation: Encodes Intensity of the color

- Value: Encodes Brightness of Color

In code the range 0-10 and 170-180 is used to avoid detection of skin as red. The lower range of 70 is used so that we can detect red color in the spots and crumbles.

lower_red=np.array([170,120,70])
upper_red=np.array([180,255,255])

I found these values online for red color, I will surely update the code for green color cloth as well!

>> I wrote the code on Google Collaboratory, but in the end when we try to get final output using

camera.release()
out.release()
cv2.destroyAllWindows()




, we do not get output as COLAB is a virtual machine and to access camera, we need a API to use. So the easiest approach is to download the file on local machine and run it.