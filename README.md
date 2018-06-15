# pic10C_final_project
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
