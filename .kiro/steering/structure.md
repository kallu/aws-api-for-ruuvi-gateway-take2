# Project Structure

## Root Directory
- `README.md` - Project documentation and overview
- `sample-payload.json` - Example Ruuvi Gateway data payload for testing and reference

## Configuration
- `.kiro/` - Kiro AI assistant configuration and steering rules
- `.git/` - Git version control metadata

## Data Structure Conventions
- Gateway data contains a single `data` object with gateway metadata and sensor readings
- Sensor tags are organized under `data.tags` with MAC address as keys
- Each sensor tag contains standardized fields for environmental and motion data
- Missing sensor values should be represented as `null` rather than omitted

## Naming Conventions
- MAC addresses used as identifiers (format: `XX:XX:XX:XX:XX:XX`)
- Camel case for JSON field names (e.g., `dataFormat`, `accelX`, `movementCounter`)
- Timestamps in Unix epoch format
- Temperature in Celsius, pressure in Pascals, voltage in volts

## Development Guidelines
- Maintain compatibility with Ruuvi Data Format 5 specification
- Preserve all sensor metadata for debugging and analysis
- Handle variable sensor capabilities (some may not report humidity/pressure)
- At this point we want to collect ONLY tag identifier, timestamp, temperature and voltage, sequence number. Other parameters are ignored.