## Instalación de Alexa Skills Kit SDK con Node.js (Alexa-SDK)
El alexa-sdk está disponible de inmediato en [github](https://github.com/alexa/alexa-skills-kit-sdk-for-nodejs) y se puede implementar como un paquete de node.js utilizando el siguiente comando desde su entorno Node.js:
```javascript
npm install --save alexa-sdk
```
Para comenzar a usar el alexa-sdk primero importe la biblioteca. Para hacer esto dentro de su propio proyecto simplemente cree un archivo llamado index.js y agregue lo siguiente a él:
```javascript
var Alexa = require('alexa-sdk');

exports.handler = function(event, context, callback){
    var alexa = Alexa.handler(event, context, callback);
};
```
Esto importará alexa-sdk y configurará un objeto Alexa para que podamos trabajar con él. A continuación, tenemos que manejar los intentos de nuestra habilidad. Alexa-sdk hace que sea sencillo tener una función de disparar un Intento. Por ejemplo, para crear un controlador para 'HelloWorldIntent' simplemente agregamos lo siguiente:
```javascript
var handlers = {
    'HelloWorldIntent': function () {
        this.emit(':tell', 'Hello World!');
    }
};
```
