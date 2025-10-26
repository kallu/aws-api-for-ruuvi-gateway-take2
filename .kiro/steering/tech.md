# Technology Stack

## Platform
- **Cloud Provider**: AWS (Amazon Web Services)
- **Architecture**: API Gateway, Lambda and DynamoDB

## Data Format
- **Input**: JSON payloads from Ruuvi Gateway devices received in HTTP POST to API
- **Data Format**: Ruuvi Data Format 5, see sample in sample-payload.json

## Key Data Fields
- Gateway metadata: MAC address, coordinates, timestamp, nonce
- Sensor readings: temperature, humidity, pressure, acceleration (X/Y/Z)
- Device status: RSSI, voltage, movement counter, transmission power
- BLE details: PHY type, channel, measurement sequence numbers

## Development Notes
- Handle null values in sensor data (some sensors may not report all metrics)
- Timestamps are Unix epoch format
- MAC addresses used as unique identifiers for both gateways and sensor tags
- Sensor data includes both environmental and motion detection capabilities

## Implementation Notes
- Lambda functions are written in Python 3
- AWS resources are deployed using Cloudformation templates with AWS::Serverless transfrom to keep it more readable.
- At first you should implement only the bare minimum to make it work. More features will be added later per request. Focus on keeping things simple and easy to understand.