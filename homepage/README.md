#

## :speech_balloon: Online Messaging Service
- Created an online messaging service similiar to Slack.
- Used Python and `Flask` as the server framework.

| /signin | /newchannel |
:-------------------------:|:-------------------------:
<img src="screenshots/login.PNG" width="400"> | <img src="screenshots/channel.PNG" width="400">
| user can sign in | user can create new channel |

| /channel |
:-------------------------:|
<img src="screenshots/chat.PNG" width="400"> |
| user can send text messages in real-time within a channel |


- Utilized __different methods of connnection__ between client and server:
  1) In general, `GET & POST requests and responses` (defined in application.py).
     - the javascript function for creating a new channel is not ajax (even though the action is defined in javascript, it is the same as creating a form in html; it submits a form via POST request and then the server sends a response to render the entire page. The function is merely defined in javascript because the form would have to encompass a large portion in the channel.html file if it were to be in the html file.)
  2) `Websockets` for posting new messages in order for persistent connection (because making request everytime is inefficient) and broadcasting messages to all users.
  3) `Ajax` for changing channels so that the sidebar remains the same while only the main content part is modified. (Websockets have problem with blockages and ajax is simplier for rest apis)
- For the purpose of focusing on practicing javascript, channels and messages are stored as global variables instead of in databases. For this reason, they will be initialized every time the server restarts.

