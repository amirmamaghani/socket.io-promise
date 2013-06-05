socket.io-wildcard
==================

Extends socket.io with a wildcard event.

Examples
=====

```js
var socketio = require( 'socket.io' ),
    socketioWildcard = require( 'socket.io-wildcard' ),
    io = socketioWildcard( socketio ).listen( 8000 );

io.sockets.on( 'connection', function onConnection ( socket ) {
  socket.on( '*', function onWildcard ( eventData, eventName ) {
    console.log( 'eventName', eventName );
    console.log( 'eventData', eventData );
  } );

  socket.emit( 'cake', { 'is a lie': true } );
} );
```