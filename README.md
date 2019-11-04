# Messenger Bot Tutorial
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
### Specifical Replication
We get a problem that bot reply only "Hello World!" without considering content. But don't be frustrated. This problem can be solved easily with a conditional sentence, if. When you use if sentence, you will be use Boolean. As you know, Boolean is consist of True and False. Oops, although you don't know about Boolean, Never keep in mind. That is just a number. Let me show you a example,
```js
if (true) {
    print("Hello World!");
}
```
That's all. Output will be `Hello World!` because condition is true. With this, we get to able to solve the problem. Try to following script.
```js
function response(room, msg, sender, isGroupChat, replier, ImageDB, packageName, threadId){
    if (msg=='Hello'){
        replier.reply("Hello! Nice to meet you!");
    }
}
```
Then, only when you send 'Hello', bot will reply 'Hello! Nice to meet you!' Like this, if you make some conditional sentence then bot will be able to say appropriately.
### Long Scripts Problem
If you code a lot then you will see your loooooooong script with a lot of if sentences. How can we write shortly? A lot of if sentences isn't seemed to nice. So we get to think how to write shortly. The anwser is using dictionary.
```js
function response(room, msg, sender, isGroupChat, replier, ImageDB, packageName, threadId){
    var msgDict = {'Hello': "Hello World!", 'loli is': "LIFE!!!", 'XD': "lol"};
    if (msg in msgDict){
        replier.reply(msgDict[msg]);
    }
}
```
You can think there's something strange about it, but never keep in mind. ~~**FBI OPEN UP!!!**~~  
If we use only if sentences then our script will be get too long like this.
```js
function response(room, msg, sender, isGroupChat, replier, ImageDB, packageName, threadId){
    if (msg=='Hello'){
        replier.reply("Hello! Nice to meet you!");
    }
    if (msg=='loli is'){
        replier.reply("LIFE!!!");
    }
    if (msg=='XD'){
        replier.reply("lol");
    }
}
```
Of course, this script can be short by deleting lines like this.
```js
function response(room, msg, sender, isGroupChat, replier, ImageDB, packageName, threadId){
    if (msg=='Hello'  ){replier.reply("Hello! Nice to meet you!");}
    if (msg=='loli is'){replier.reply("LIFE!!!");}
    if (msg=='XD'     ){replier.reply("lol");}
}
```
If you know about switch sentence then you will be able to write using switch sentence like this.
```js
function response(room, msg, sender, isGroupChat, replier, ImageDB, packageName, threadId){
    switch(msg){
        case 'Hello' :
            replier.reply("Hello! Nice to meet you!");
            break;
        case 'loli is' :
            replier.reply("LIFE!!!");
            break;
        case 'XD' :
            replier.reply("lol");
            break;
    }
}
```
Well... When we extend conditions, we'd rather use dictionary. With so far is enough to make a simple bot. So, From the next chapter, We will add some function.
