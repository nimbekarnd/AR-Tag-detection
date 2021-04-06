# AR Tags detection and processing

### The problem focuses on detecting a custom AR tag (see fig.), that is used for obtaining a point of reference in the real world, such as in augmented reality applications.

AR Tag

![alt text](./media/ar_tag.png?raw=true "AR Tag")


### The code basically involves three tasks:
    1) Detection of the AR tags in the videos (position and orientation) and calculating the id corresponding to each tag in the videos.
    2) Tracking the AR tags throughout the video.
    3) Superimposing 'lena' image and drawing a 3D cube over the tags in the videos. 


Steps to identify the id, track the tags and superimposing lena image and cube over the tags can be found in the [report](./Report.pdf).


### Output

The solution involves implementation of **cv2.getPerspectiveTransform()** and **cv2.warpPerspective()** functions of OpenCV.


**Warped Tags**

(./media/warped_tags.png?raw=true "Warped Tags")


**Tag and ID detection in video frames:**

![alt text](./mediat/tag_detection1.png?raw=true "Tag detection ID=7")

![alt text](./media/tag_detection2.png?raw=true "Tag detection ID=13")

![alt text](./media/tag_detection_3tags.png?rrue "Tag detection: Three tags")


**Superimposing _Lena_ image on the tags with proper orientation:**

![alt text](./media/lena_one_tag.pngaw=true "Superimposing Lena image on one tag")

![alt text](./media/lena_three_tags.pngaw=true "Superimposing Lena image on all the tags")

**Drawing 3D cube over the tags:**

![alt text](./media/cube_one_tag.png?raw=true "Drawing 3D cube over the tag")
    
![alt text](./media/cube_three_tags.png?raw=true "Drawing 3D cube over all the tags")

**Output videos can be found [here](https://drive.google.com/drive/folders/1bzZxU0ElG-uYMcrTHAwsvdtPljzHXHqh?usp=sharing)**




### Instructions to run the code:

python file named *‘process_ar_tags.py’* (location: /Code/) is to be run for the execution of the code:

Please make sure that the following files and sub-directories are at the same level relative to *‘process_ar_tags.py’* :
- /process_ar_tags.py
- /media/multipleTags.mp4
- /media/Tag0.mp4
- /media/Tag1.mp4
- /media/Tag2.mp4
- /media/Lena.png


- The code process the video frames and 1) detects the tag_id, 2) superimposes Lena image on the tags, 3) draws a 3D cube over the tags
- Commands to run the code:
- To display the detected tag and their ids - *$ python process_ar_tags.py*
- To display Lena image - *$ python process_ar_tags.py --show_lena=True* 
- To display cube - *$ python process_ar_tags.py --show_cube=True*
- To display lena image and cube - *$ python process_ar_tags.py --show_lena=True --show_cube=True*
- Lena image frame and cube display frame will open in a separate window
- The code by default process _multipleTags.mp4_ video. To process a different video other than this, say _Tag0.mp4_: *$ python process_ar_tags.py --video_option=Tag0*
- Any logical permutations of arguments can be used to test different behaviors
