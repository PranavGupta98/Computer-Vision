Face Detection Algorithm - Haarcascade

1. Import open cv
2. Read a photo from the storage
3. Hard code a rectangle as shown and try to get an idea of coordinates:

![FD1](https://user-images.githubusercontent.com/27321748/121680263-f65c7a80-cad6-11eb-9a7c-e6525c7a6741.jpg)


4. Now use Haarcascade which is a pre-trained model for detecting faces. Need to download the 	“haarcascade_frontalface_default.xml” file from the internet
5. To detect face we need to set a variable(‘cap’) to connect to our camera, by using the function VideoCapture() of opencv. The number 0 represents camera number as there can be multiple cameras in a pc, 0 is the default laptop webcam.
6. Create an object of the CascadeClassifier
7. We use an infinite loop using ‘while True’ since we need a video, since video is nothing a but a series of images captured in short intervals hence infinite loop of clicking photos looks like a video
8. Capture each photo in loop and store in variable
9. Using the pre-trained mode detect the face and store coordinates(in form of an array in a variable called “faces”
![FD2](https://user-images.githubusercontent.com/27321748/121680576-58b57b00-cad7-11eb-864c-6daebc60fcd2.jpg)

10. Faces here is a 2D array with 1 row 4 columns, so it’s length is 1. Hence we put a condition that if len(faces) == 0 that means the array is empty/has no rows, which means no face coordinates were detected and stored. So we pass and continue the loop.
11. Here is what each element of the “faces” array means:
11. 1. faces[0][0] - leftmost coordinate of a box enclosing the face
11. 2. faces[0][1] - topmost coordinate of the box enclosing the face
11. 3. faces[0][2] - width of the face
11. 4. faces[0][3] - height/vertical length of the face
12. Now to create a rectangle we need to give coordinates for all the lines as described in Fig 1.1. So to get the coordinates of rightmost line we add width of face to leftmost coordinate and to get bottommost line we add height of face to topmost coordinate.
Example:
![FD4](https://user-images.githubusercontent.com/27321748/121680728-84386580-cad7-11eb-8f48-b6d7d0fcc881.jpg)

13. Store this photo along with the rectangle in a variable “aphoto”
14. Now we show the photo with the rectangle defined around the face using imshow()
15. Since the infinite loop will generate infinite photos we set a break condition with defining waitKey() function = 13. The 13 number is used to define “Enter” so this means that when we press enter we will break out of the loop. Also ‘n’ in ‘waitKey(n)’ represents the number of milliseconds we want each photo to be shown. 
  1. Higher n = longer each photo is shown = slower/choppy video
  2. Lower n = single photo shown for shorter duration = smooth video
16. Then we release the camera
  
![FD3](https://user-images.githubusercontent.com/27321748/121680686-77b40d00-cad7-11eb-9c18-434eddbc8d56.jpg)

