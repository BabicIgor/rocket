## rocket

This project contains a web UI and mock service backend useful for demonstrating experiments using Active Learning on unstructured text data.

While a pre-alpha, work-in-progress, here is the expected workflow:
The user starts on a domains screen where they select the data domain.  The data domain is the common name of the pool of data the user selects for experimentation.  The Stanford movies review database, 'movies' data domain, is included for all users.

Selecting a domain moves to the concepts screen.  Here you create and delete 'concepts,' or things they want Rocket, a machine learning system, to discover in unstructured text data.  You give the concept a name, description, and add a few keywords.   The field to the right updates with related words as you add keywords.  You can scroll through related words and click the ones that are related to add them to your concept.  When you scroll through related words, for efficiency, the system hides those words you do not select.  Toggling the eye icon shows all related words including those you have previously reviewed.   Remove keywords by clicking the X that appears when hovering over the word.


## To run UI locally

clone this repo, cd into the rocket directory, then install the node packages found in package.json using 
`npm install`

serve up the UI using
`ng serve`

Note:  The current UI is build using @angular/cli@6.1.5.  You can install this version globally using 
`npm install -g @angular/cli@6.1.5`


## To run the mock service API locally

This project includes a mock service layer that provides a means of demonstrating various UI features.  It is written in python, uses Flask, supports CORS, but does not currently have an authentication mechanism.

Assuming python 3.6+ with a local anaconda install, add the unique python dependencies using
`pip install pymagnitude flask_cors`

and then run the run.py under the source/services path
`python run.py`


## To change the pretrained model used for finding similiar words 

If enriching concepts with related words, you will want to either download the pretrained models or stream them from source.
I tend to run them locally but they are between 100MB to 10GB.  An example configuration to run locally, download http://magnitude.plasticity.ai/glove/light/glove.6B.50d.magnitude to the src/service/pretrained_features directory.  (Files greater than 100MB are not stored in GitHub.  To experiment with other pretrained models, change the vector assignment in the file src/service/run.py  (~line 188) using the provided streaming and local file examples.


## Acknowledgements & Credits

Muhammad Yaseen of Explore Logics (Attock, Pakistan) for UI implementation & highlighting code  
Guangjun Zhao (Dandong, China) for interactive concepts UI, concept definition, keyword and nearest word tracking services  




