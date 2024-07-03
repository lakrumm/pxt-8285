This is a fork for my personal needs.
## Basic usage

### Grove - UART WiFi V2

Connect to a WiFi and send data via tcp

```blocks

grove.setupWifi(
    SerialPin.P15,
    SerialPin.P1,
    BaudRate.BaudRate115200,
    "test-ssid",
    "test-passwd"
)

basic.forever(() => {
    if (grove.wifiOK()) {
        basic.showIcon(IconNames.Yes)
    } else {
        basic.showIcon(IconNames.No)
    }
    grove.sendTcpMsg("127.0.0.1", "1884", "Hello World!")
    basic.pause(5000)
})


## License

MIT

## Supported targets

* for PXT/calliopemini
