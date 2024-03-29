
## emqttd_sockjs

The plugin could make web browsers(even IE6) talk to the emqttd broker with the awesome Stomp/SockJS library.

The Web Apps could pub/sub messages to/from the emqttd broker and communicate with other MQTT clients.


## Build

**Notice that the [emqttd_stomp](https://github.com/emqtt/emqttd_stomp) plugin is required.**

Git submodule to emqttd/plugins folder after the emqttd_stomp plugin installed.

```
git submodule add https://github.com/emqtt/emqttd_sockjs.git plugins/emqttd_sockjs

make && make dist
```

## Configure

**Default port is 61616**

```erlang
[
  {emqttd_sockjs, [

    {sockjs, []},

    {cowboy_listener, {stomp_sockjs, 61616, 4}},

  ]}
].
```

## Load

```
./bin/emqttd_ctl plugins load emqttd_stomp

./bin/emqttd_ctl plugins load emqttd_sockjs
```


## Demo

http://localhost:61616/index.html


## Author

Contact <feng@emqtt.io> if any issues.

