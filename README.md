# MessengerBotTutorial
Tutorials based on AutoReplyBot using javascript.

## Setup
https://play.google.com/store/apps/details?id=com.xfl.kakaotalkbot  
https://play.google.com/store/apps/details?id=com.google.android.wearable.app

## Settings
If you installed two applications then open MessengerBot application. Then, touch a hand icon. if you do, will be open setting activity that control permissions about Notification access. then active MessengerBot and Wear OS by Google. This's all of settings that you have to do.

## Make your script
If you did Settings, touch bottom right's a plus button and write a script's name that you want. In my case, I wrote 'normal'.
```js
const scriptName="normal.js";

function response(room, msg, sender, isGroupChat, replier, ImageDB, packageName, threadId){
    /*(이 내용은 길잡이일 뿐이니 지우셔도 무방합니다)
     *(String) room: 메시지를 받은 방 이름
     *(String) msg: 메시지 내용
     *(String) sender: 전송자 닉네임
     *(boolean) isGroupChat: 단체/오픈채팅 여부
     *replier: 응답용 객체. replier.reply("메시지") 또는 replier.reply("방이름","메시지")로 전송
     *(String) ImageDB.getProfileImage(): 전송자의 프로필 이미지를 Base64로 인코딩하여 반환
     *(String) packageName: 메시지를 받은 메신저의 패키지 이름. (카카오톡: com.kakao.talk, 페메: com.facebook.orca, 라인: jp.naver.line.android
     *(int) threadId: 현재 쓰레드의 순번(스크립트별로 따로 매김)     *Api,Utils객체에 대해서는 설정의 도움말 참조*/
    
}

function onStartCompile(){
    /*컴파일 또는 Api.reload호출시, 컴파일 되기 이전에 호출되는 함수입니다.
     *제안하는 용도: 리로드시 자동 백업*/
    
}

//아래 4개의 메소드는 액티비티 화면을 수정할때 사용됩니다.
function onCreate(savedInstanceState,activity) {
    var layout=new android.widget.LinearLayout(activity);
    layout.setOrientation(android.widget.LinearLayout.HORIZONTAL);
    var txt=new android.widget.TextView(activity);
    txt.setText("액티비티 사용 예시입니다.");
    layout.addView(txt);
    activity.setContentView(layout);
}
function onResume(activity) {}
function onPause(activity) {}
function onStop(activity) {}
```
Because We will not develop deeply, delete some lines. When I developed, I used only response(). Then we get a simple script, like this.
```js
function response(room, msg, sender, isGroupChat, replier, ImageDB, packageName, threadId){
    
}
```
Good. Then let's code a **Hello World!**
## Hello World!
```js
function response(room, msg, sender, isGroupChat, replier, ImageDB, packageName, threadId){
    replier.reply("Hello World!")
}
```
Write this script, and then compile. Compile is can be run as press and hold a save button. If you did, then active your script. Don't ask me How to active please. Then, try your script by chatting. Then you can see a result that bot reply only "Hello World!" whatever what you send. When user use your bot, if bot reply only "Hello World!" without considering content then user will be get annoyed. So we have to write bot to reply specifically.
