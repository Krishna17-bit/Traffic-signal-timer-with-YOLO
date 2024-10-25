**Adaptive Traffic Signal Timer Using YOLO**

**Overview**

This project develops an adaptive traffic signal timer using YOLO (You Only Look Once) for vehicle detection. The system adjusts the duration of green signals based on the detected vehicle count at an intersection, helping to manage traffic flow dynamically.

**Project Structure**

1.  **Vehicle Detection Using YOLO**:
    
    *   **Model Loading**: Load YOLO using pre-trained yolov3.cfg and yolov3.weights files, trained on the COCO dataset.
        
    *   **Image Preprocessing**: Prepare images for YOLO using resizing, normalization, and formatting through OpenCV’s cv2.dnn.blobFromImage.
        
    *   **Object Detection**: Run the YOLO model to detect vehicles, focusing on high-confidence detections for cars, buses, trucks, and bicycles.
        
    *   **Displaying Detections**: Use bounding boxes and labels to show detected objects on images, visualized with Matplotlib.
        
2.  **Adaptive Traffic Signal Timing**:
    
    *   **Counting Vehicles**: Count detected vehicles by checking class IDs for relevant objects (e.g., cars, buses).
        
    *   **Dynamic Timer Adjustment**: Set green signal duration based on vehicle count. If count exceeds a threshold, set a longer green time (e.g., 60 seconds); otherwise, set a shorter green time (e.g., 30 seconds).
        
3.  **Saving Results**:
    
    *   Save images with bounding boxes and labels for detected vehicles using cv2.imwrite.
        
    *   Extend the model to handle video input by applying YOLO to each frame.
        

**Challenges and Solutions**

*   **Visualization**: Since OpenCV’s imshow() doesn’t work in notebook environments, we used Matplotlib for displaying images and video frames.
    
*   **Detection Limitations**: The initial model had limited detection capability. We improved vehicle detection by adjusting the model to include bicycles and other relevant objects.
    

**Setup and Installation**

1.git clone https://github.com/Krishna17-bit/Traffic-signal-timer-with-YOLO.git
cd traffic-signal-timer
    
2. pip install -r requirements.txt
    

**Usage**

1.  **Run the Adaptive Timer Model**:
    
    *   Load traffic images or video frames and run the YOLO-based detection.
        
    *   Observe the dynamically adjusted green signal time based on vehicle count.
        
2.  **Adjust Parameters**:Modify threshold values to customize green signal duration based on traffic volume.
    

**Results**

*   **Vehicle Detection**: Detects vehicles accurately in images and video, adjusting signal timing based on traffic density.
    
*   **Adaptive Signal Timing**: Effectively manages green signal duration, improving traffic flow during high congestion.
