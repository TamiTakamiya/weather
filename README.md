# Weather MCP Server

A Model Context Protocol (MCP) server that provides weather information using the National Weather Service (NWS) API.

This project is based on the code from [Building an MCP Server](https://modelcontextprotocol.io/docs/develop/build-server).

## Features

- **Weather Alerts**: Get active weather alerts for any US state
- **Weather Forecasts**: Get detailed weather forecasts for any location using latitude/longitude coordinates
- **FastMCP Integration**: Built with FastMCP for easy MCP server deployment
- **Streamable HTTP Transport**: Runs on HTTP for flexible integration

## Installation

This project uses Python 3.12+ and UV for dependency management.

```bash
# Install dependencies
uv sync
```

## Usage

### Running the Server

```bash
python weather.py
```

The server will start on `0.0.0.0:8006` with streamable-http transport.

### Available Tools

#### get_alerts

Get active weather alerts for a US state.

**Parameters:**
- `state` (str): Two-letter US state code (e.g., "CA", "NY", "TX")

**Example:**
```python
await get_alerts(state="CA")
```

#### get_forecast

Get detailed weather forecast for a specific location.

**Parameters:**
- `latitude` (float): Latitude of the location
- `longitude` (float): Longitude of the location

**Example:**
```python
await get_forecast(latitude=37.7749, longitude=-122.4194)
```

The forecast returns the next 5 periods with temperature, wind information, and detailed forecasts.

## Requirements

- Python >= 3.12
- httpx >= 0.28.1
- mcp[cli] >= 1.26.0

## Data Source

This server uses the [National Weather Service API](https://www.weather.gov/documentation/services-web-api), which provides free weather data for US locations.

## License

See LICENSE file for details.
