# HttpSession expiration notification with WebSocket

This is a technique I invented to solve a very old problem in web programming. It works by persuading the browser to open a WebSocket connection to the server. The connect request is intercepted and the WebSocket Session is added as an attribute to the HttpSession. When the HttpSession expires, the WebSocket Session is retrieved and used to send a message to the browser. To get notified when the HttpSession is about to be destroyed, you need to write an HttpSessionListener and implement its sessionDestroyed method. This method is called right before the HttpSession is invalidated.

For more details, see this blog: http://blogs.brainysoftware.com/welcom/entry/tracking-session-expiration-in-the
