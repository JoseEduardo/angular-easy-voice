# Angular Easy Voice

Is a voice command library.

## Installation
```html
bower install angular-easy-voice --save
```

## Add dependencies to the <head> section of your main html:
```html
<script src="bower_components/angular-easy-voice/dist/EasyVoice.min.js"></script>
```

## Add module
```javascript
MODULE NAME: 'angular-easy-voice';

angular.module('myApp', ['angular-easy-voice'])
       .controller('myCtrl', function('$scope', EasyVoice){
              console.log(EasyVoice);
         });
```
## Basic usage
```javascript
// The first parameter is the phrase that will turn on the voice command.
EasyVoice.initWatch('Ok Google', {
    lang: 'pt-BR', // language is optional, default: 'en-US'
    debug: false // Shows the user's speech
}, false); // true or false to come active
```
## Stop
```javascript
EasyVoice.stopWatch();
```
## Example Simple Command
```javascript
EasyVoice.addCommand('hello', function(){
    console.log('hello my friend!');
});
```
##Example Start-based command
```javascript
//Command will be executed when the user phrase starts with "Search people"
EasyVoice.addCommandStartingWith('Search people', function(text){
    console.log(text) // Whole text
});
```
## Example Speech
```javascript
  //The first parameter is speech, The second parameter is the language
  // language is optional, default: 'en-US'
  EasyVoice.reproduce('Hello my friend.', 'en-US');
```

#Add words
```javascript
  EasyVoice.addWord("Gumga");  // or ["Gumga", "Other"]
```
#Translate
```javascript
EasyVoice.setTranslate({
    speakNow: 'Speak Now',
    notUnderstand : 'Not understand.',
    tryAgain : 'Try again.',
    checkMicrophone: 'Please, check your microphone.',
    listening: 'listening...'
});
```
## Installation of dependencies for use or development
```
npm install
```
## Tasks
Run the task 'npm run dev' for the development.
Run the task 'npm run prod' generating the minified file.
