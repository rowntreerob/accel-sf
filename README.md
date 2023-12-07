From an Interesting [project](https://github.com/elizabethsiegle/accelerate-sf-hackathon-streamlit)  implements internal GPTs along with media uploads, providing accessible AI / GPT code. Run it on streamlit with some small mods from [another project](https://github.com/PawanOsman/ChatGPT/tree/main#use-our-hosted-api-reverse-proxy) to finesse the student access to secure keys on openai API.  Proxy is used to swap an easily acquired proxy-token for much harder to get api key on openai.   
A second project detailed below at the *hosted proxy* link makes it possible for students to sign up, getting a token that is used as a front-end call in place of native calls on the openai API. This is an example of a reverse proxy sitting in front of a protected resource, which openai API is until you have a working api key.   
Get started by following instructions below: 

#### clone it and then install the apps dependencies 
```
pip install -r requirements.txt
```

#### See the instructions for  "Use Our Hosted API Reverse"
[hosted proxy](https://github.com/PawanOsman/ChatGPT/tree/main#use-our-hosted-api-reverse-proxy)  
```
go to the discord server mentioned in the link
sign up  and wait for 10 min to elapse  
follow instructions to get a personal key to use with the reverse proxy
this key used as **OPENAI_API_KEY** in conjunction with api calls to endpt. below  
api.pawan.krd/v1/completions  # note calls on the proxy are relayed to openai
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
