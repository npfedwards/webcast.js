Webcast
=======

This file and its corresponding repository documents the webcast protocol for streaming audio and video data using
[websockets](http://en.wikipedia.org/wiki/WebSocket).

Documentation
-------------

<table>
  <tr><td><img src="https://rawgithub.com/savonet/webcast/master/misc/webcast.svg" alt="Webcast Flowchart" title="Webcast Flowchart"/></td></tr>
  <tr><td>The Webcast Flowchart</td></tr>
</table>

### Description

The webcast protocol is used to send multimedia data to a streaming server using websockets. It is designed to be implemented
in browsers, thus providing a readily available browser client to stream local files and live media (webcam video, microphone audio).

### How to test?

#### Client

The `examples/client/` directory of this repository contains a client example, sending mp3 encoded data, using 
[libshine.js](https://github.com/savonet/shine/tree/master/js) or raw PCM data.

You can start the client by executing `make` in the repository. You will need a functional `python` binary 
with the `SimpleHTTPServer` module.

Once started, you can point your browser to [http://localhost:8000/](http://localhost:8000/).

#### Server

The `examples/server/` directory contains a demo server, written in [NodeJS](http://nodejs.org/). In order to run it, you
will need a functional node install. Once this is done, you can execute `npm install` in the `server/` directory
and then `cake run` and you should be good to go!

Alternatively, a fully functional implementation of the protocol is available in
[liquidsoap](https://github.com/savonet/liquidsoap). To test it, you can simply run liquidsoap with the following
command line:
```
liquidsoap 'output.ao(fallible=true,audio_to_stereo(input.harbor("mount",port=8080)))'
```

### Webcast.js API

See [API](https://github.com/webcast/webcast.js/blob/master/API.md)

### Protocol Specifications

See [SPECS](https://github.com/webcast/webcast.js/blob/master/SPECS.md)
