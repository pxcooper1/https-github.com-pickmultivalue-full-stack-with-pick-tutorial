[![Setting up a GET endpoint](video-thumb.jpg)](https://youtu.be/aKCau-EJA7c)

# How to Set Up REST API Get End Points
We need to startup jAgent in the background and verify it's running.
```
!nohup jbase_agent --config= & 
```
You may have to hit enter for the command prompt to come back.  
  
Fire up your favortie browser and navigate to: [http://localhost:20002/api/wresttest](http://localhost:20002/api/wresttest). This will prove that jAgent is up and running if you see a page full of JSON. It will also setup the WDB.RESOURCE file when it’s accessed for the first time.  
  
### Output JSON with a Program 
The next step is to write a program that outputs JSON for the web. I have prepared a [minimal program available here](https://github.com/pickmultivalue/full-stack-with-pick-tutorial/tree/master/back-end/jbase/setting-up-get-endpoint/GET-API-DEMO.b).

1. `EDIT BP GET-API-DEMO` enter
1. `I` enter 
1. Paste in the [prepared program](https://github.com/pickmultivalue/full-stack-with-pick-tutorial/tree/master/back-end/jbase/setting-up-get-endpoint/GET-API-DEMO.b)
1. enter
1. `FI` enter
1. `BASIC BP GET-API-DEMO` enter
1. `CATALOG BP GET-API-DEMO` enter
  
### Connect jAgent to Program 
Next, we need to wire up jAgent to our new program

1. `EDIT WDB.RESOURCE API*DEMO` enter
1. `I` enter 
1. `P` enter
1. `API FOR GETTING A SINGLE RECORD FROM DEMO-FILE` enter
1. `GET-API-DEMO` enter
1. ` ` (space) enter
1. `1` enter
1. `1` enter
1. enter
1. `FI` enter
  
To verify we that it is working, go back to your browser and navigate to: [http://localhost:20002/api/demo/001](http://localhost:20002/api/demo/001)  
  
This will get us the data in JSON format that is accessible on the web.

## Test with Postman
I like to use a product called postman. Download it for free here: [https://www.postman.com](https://www.postman.com).

1. Launch Postman
1. Click the orange NEW button in the upper left-hand corner
1. Select REQUEST, Name the REQUEST: DEMO GET SINGLE RECORD
1. Select DEMO (last item on the lower left-hand side) for the collection
1. Click SAVE TO DEMO button in lower right-hand corner
1. In the center upper third of the next screen of the URL field type: [http://localhost:20002/api/demo/001](http://localhost:20002/api/demo/001)
1. click SEND
  
You should now see the same output that we received using the browser
This proves it worked and that this data is available to the UI layer to be built in our next video.

  
## License
[MIT](https://opensource.org/licenses/MIT)  
  
Copyright (c) 2020-present, Zumasys
