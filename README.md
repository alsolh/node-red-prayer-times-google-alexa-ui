# node-red-prayer-times-google-alexa-ui
Prayer times flow to call api and announce prayer times in alexa, google assistant and show in node red ui

![Alt text](2021-12-27_16-06-37.png.png?raw=true "Node Red Flow")

```
[
    {
        "id": "de2b66d6.0ccf18",
        "type": "tab",
        "label": "Prayer Times",
        "disabled": false,
        "info": ""
    },
    {
        "id": "f476330c.63b79",
        "type": "inject",
        "z": "de2b66d6.0ccf18",
        "name": "",
        "topic": "",
        "payload": "1",
        "payloadType": "num",
        "repeat": "3600",
        "crontab": "",
        "once": true,
        "onceDelay": "",
        "x": 110,
        "y": 120,
        "wires": [
            [
                "8a4c435c.5dd21"
            ]
        ]
    },
    {
        "id": "f23e0be8.048318",
        "type": "http request",
        "z": "de2b66d6.0ccf18",
        "name": "Prayer Times",
        "method": "GET",
        "ret": "obj",
        "url": "",
        "tls": "",
        "x": 600,
        "y": 120,
        "wires": [
            [
                "1f443032.f8d35",
                "123bbbff.71b164",
                "5b549aac.fadb14",
                "cf274b0c.c176a8",
                "3bc6c160.2eef1e",
                "c45e3966.f18b78",
                "34f6dc40.fda0c4",
                "d0b1a4b0.8b2c08",
                "4cc23770.facc78",
                "6c9687eb.bb8168",
                "3b5ec015.456df",
                "c4e35244.aee7b"
            ]
        ]
    },
    {
        "id": "1f443032.f8d35",
        "type": "ui_text",
        "z": "de2b66d6.0ccf18",
        "group": "8a8c9849.8939a8",
        "order": 2,
        "width": 0,
        "height": 0,
        "name": "",
        "label": "Fajr",
        "format": "{{msg.payload.data.timings.Fajr}}",
        "layout": "row-spread",
        "x": 920,
        "y": 260,
        "wires": []
    },
    {
        "id": "123bbbff.71b164",
        "type": "ui_text",
        "z": "de2b66d6.0ccf18",
        "group": "8a8c9849.8939a8",
        "order": 3,
        "width": 0,
        "height": 0,
        "name": "",
        "label": "Sunrise",
        "format": "{{msg.payload.data.timings.Sunrise}}",
        "layout": "row-spread",
        "x": 930,
        "y": 300,
        "wires": []
    },
    {
        "id": "5b549aac.fadb14",
        "type": "ui_text",
        "z": "de2b66d6.0ccf18",
        "group": "8a8c9849.8939a8",
        "order": 4,
        "width": 0,
        "height": 0,
        "name": "",
        "label": "Dhuhr",
        "format": "{{msg.payload.data.timings.Dhuhr}}",
        "layout": "row-spread",
        "x": 920,
        "y": 340,
        "wires": []
    },
    {
        "id": "cf274b0c.c176a8",
        "type": "ui_text",
        "z": "de2b66d6.0ccf18",
        "group": "8a8c9849.8939a8",
        "order": 5,
        "width": 0,
        "height": 0,
        "name": "",
        "label": "Asr",
        "format": "{{msg.payload.data.timings.Asr}}",
        "layout": "row-spread",
        "x": 920,
        "y": 380,
        "wires": []
    },
    {
        "id": "3bc6c160.2eef1e",
        "type": "ui_text",
        "z": "de2b66d6.0ccf18",
        "group": "8a8c9849.8939a8",
        "order": 6,
        "width": 0,
        "height": 0,
        "name": "",
        "label": "Maghrib & Iftar",
        "format": "{{msg.payload.data.timings.Maghrib}}",
        "layout": "row-spread",
        "x": 950,
        "y": 420,
        "wires": []
    },
    {
        "id": "4cc23770.facc78",
        "type": "ui_text",
        "z": "de2b66d6.0ccf18",
        "group": "8a8c9849.8939a8",
        "order": 7,
        "width": 0,
        "height": 0,
        "name": "",
        "label": "Isha",
        "format": "{{msg.payload.data.timings.Isha}}",
        "layout": "row-spread",
        "x": 920,
        "y": 460,
        "wires": []
    },
    {
        "id": "c45e3966.f18b78",
        "type": "ui_text",
        "z": "de2b66d6.0ccf18",
        "group": "200a22ea.3be1de",
        "order": 2,
        "width": 0,
        "height": 0,
        "name": "",
        "label": "Imsak",
        "format": "{{msg.payload.data.timings.Imsak}}",
        "layout": "row-spread",
        "x": 920,
        "y": 220,
        "wires": []
    },
    {
        "id": "d0b1a4b0.8b2c08",
        "type": "ui_text",
        "z": "de2b66d6.0ccf18",
        "group": "200a22ea.3be1de",
        "order": 1,
        "width": 0,
        "height": 0,
        "name": "",
        "label": "Midnight",
        "format": "{{msg.payload.data.timings.Midnight}}",
        "layout": "row-spread",
        "x": 930,
        "y": 500,
        "wires": []
    },
    {
        "id": "34f6dc40.fda0c4",
        "type": "ui_text",
        "z": "de2b66d6.0ccf18",
        "group": "87e9445b.576e18",
        "order": 1,
        "width": 0,
        "height": 0,
        "name": "",
        "label": "Date",
        "format": "{{msg.payload.data.date.readable}}",
        "layout": "row-spread",
        "x": 920,
        "y": 180,
        "wires": []
    },
    {
        "id": "134e83ee.ffc3dc",
        "type": "comment",
        "z": "de2b66d6.0ccf18",
        "name": "APIs",
        "info": "https://aladhan.com/prayer-times-api#GetCalendarByCitys\nhttp://ip-api.com/json",
        "x": 89.5,
        "y": 56.99999809265137,
        "wires": []
    },
    {
        "id": "8a4c435c.5dd21",
        "type": "function",
        "z": "de2b66d6.0ccf18",
        "name": "",
        "func": "var url= \"http://api.aladhan.com/timingsByCity?city=Ajman&country=UAE&method=4\";\nmsg.url = url;\n\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 430,
        "y": 120,
        "wires": [
            [
                "f23e0be8.048318"
            ]
        ]
    },
    {
        "id": "6c9687eb.bb8168",
        "type": "ui_text",
        "z": "de2b66d6.0ccf18",
        "group": "8a8c9849.8939a8",
        "order": 1,
        "width": 0,
        "height": 0,
        "name": "",
        "label": "Methode",
        "format": "{{msg.payload.data.meta.method.name}}",
        "layout": "row-spread",
        "x": 930,
        "y": 540,
        "wires": []
    },
    {
        "id": "c4e35244.aee7b",
        "type": "function",
        "z": "de2b66d6.0ccf18",
        "name": "",
        "func": "flow.set(\"prayerTimes\",msg.payload.data.timings);\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 670,
        "y": 280,
        "wires": [
            [
                "3b5ec015.456df"
            ]
        ]
    },
    {
        "id": "f5fdecbb.1adc4",
        "type": "inject",
        "z": "de2b66d6.0ccf18",
        "name": "",
        "topic": "",
        "payload": "prayerTimes",
        "payloadType": "flow",
        "repeat": "60",
        "crontab": "",
        "once": false,
        "onceDelay": 0.1,
        "x": 130,
        "y": 240,
        "wires": [
            [
                "88efe48d.106f08"
            ]
        ]
    },
    {
        "id": "3b5ec015.456df",
        "type": "debug",
        "z": "de2b66d6.0ccf18",
        "name": "",
        "active": true,
        "tosidebar": true,
        "console": false,
        "tostatus": false,
        "complete": "false",
        "x": 910,
        "y": 120,
        "wires": []
    },
    {
        "id": "88efe48d.106f08",
        "type": "function",
        "z": "de2b66d6.0ccf18",
        "name": "",
        "func": "var d = new Date();\nvar n = d.toTimeString();\nvar found = false;\nvar prayerName = \"\";\nfor (var k in msg.payload)\n        {if(n.substring(0, 5) == msg.payload[k]){\n            found = true;\n            prayerName = k;\n        }\n}\n//prayerName = \"This is a test\";\n//found = true;\nif(found){\nmsg.payload = \"it is time for \" + prayerName  + \" prayer!\";\nmsg.emitVolume = 100;\nreturn msg;\n}",
        "outputs": 1,
        "noerr": 0,
        "x": 250,
        "y": 300,
        "wires": [
            [
                "37a14cf1.97d464",
                "db6e065.66065f8",
                "3b5ec015.456df",
                "dccdc3b2.cdcc1"
            ]
        ]
    },
    {
        "id": "8b779072.02629",
        "type": "exec",
        "z": "de2b66d6.0ccf18",
        "command": "/home/alsolh/ha-alexa-tts-master/alexa_remote_control.sh -d",
        "addpay": true,
        "append": "",
        "useSpawn": "false",
        "timer": "",
        "oldrc": false,
        "name": "",
        "x": 780,
        "y": 600,
        "wires": [
            [
                "c4b1418e.8db7f"
            ],
            [
                "c4b1418e.8db7f"
            ],
            [
                "c4b1418e.8db7f"
            ]
        ]
    },
    {
        "id": "c4b1418e.8db7f",
        "type": "debug",
        "z": "de2b66d6.0ccf18",
        "name": "",
        "active": true,
        "tosidebar": true,
        "console": false,
        "tostatus": false,
        "complete": "true",
        "x": 930,
        "y": 680,
        "wires": []
    },
    {
        "id": "37a14cf1.97d464",
        "type": "function",
        "z": "de2b66d6.0ccf18",
        "name": "",
        "func": "msg.payload = \"\\\"alsolh's Echo Show\" + \"\\\"\" + \" -e speak:\" + msg.payload.replace(/ /g, '_');\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 270,
        "y": 620,
        "wires": [
            [
                "8b779072.02629",
                "82e6df7.7403a2"
            ]
        ]
    },
    {
        "id": "82e6df7.7403a2",
        "type": "debug",
        "z": "de2b66d6.0ccf18",
        "name": "",
        "active": true,
        "tosidebar": true,
        "console": false,
        "tostatus": false,
        "complete": "false",
        "x": 410,
        "y": 680,
        "wires": []
    },
    {
        "id": "db6e065.66065f8",
        "type": "function",
        "z": "de2b66d6.0ccf18",
        "name": "",
        "func": "msg.payload = \"\\\"Mohammed's Echo Dot\" + \"\\\"\" + \" -e speak:\" + msg.payload.replace(/ /g, '_');\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 270,
        "y": 740,
        "wires": [
            [
                "8b779072.02629",
                "82e6df7.7403a2"
            ]
        ]
    },
    {
        "id": "dccdc3b2.cdcc1",
        "type": "cast-to-client",
        "z": "de2b66d6.0ccf18",
        "name": "",
        "url": "",
        "contentType": "",
        "message": "",
        "language": "en",
        "ip": "192.168.1.129",
        "port": "",
        "volume": "",
        "x": 490,
        "y": 520,
        "wires": [
            []
        ]
    },
    {
        "id": "8a8c9849.8939a8",
        "type": "ui_group",
        "z": "",
        "name": "Prayer Times",
        "tab": "f5b358a4.ab2828",
        "order": 3,
        "disp": true,
        "width": "6",
        "collapse": false
    },
    {
        "id": "200a22ea.3be1de",
        "type": "ui_group",
        "z": "",
        "name": "Sunna",
        "tab": "f5b358a4.ab2828",
        "order": 4,
        "disp": true,
        "width": "6",
        "collapse": false
    },
    {
        "id": "87e9445b.576e18",
        "type": "ui_group",
        "z": "",
        "name": "Position",
        "tab": "a7a7d3f8.a5c6e",
        "order": 1,
        "disp": true,
        "width": "6",
        "collapse": false
    },
    {
        "id": "f5b358a4.ab2828",
        "type": "ui_tab",
        "z": "",
        "name": "Prayer Times",
        "icon": "dashboard"
    },
    {
        "id": "a7a7d3f8.a5c6e",
        "type": "ui_tab",
        "z": "",
        "name": "Prayer Times",
        "icon": "accessibility",
        "disabled": false,
        "hidden": false
    }
]
```
