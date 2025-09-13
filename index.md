# VertexEA - Advanced Trading Expert Advisor

## Overview

VertexEA is a sophisticated MetaTrader 5 Expert Advisor designed for advanced algorithmic trading. It integrates multiple technical indicators across different timeframes and establishes real-time communication with external machine learning systems for intelligent trade signal generation and execution.

## Key Features

### Multi-Timeframe Analysis
- **Primary Timeframes**: M1, M5, M30
- **Secondary Timeframes**: Automatically opens additional charts for higher timeframes
  - M1 → M5, M30
  - M5 → M30, H4  
  - M30 → H4, D1
- **Multi-chart Management**: Opens and manages multiple chart windows with synchronized indicators

### Technical Indicators Integration
- **Moving Averages**: SMA (200), EMA (20, 10)
- **MACD**: Fast (12), Slow (26), Signal (9)
- **Volume Analysis**: Tick volume monitoring
- **SMC Indicator**: Smart Money Concepts integration
- **Custom Indicators**: Support for additional custom indicators

### Real-Time Data Collection
- **CSV Export**: Comprehensive data logging with timestamp, OHLC, and all indicator values
- **Multi-timeframe Data**: Captures indicator values from all active timeframes
- **Historical Data**: Maintains complete trading session history for analysis

### External System Integration
- **Socket Communication**: TCP/IP connection to external Python servers
- **Real-time Streaming**: Continuous price and indicator data transmission
- **Bidirectional Communication**: Receives trading signals and predictions from ML systems
- **Auto-reconnection**: Robust connection management with automatic retry logic

### Machine Learning Integration
- **Transformer Models**: Integration with transformer-based time series prediction models
- **Signal Processing**: Receives and processes ML-generated trading signals
- **Classification Models**: Support for machine learning classification algorithms
- **Real-time Predictions**: Live market analysis and opportunity detection

### Trading Capabilities
- **Auto-Trading**: Configurable automatic trade execution
- **Manual Alerts**: Alert system for manual trade entries
- **Signal Processing**: Intelligent signal filtering and validation
- **Risk Management**: Built-in risk management protocols

### Strategy Testing
- **Backtesting Support**: Full compatibility with MetaTrader 5 Strategy Tester
- **Optimization**: Parameter optimization capabilities
- **Performance Analytics**: Comprehensive testing and performance metrics
- **Test Completion Tracking**: Automated test completion file generation

## Architecture

### Core Components

#### 1. Main EA (`VertexEA.mq5`)
- Primary Expert Advisor file
- Orchestrates all components
- Manages initialization and cleanup
- Handles tick processing and new bar detection

#### 2. Configuration (`Config.mqh`)
- Centralized configuration management
- Timeframe mapping and validation
- Indicator parameter definitions
- Data structure definitions

#### 3. Indicators Management (`Indicators.mqh`)
- Multi-timeframe indicator creation and management
- Chart window management
- Data collection and validation
- Indicator handle lifecycle management

#### 4. Socket Communication (`Socket.mqh`)
- TCP/IP client implementation
- Connection management and error handling
- Data transmission and reception
- Auto-reconnection logic

#### 5. CSV Data Export (`Csv.mqh`)
- Structured data export functionality
- Multi-timeframe data formatting
- File management and error handling
- Data validation and formatting

#### 6. Socket Library (`socketlib.mqh`)
- Low-level socket operations
- Windows Sockets API integration
- Error handling and diagnostics
- Network protocol support

## Installation

### Prerequisites
- MetaTrader 5 platform
- Windows operating system
- Network connectivity for external system communication

### Setup Instructions
1. Copy all files to your MetaTrader 5 `Experts` directory
2. Ensure `socketlib.mqh` is in the `Include` directory
3. Compile the Expert Advisor in MetaEditor
4. Configure external Python server connection parameters
5. Attach to desired chart (M1, M5, or M30)

### Configuration
- **Server IP**: Configure in `Config.mqh` (default: 127.0.0.1)
- **Server Port**: Configure in `Config.mqh` (default: 8888)
- **Indicators**: Modify periods in `Config.mqh` as needed
- **CSV Output**: Customize filename and format in `Config.mqh`

## Usage

### Live Trading
1. Attach VertexEA to a supported timeframe chart
2. Ensure external Python server is running
3. Monitor connection status in Expert Advisor logs
4. Review CSV data files for analysis
5. Configure auto-trading or manual alert settings

### Strategy Testing
1. Open MetaTrader 5 Strategy Tester
2. Select VertexEA from Expert Advisor list
3. Configure test parameters and date range
4. Run backtest or optimization
5. Review results and performance metrics

### Data Analysis
- CSV files contain comprehensive market data
- Multi-timeframe indicator values for correlation analysis
- Timestamp data for temporal analysis
- Volume and price action data for market microstructure analysis

## File Structure

```
VertexEA/
├── VertexEA.mq5          # Main Expert Advisor
├── Config.mqh            # Configuration and data structures
├── Indicators.mqh        # Indicator management
├── Socket.mqh           # Socket communication
├── Csv.mqh              # CSV data export
├── socketlib.mqh        # Socket library
├── ChronoBasedEA.mq5    # Legacy version
├── ChronoBasedEA.mqproj # Project file
└── README.md            # This file
```

## Data Output

### CSV Format
The EA generates comprehensive CSV files containing:
- **Timestamp**: Bar time and date
- **Price Data**: Open, High, Low, Close
- **Main Timeframe Indicators**: SMA, EMA, MACD, Volume
- **Secondary Timeframe 1**: All indicators from higher timeframe
- **Secondary Timeframe 2**: All indicators from highest timeframe
- **Data Validation**: Proper handling of missing or invalid data

### Real-time Streaming
- **Price Updates**: Continuous bid price streaming
- **Indicator Values**: Real-time indicator data transmission
- **Signal Reception**: ML-generated trading signals
- **Status Updates**: Connection and system status information

## External System Requirements

### Python Server
- TCP/IP server implementation
- Transformer-based time series models
- Machine learning classification algorithms
- Real-time data processing capabilities
- Signal generation and transmission

### Network Configuration
- Stable network connection
- Configurable IP address and port
- Firewall configuration for socket communication
- Error handling and reconnection logic

## Performance Considerations

### Optimization
- Efficient indicator calculation
- Minimal memory footprint
- Optimized data structures
- Streamlined socket communication

### Reliability
- Robust error handling
- Automatic reconnection
- Data validation
- Graceful degradation

### Scalability
- Multi-symbol support capability
- Configurable indicator sets
- Flexible timeframe combinations
- Extensible architecture

## Development Status

This project is currently under active development. The core functionality is implemented and operational, with ongoing enhancements for:

- Advanced signal processing algorithms
- Enhanced machine learning integration
- Improved risk management features
- Extended indicator support
- Performance optimizations

## Support and Documentation

For technical support, configuration assistance, or feature requests, please refer to the project documentation or contact the development team.

## License

Copyright © 2025 LesleyJJ. All rights reserved.

---

**Note**: This Expert Advisor is designed for advanced users with experience in algorithmic trading and machine learning integration. Proper testing and risk management are essential before live trading implementation.

The full source code is not publicly available. If you are interested in accessing the source code or collaborating, please [contact me](mailto:jacobjohnlesley@gmail.com).
