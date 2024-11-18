<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Robot Control</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #2c3e50;
            color: #ecf0f1;
            text-align: center;
            margin: 0;
            padding: 0;
        }

        .container {
            display: inline-block;
            margin: 40px auto;
            padding: 20px;
            background-color: #34495e;
            border-radius: 12px;
            box-shadow: 0px 4px 20px rgba(0, 0, 0, 0.3);
            width: 350px; /* Tăng chiều rộng của container */
        }

        .top-controls {
            margin-bottom: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .enable-switch {
            display: flex;
            align-items: center;
        }

        .enable-switch label {
            font-size: 1.2rem;
            color: #16a085;
            margin-right: 10px;
        }

        #enableButton {
            background-color: #e74c3c;
            color: white;
            border: none;
            border-radius: 6px;
            padding: 6px 12px; /* Tăng kích thước nút */
            cursor: pointer;
            font-size: 1.2rem; /* Tăng kích thước chữ */
            transition: background-color 0.3s;
        }

        #enableButton.active {
            background-color: #16a085;
        }

        select {
            background-color: #16a085;
            color: #fff;
            padding: 8px;
            border: none;
            border-radius: 8px;
            font-size: 1.2rem; /* Tăng kích thước chữ */
        }

        #cameraButton {
            width: 100%;
            padding: 15px;
            background-color: #e74c3c;
            color: #fff;
            border: none;
            border-radius: 8px;
            font-size: 1.2rem;
            cursor: pointer;
            margin-bottom: 20px;
            transition: background-color 0.3s;
        }

        #cameraButton:hover {
            background-color: #c0392b;
        }

        #cameraFeed {
            padding: 20px;
            background-color: #34495e;
            border: 2px solid #ecf0f1;
            border-radius: 12px;
            margin-bottom: 20px;
            font-size: 1.2rem;
        }

        .control-panel {
            margin: 20px 0;
        }

        .control-row {
            display: flex;
            justify-content: center;
            margin-bottom: 20px; /* Tăng khoảng cách giữa các hàng */
        }

        .control-button {
            background-color: #3498db;
            border: none;
            border-radius: 50%;
            color: #fff;
            padding: 25px; /* Tăng kích thước nút */
            font-size: 2rem; /* Tăng kích thước chữ */
            cursor: pointer;
            width: 80px; /* Tăng kích thước của nút */
            height: 80px; /* Tăng kích thước của nút */
            transition: background-color 0.3s;
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 0 15px; /* Tăng khoảng cách giữa các nút */
        }

        .control-button:hover {
            background-color: #2980b9;
        }

        .control-button:focus {
            outline: none;
        }

        .control-button#stop {
            background-color: #e74c3c;
        }

        .sliders {
            margin-top: 20px;
        }

        .slider {
            margin: 20px 0;
        }

        .slider label {
            display: block;
            font-size: 1.2rem;
            margin-bottom: 5px;
        }

        .slider input {
            width: 100%;
        }

        .slider span {
            font-size: 1.5rem;
            color: #16a085;
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="top-controls">
            <div class="enable-switch">
                <label>STATUS:</label>
                <button id="enableButton" onclick="toggleEnable()">OFF</button>
            </div>
        </div>

        <div class="control-panel">
            <div class="control-row">
                <button class="control-button" id="up" 
                    onmousedown="startSendingCommand('UP')" 
                    onmouseup="stopSendingCommand()" 
                    ontouchstart="startSendingCommand('UP')" 
                    ontouchend="stopSendingCommand()">↑</button>
            </div>
            <div class="control-row">
                <button class="control-button" id="left" 
                    onmousedown="startSendingCommand('LEFT')" 
                    onmouseup="stopSendingCommand()" 
                    ontouchstart="startSendingCommand('LEFT')" 
                    ontouchend="stopSendingCommand()">←</button>
                <button class="control-button" id="stop" onclick="stopCommand()">⦿</button>
                <button class="control-button" id="right" 
                    onmousedown="startSendingCommand('RIGHT')" 
                    onmouseup="stopSendingCommand()" 
                    ontouchstart="startSendingCommand('RIGHT')" 
                    ontouchend="stopSendingCommand()">→</button>
            </div>
            <div class="control-row">
                <button class="control-button" id="down" 
                    onmousedown="startSendingCommand('DOWN')" 
                    onmouseup="stopSendingCommand()" 
                    ontouchstart="startSendingCommand('DOWN')" 
                    ontouchend="stopSendingCommand()">↓</button>
            </div>
        </div>

        <div class="sliders">
            <div class="slider">
                <label>Straight speed: <span id="straightSpeed">0</span></label>
                <input type="range" min="0" max="1" value="0" step="0.1" id="straightSpeedSlider" oninput="updateStraightSpeed()">
            </div>
            <div class="slider">
                <label>Rotation speed: <span id="rotationSpeed">0</span></label>
                <input type="range" min="0" max="1" value="0" step="0.1" id="rotationSpeedSlider" oninput="updateRotationSpeed()">
            </div>
        </div>
    </div>

    <script src="https://unpkg.com/mqtt/dist/mqtt.min.js"></script>
    <script>
        const brokerUrl = 'wss://604b372efa0e444ebbe062ca5d3e2243.s1.eu.hivemq.cloud:8884/mqtt';
        const options = {
            username: 'truong',
            password: 'Lhh12345@@',
            clientId: 'web-client-' + Math.random().toString(16).substr(2, 8),
            protocolVersion: 4,
            clean: true,
        };

        const client = mqtt.connect(brokerUrl, options);

        client.on('connect', function () {
            console.log('Connected to MQTT Broker!');
            sendCommand('RESET');
            sendCommand('DISABLE');
            sendCommand('STOP');
        });

        client.on('error', function (err) {
            console.error('Connection error: ', err);
            client.end();
        });

        let intervalId;
        let enabled = false;

        window.onload = function() {
            // Reset trạng thái khi tải lại trang
            enabled = false;
            const enableButton = document.getElementById('enableButton');
            enableButton.classList.remove('active');
            enableButton.innerText = 'OFF';

            // Reset giá trị các thanh trượt về 0
            document.getElementById('straightSpeedSlider').value = 0;
            document.getElementById('rotationSpeedSlider').value = 0;

            // Hiển thị giá trị 0 trên giao diện
            document.getElementById('straightSpeed').innerText = '0';
            document.getElementById('rotationSpeed').innerText = '0';

            // Gửi lệnh reset đến robot hoặc thiết bị
            sendCommand('RESET');
            sendCommand('STOP');
        };

        function startSendingCommand(command) {
            sendCommand(command);
            intervalId = setInterval(function() {
                sendCommand(command);
            }, 100);
        }

        function stopSendingCommand() {
            clearInterval(intervalId);
            setTimeout(() => {
                sendCommand('STOP');
            }, 100);
        }

        function sendCommand(command) {
            const topic = 'esp8266/client';
            client.publish(topic, command, { qos: 1, retain: true });
            console.log('Sending:', command);
        }

        function updateStraightSpeed() {
            const speed = document.getElementById('straightSpeedSlider').value;
            document.getElementById('straightSpeed').innerText = speed;
            sendCommand(`STRAIGHT_SPEED:${speed}`);
        }

        function updateRotationSpeed() {
            const speed = document.getElementById('rotationSpeedSlider').value;
            document.getElementById('rotationSpeed').innerText = speed;
            sendCommand(`ROTATION_SPEED:${speed}`);
        }

        function toggleEnable() {
            enabled = !enabled;
            const button = document.getElementById('enableButton');
            if (enabled) {
                button.classList.add('active');
                button.innerText = 'ON';
                sendCommand('ENABLE');
            } else {
                button.classList.remove('active');
                button.innerText = 'OFF';
                sendCommand('DISABLE');
                sendCommand('STOP');
            }
        }

        function stopCommand() {
            sendCommand('STOP');
        }
    </script>
</body>
</html>
