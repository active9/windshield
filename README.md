#Windshield
![Windshield](https://raw.githubusercontent.com/active9/windshield/master/html/windshield.png)

Real-Time Transcoder & Streaming Server

##USING
Windshield runs on tcp port 40. Open localhost.rocks:40 to view your running instance of windshield.

##SECURITY
Windshield does not provide any security mechanisms to secure the data channel during video streams. In order to have a secured data channel you would need to fork the windshield repo from github and establish your own security measures.

##Introduction
Windshield provides a real-time "Virtual Windshield" for video encoding, transcoding, streaming, & piping.  It runs as a tcp/ip server on port 40. Requests passed through Windshield output as an mp4 and stream in real-time (where available). Much like a real windshield that you can see through this software provides a "Virtual Windshield" that can consume source videos in real-time pending cpu resources.

##Installing
```bash
npm install windshield -g
```

##Running
```bash
windshield
```
Windshield is easy to start. Just globally install the Windshield package then run the command windshield to launch the server.

##USING

Windshield is used as a stand-alone application. Now that you have Windshield installed you can visit http://localhost.rocks/ . Windshield has the following routes and features:

**/videos/:filename**
```bash
http://localhost.rocks:40/videos/test.avi
```
This will pass test.avi from the supplied videos folder via a tcp/ip octet-stream.

**/transcode/:kbps/:filename/:outfile**
```bash
http://localhost.rocks:40/transcode/700/test.avi/test.mp4
```
This will transcode test.avi and pipe it to test.mp4 in the background without sending any stream data through the browser.

**/network/:url**
```bash
http://localhost.rocks:40/network/http://somevideodomain.com/video.mp4
```
This will proxy and pipe the video from the remote location directly for streaming.

**/livestream/:kbps/:url**
```bash
http://localhost.rocks:40/livestream/1400/http://somevideodomain.com/video.mp4
```
This will proxy, transcode, & pipe the video from the remote location for real-time variable streaming.

**/live/:kbps/:filename**
```bash
http://localhost.rocks:40/live/1400/test.avi
```
This will transcode test.avi and pipe it to test.mp4 for real-time variable streaming.

**/stream/:filename**
```bash
http://localhost.rocks:40/stream/test.avi
```
This will input pipe test.avi for direct output streaming with no transcoding.

##CONTRIBUTING

We encourage forking. Feel free to fork & pull your new additions, or bug fixes.

##LICENSE
MIT

