wapi
==============

wapi is a simple async HTTP library which uses LÖVE threads

This github repository is a fork of the original wapi library by [Ulydev](https://github.com/Ulydev/wapi) updating it for support with lua-https (Love2D 12)

![image](https://media.giphy.com/media/l0MYxXHK9yvD8yJNu/giphy.gif)

Setup
----------------
Require library and update it
```lua
local wapi = require "webapi"

function love.update(dt)
  wapi.update()
end
```

Make request
```lua
request = wapi.request({
  method = "GET",
  url = "http://jsonplaceholder.typicode.com/posts/1"
}, function (code, headers, body)

  print(body)

end)
```

Usage
----------------

```lua
wapi.request(args, callback)
```
args supports the following fields:
- method: string
- url: string
- headers: table

Read more about the fields in the [LÖVE wiki](https://love2d.org/wiki/lua-https)

```lua
wapi.update()
```
update all running requests

```lua
wapi.cancel(request)
```
cancel an active request
