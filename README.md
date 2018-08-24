# THE_HIT_SONGS
This program will prompt the user for a mp3 upload, then run it through a machine learning algorithm that will predict it to be a "hit" or "not a hit".

The program analyzes four features of each uploaded song:

1. Average Frequency
2. Mode Frequency
3. BPM (Beats Per Minute)
4. Duration

It analyzes these features on the client-side using the web-audio-api along with some other frontend libraries. 
It then passes an array with these features to the backend via an XML HTTP POST Request. 

The backend accepts the array and routes it the machineLearning.js file, which uses a trained  kNN (k-nearest neighbors) machine learning
 algorithm to classify the array as a 0 (not a hit) or 1 (a hit). 

After classification, the 0 or 1 is returned via HTTP, and the hit or not a hit page is rendering depending on the returned value. 

To Run Locally:

1. npm install
2. npm start
3. node server
4. Navigate to localhost:8080 in Chrome browser 

**ONLY WORKS IN CHROME** 

I am a musician. I've played piano as a hobby since I was child, and recently I've decided to attempt to produce professional-grade music.
I've made several songs over the past couple of months, but I wanted to accurately gauge if they were good pieces of music before releasing them.
Thus came the idea for a machine learning algorithm that can determine hit songs!

I plan to release the program in the future online as a web application accessible through the domain "thehitsongs.com". I've purchased the 
domain and will hopefully get around to uploading it in the coming months. I'd like to improve it in these ways before I do so:

1. Decrease latency of converting youtube links into mp3 files. The current method downloads the entire mp4, and converts
that mp4 to an mp3 using ffmpeg. However, I have a feeling there is a way to only download the audio from the file online,
 thus decreasing the size of the file needed to be downloaded and, in turn, improving the latency. 
2. Start audio analysis while user's file is being uploaded. This would decrease the amount of time taken to upload and analyze the song. 
I believe this could potentially be done by reading the user's uploaded file as an audio stream, thus taking the first 20 seconds as a packet
 and analyzing everything besides the duration with the small 20 second packet. 
3. Re-approach the user interface to facilitate a more user-friendly experience. 

Connections to lecture:

- Many of my javascript functions were lambda functions! These anonymous functions were often times passed as parameters in other functions,
 thus acting as callback functions. 

Learning Process:

1. I began by understanding the fundamental structure behind applications with a backend and frontend, since designing a node application
 required a thorough understanding of the request response structure between the client and the server. 
2. After which, I started playing around with and picking up javascript by watching online tutorial videos and relating it to 
my knowledge of other object-oriented programming languages like c++.
3. Then, I began doing my research on machine-learning. I found lots of interesting articles and videos about supervised learning, 
back-propagation, and perceptron networks. I found that the best option was kNN due to the fact that it is efficient for 
classification programs with more than 2 features being analyzed. 
4. I did some light reading on UI design, quickly picking up HTML and CSS.
5. I moved to implement the functionality I desired! The most difficult problems were associated with generating XML HTTP Requests after the
song was analyzed. I had to figure out JSON structure, and, most importantly, realize that requests and responses to and from the server 
can only be strings!
6. Finally, I realized the benefit of dynamic HTML pages and learned about pug.

This project was an incredible learning experience for me, and I am so proud to say I completed it. 
