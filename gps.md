# Testing the GPS on Aerocore 2

The following table comes from the Aerocore 2 user manual (2015-07-10) pg 3

| Pin  | Processor | Port | Signal   |
| ---- | --------- | ---- | ------   |
| 1    |           |      | V_OUT (5.0V)*| 
| 2    | Cortex-M4 | PB6  | UART1_TX | 
| 3    | Cortex-M4 | PB7  | UART1_RX | 
| 4    |           |      | VCC_3.3  | 
| 5    |           |      | GNC      | 



\* 5.0V from power multiplexor sourced from battery / USB (battery default)


```
nsh> gps
gps: unrecognized command, try 'start', 'stop', 'test', 'reset' or 'status'
 [-d /dev/ttyS0-n][-f (for enabling fake)][-s (to enable sat info)]
```

by getting the status
```
gps status
```

with GPS connected to connector 9 [1] pg 1 

![Aerocore 2 map](/images/aerocore2map.png)

```
nsh> gps status
gps: protocol: UBX
gps: port: /dev/ttyS0, baudrate: 38400, status: NOT OK
gps: sat info: disabled, noise: 0, jamming detected: NO
gps: position lock: 0D, satellites: 0, last update: 1397.6380ms ago
gps: lat: 0, lon: 0, alt: 0
gps: vel: 0.00m/s, 0.00m/s, 0.00m/s
gps: eph: 0.00m, epv: 0.00m
gps: rate position:       0.00 Hz
gps: rate velocity:       0.00 Hz
gps: rate publication:    0.00 Hz

nsh> gps status
gps: protocol: MTK
gps: port: /dev/ttyS0, baudrate: 38400, status: NOT OK
gps: sat info: disabled, noise: 0, jamming detected: NO
gps: position lock: 0D, satellites: 0, last update: 2124.1530ms ago
gps: lat: 0, lon: 0, alt: 0
gps: vel: 0.00m/s, 0.00m/s, 0.00m/s
gps: eph: 0.00m, epv: 0.00m
gps: rate position:       0.00 Hz
gps: rate velocity:       0.00 Hz
gps: rate publication:    0.00 Hz

nsh> gps status
gps: protocol: UBX
gps: port: /dev/ttyS0, baudrate: 57600, status: NOT OK
gps: sat info: disabled, noise: 0, jamming detected: NO
gps: position lock: 0D, satellites: 0, last update: 1693.0580ms ago
gps: lat: 0, lon: 0, alt: 0
gps: vel: 0.00m/s, 0.00m/s, 0.00m/s
gps: eph: 0.00m, epv: 0.00m
gps: rate position:       0.00 Hz
gps: rate velocity:       0.00 Hz
gps: rate publication:    0.00 Hz

nsh> gps status
gps: protocol: UBX
gps: port: /dev/ttyS0, baudrate: 9600, status: NOT OK
gps: sat info: disabled, noise: 0, jamming detected: NO
gps: position lock: 0D, satellites: 0, last update: 1165.6290ms ago
gps: lat: 0, lon: 0, alt: 0
gps: vel: 0.00m/s, 0.00m/s, 0.00m/s
gps: eph: 0.00m, epv: 0.00m
gps: rate position:       0.00 Hz
gps: rate velocity:       0.00 Hz
gps: rate publication:    0.00 Hz

nsh> gps status
gps: protocol: MTK
gps: port: /dev/ttyS0, baudrate: 38400, status: NOT OK
gps: sat info: disabled, noise: 0, jamming detected: NO
gps: position lock: 0D, satellites: 0, last update:  96.1410ms ago
gps: lat: 0, lon: 0, alt: 0
gps: vel: 0.00m/s, 0.00m/s, 0.00m/s
gps: eph: 0.00m, epv: 0.00m
gps: rate position:       0.00 Hz
gps: rate velocity:       0.00 Hz
gps: rate publication:    0.00 Hz

nsh> gps status
gps: protocol: ASHTECH
gps: port: /dev/ttyS0, baudrate: 115200, status: NOT OK
gps: sat info: disabled, noise: 0, jamming detected: NO
gps: position lock: 0D, satellites: 0, last update: 823.4550ms ago
gps: lat: 0, lon: 0, alt: 0
gps: vel: 0.00m/s, 0.00m/s, 0.00m/s
gps: eph: 0.00m, epv: 0.00m
gps: rate position:       0.00 Hz
gps: rate velocity:       0.00 Hz
gps: rate publication:    0.00 Hz

```


gps disconnected
```
nsh> gps test
gps: PASS


nsh> gps status
gps: protocol: MTK
gps: port: /dev/ttyS0, baudrate: 38400, status: NOT OK
gps: sat info: disabled, noise: 0, jamming detected: NO
gps: position lock: 0D, satellites: 0, last update: 202.8980ms ago
gps: lat: 0, lon: 0, alt: 0
gps: vel: 0.00m/s, 0.00m/s, 0.00m/s
gps: eph: 0.00m, epv: 0.00m
gps: rate position:       0.00 Hz
gps: rate velocity:       0.00 Hz
gps: rate publication:    0.00 Hz
```
