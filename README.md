Interesting [project](https://github.com/elizabethsiegle/accelerate-sf-hackathon-streamlit) from recent SF AI conference  Hackathon implements internal GPTs along with media uploads, providing accessible AI / GPT code. Not a complex project and can be run on streamlit with some small mods to finesse the student access to secure [openAI key issue](https://community.openai.com/t/recommended-way-to-deal-with-api-key-s-for-students-in-programming-courses/335259/9). Proxy is used to swap an easily acquired proxy-token for much harder to get api key on openai.   
A second project detailed below at the *hosted proxy* link makes it possible for students to sign up, getting a token that is used as a front-end call in place of native calls on the openai API. This is an example of a reverse proxy sitting in front of a protected resource, which openai API is until you have a working api key.   
Get started by following instructions below: 
#### create python virtual environment for this project & this app
```
conda create --name 311accel python=3.10
conda activate 311accel
```
python 3.9 will also work.  
new to [virtual environments](https://chat.openai.com/share/c963bdd8-1e82-4dc8-be92-3939b62a87da) in python?  
prior to working on the project, familiarize yourself with **python virtual environments**  
Some people use venv, some prefer [conda](https://www.youtube.com/watch?v=sDCtY9Z1bqE)
#### using git , clone the app and go to the home directory of the local git clone 
```
git clone https://github.com/elizabethsiegle/accelerate-sf-hackathon-streamlit.git
cd accelerate-sf-hackathon-streamlit
```

#### install the apps dependencies 
```
python3 -m pip install -r requirements.txt

OR
while read requirement; do conda install --yes $requirement; done < requirements.txt
```

#### See the instructions for  "OPENAI_API_KEY"
[hosted proxy](https://github.com/PawanOsman/ChatGPT/tree/main#use-our-hosted-api-reverse-proxy)  
```
go to the discord server
sign up  and wait for 10 min to elapse  
follow instructions to get a personal key to the proxy
this key used as **OPENAI_API_KEY** in conjunction with api calls to endpt. below  
api.pawan.krd/v1/completions  
```
#### Twilio account credentials
use the [dashboard](https://console.twilio.com/us1/account/keys-credentials/api-keys) for account, SID, and token  
the sample app uses Twilio sms  
dashboard will create/list your [twilio phone number](https://console.twilio.com/us1/develop/phone-numbers/manage/incoming)  
#### ENV vars - manual edit on .streamlit/secrets.toml file
create toml file at project path above
on streamlit run on localhost  
3 env vars below will be read by the runtime and passed to *st.secrets*
```
OPENAI_API_KEY = "<your-key>"
TWILIO_ACCOUNT_SID = "<your-value>"
TWILIO_AUTH_TOKEN = "<your-token>"
```
#### Edits to app.py to insert the hosted proxy in place of api.openai.com 
change [urls and print statements](https://github.com/rowntreerob/demo311/blob/master/public/dif_1.png)  
change [model and stop props](https://github.com/rowntreerob/demo311/blob/master/public/dif_2.png)
above in 2 places *data, data2*  
change [twilio number and print statements](https://github.com/rowntreerob/demo311/blob/master/public/dif_3.png)  
#### run the app using streamlit for host-server  
```
 rob@penguin:~/src/accelerate-sf-hackathon-streamlit$ streamlit run app.py  
```
```
  stdout--
  You can now view your Streamlit app in your browser.

  Local URL: http://localhost:8501
  Network URL: http://100.115.92.199:8501 
  ```
     
   
Brief instructions with [the app](https://youtu.be/kYDMzAhe8dw)   	
