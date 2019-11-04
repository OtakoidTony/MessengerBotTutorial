# Chapter 1 : Calculator

## eval()
eval function have a string parameter and eval function is running input as a sentence. For example, if input is 3\*4 then output is 12. This is veeeeeery comfortable! Right?! **BUT EVAL FUNCTION IS VARY DANGEROUS!** Let me show you a example, if input is a function that is send your he\*\*ai po\*n to fbi...! **~~FBI OPEN UP!!!~~** That's a joke. However some situations like before one can occur! So, ~~for save our he\*\*ai po\*n,~~ we have to write Blacklist or Whitelist. Of course, other solution can be exist. But by the way let our go our path, Blacklist and Whitelist can be used to determine to input is safe to running. Of course, if your friends are trusted, you can make calculator with this.
```js
function response(room, msg, sender, isGroupChat, replier, ImageDB, packageName, threadId){
    replier.reply(eval(msg));
}
```
Veeeeeery Simple. Right?
## Whitelist and Blacklist
In this time, we will use Array.
