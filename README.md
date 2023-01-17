# Segment Objects From Background

This code imports the necessary libraries (numpy, matplotlib, and cv2) to perform image processing tasks. It then reads an image file named 'image.jpeg' using the cv2.imread() function, and converts it to grayscale using cv2.cvtColor(). Next, the code applies a threshold to the grayscale image using the cv2.threshold() function, which converts all pixels below a certain threshold (in this case, 127) to black, and all pixels above it to white. The code then applies a Canny edge detection algorithm to the thresholded image using cv2.Canny() to detect edges in the image. The code then applies dilation to the edge image using a kernel of size (5,5) and 1 iteration, which thickens the edges. Next, the code finds contours in the dilated image using cv2.findContours() and draws them on a copy of the original image. The code then loops through the contours and extracts a sub-image for each contour that has a height greater than 100 pixels. The sub-image is then displayed using matplotlib and saved to a file named 'R0.jpg', 'R1.jpg', etc.

Steps
1. Import necessary libraries (numpy, matplotlib, cv2)
2. Read an image file named 'image.jpeg' using the cv2.imread() function.
3. Convert the image to grayscale using cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
4. Apply threshold to the grayscale image using cv2.threshold(gray, 127, 255, 0), which converts all pixels below 127 to black, and all pixels above it to white.
5. Apply Canny edge detection algorithm to the thresholded image using cv2.Canny(thresh,128,255) to detect edges in the image.
6. Apply dilation to the edge image using a kernel of size (5,5) and 1 iteration using cv2.dilate(edge, kernel, iterations=1) to thicken the edges.
7. Find contours in the dilated image using cv2.findContours(dilation, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)
8. Draw the contours on a copy of the original image using cv2.drawContours(image.copy(), contours, -1, (0, 255, 0), 2)
9. Loop through the contours and extract a sub-image for each contour that has a height greater than 100 pixels using cv2.boundingRect(c)
10. Display the sub-image using matplotlib and plt.imshow(cv2.cvtColor(im, cv2.COLOR_BGR2RGB))
11. Save the sub-image to a file named 'R0.jpg', 'R1.jpg', etc using cv2.imwrite('R' + str(image_no) + '.jpg',im)
12. Increment the image number by 1 using image_no += 1
