# MacTRMNL Proxy Server

This is a silly one-file Ruby application that acts as a proxy server between MacTRMNL and the official TRMNL servers.

It serves up images on TCP port 31337. Simply open a connection and it will fetch the latest image from the API and send it directly over the socket.

The image is a BMP, which is easy(ish) to decode on the Mac. And the refresh rate information is stripped out, so it's the client's responsibility to determine how long to show each screen.

## Installation

The only requirement is Ruby 3. No gems are used.

## Usage

Get the API key from https://usetrmnl.com/devices/current/edit

```sh
export ACCESS_TOKEN="my-device-api-key"

./trmnappl.rb [port]
```

## Testing

Requires netcat (`brew install netcat` on macOS).

```sh
nc localhost 31337 > trmnl.bmp
```

