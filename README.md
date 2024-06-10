## Automatic Number Plate Detection using OpenCv and Python
### Step 1: Importing Libraries
-> cv2: OpenCV library for image processing.<br>
-> os: Standard library for interacting with the operating system.<br>
-> matplotlib.pyplot: Library for plotting images.<br>
-> numpy: Library for numerical operations on arrays.<br>
-> easyocr: Optical Character Recognition (OCR) library.<br>
-> imutils: Utility functions for basic image processing tasks.<br>

### Step 2: Read, Grayscale, and Blur the Image
-> cv2.imread: Reads the image from the specified path.<br>
-> cv2.cvtColor: Converts the image to grayscale for easier processing.<br>
-> plt.imshow: Displays the image using matplotlib.<br><br>
<img align="left" width="350" height="300" src="https://github.com/Dhanishthad/Number-Plate-Detection-using-OpenCv/assets/101131774/f21ffd40-2feb-41c1-aead-42cd19d2f1e4"></img> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br>

### Step 3: Apply Filter and Find Edges for Localization 
-> cv2.bilateralFilter: Applies a bilateral filter to reduce noise while keeping edges sharp. <br>
-> cv2.Canny: Detects edges in the image. <br> <br>
<img align="left" width="350" height="300" src="https://github.com/Dhanishthad/Number-Plate-Detection-using-OpenCv/assets/101131774/af7b2467-e005-4d9d-b60e-ecf3999b8226"> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br>

### Step 4: Find Contours and Apply Mask
-> cv2.findContours: Finds contours in the edged image.<br>
-> imutils.grab_contours: Simplifies the contour retrieval.<br>
-> cv2.approxPolyDP: Approximates the shape of the contours.<br>
-> Sorting and filtering contours: Looks for the largest contours and checks if they approximate to a quadrilateral (number plate).<br><br>
<img align="left" width="350" height="300" src="https://github.com/Dhanishthad/Number-Plate-Detection-using-OpenCv/assets/101131774/8b635a54-9058-4a40-b333-91cb2437acbc"> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br>

### Step 5: Create a Mask and Extract the Number Plate Region
-> np.zeros: Creates a blank mask.<br>
-> cv2.drawContours: Draws the found contour on the mask.<br>
-> cv2.bitwise_and: Applies the mask to the original image to isolate the number plate region.<br>

### Step 6: Crop the Number Plate from the Image
-> np.where: Finds the coordinates of the white pixels in the mask.<br>
-> np.min / np.max: Finds the bounding box of the number plate.<br>
-> Cropping: Extracts the number plate region from the grayscale image.<br><br>
<img align="left" width="300" height="150" src="https://github.com/Dhanishthad/Number-Plate-Detection-using-OpenCv/assets/101131774/34a9d1dd-f35a-4360-b947-90a90a6036db"> <br> <br> <br> <br> <br> <br> <br> 

### Step 7: Use EasyOCR to Read Text
-> easyocr.Reader: Initializes the EasyOCR reader for English.<br>
-> reader.readtext: Reads the text from the cropped number plate image.<br>

### Step 8: Render the Result on the Original Image
-> Extract text: Gets the detected text from the OCR result.<br>
-> cv2.putText: Places the detected text on the original image.<br>
-> cv2.rectangle: Draws a rectangle around the detected number plate.<br>
-> plt.imshow: Displays the final image with the annotated number plate.<br><br>
<img align="left" width="500" height="350" src="https://github.com/Dhanishthad/Number-Plate-Detection-using-OpenCv/assets/101131774/8bd93d8e-350f-472e-9f17-28daea518275"> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br> <br>






