# Tokyo2020-Pictogram-using-MediaPipe
This is a demo that estimates the posture with MediaPipe and displays a pictogram in the style of the Tokyo 2020 Olympics.

https://user-images.githubusercontent.com/37477845/127340964-5378706f-034a-4920-be23-c6fbca442686.mp4

# Requirement 
* mediapipe 0.8.6 or later
* OpenCV 3.4.2 or later

#  Demo
Start the demo with the following command. <br>
Press the ESC key to end the program. <br>
```
python main.py
```
* --device <br>
Specifying the camera device number <br>
Default: 0
* --width <br>
Width at the time of camera capture <br>
Default: 640
* --height <br>
Vertical width at the time of camera capture <br>
Default: 360
* --static_image_mode <br>
Still image mode <br>
Default: not specified
* --model_complexity <br>
Model complexity (0: Lite 1: Full 2: Heavy) <br>
* Please refer to [Pose Optimization Quality] (https://google.github.io/mediapipe/solutions/pose#pose-estimation-quality) for performance differences. <br>
Default: 1
* --min_detection_confidence<br>
Threshold for detection confidence <br>
Default: 0.5
* --min_tracking_confidence <br>
Tracking confidence threshold <br>
Default: 0.5
* --rev_color <br>
Invert background color and pictogram color <br>
Default: not specified

## Using Docker

For Ubuntu, you can also use Docker + docker-compose without installing MediaPipe on the host machine.

First, edit `docker-compose.yml` according to your environment.
If you want to use `video0` when specifying a video device, edit it as follows.
```diff
    # Edit here
    devices:
      # - "/dev/video0:/dev/video0"
      # - "/dev/video1:/dev/video0"
-     - "/dev/video2:/dev/video0"
+     - "/dev/video0:/dev/video0"
```

Then build the Docker image.

```
docker-compose build
```

Allows the GUI application to start (X11 Forwarding).

```
xhost +local:root
```

Finally, start the Docker container.

```
docker-compose up
```

# Author
Kazuhito Takahashi (https://twitter.com/KzhtTkhs)
 
# License 
Tokyo2020-Pictogram-using-MediaPipe is under [Apache-2.0 License](LICENSE).
