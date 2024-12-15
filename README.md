# Marine Route Optimization Using Machine Learning

This project implements a machine learning-based approach to optimize marine routes, taking into account various environmental and navigational factors. The system processes AIS (Automatic Identification System) data alongside oceanographic data from CMEMS (Copernicus Marine Environment Monitoring Service) to predict and optimize vessel routes.

## Project Structure

The project consists of two main notebooks:
1. `Data_Collection.ipynb`: Handles data acquisition and initial processing
2. `Model_building.ipynb`: Implements the route optimization model

## Features

- Integration of AIS vessel tracking data
- Environmental data processing from CMEMS
- Route optimization using machine learning
- Real-time data processing capabilities
- Comprehensive data visualization

## Data Sources

The project utilizes data from:
- **AIS Data**: Ship tracking information including:
  - Position (Latitude/Longitude)
  - Speed Over Ground (SOG)
  - Course Over Ground (COG)
  - Vessel characteristics

- **CMEMS Oceanographic Data**:
  - Wave height (VHM0)
  - Wave direction (VMDR)
  - Wave period (VTPK)
  - Water temperature
  - Salinity
  - Ocean depth

## Data Processing Pipeline

### 1. Data Collection
- Download and extract AIS data
- Fetch CMEMS oceanographic data
- Initial data cleaning and formatting

### 2. Preprocessing
- Remove invalid entries:
  - Ships with incorrect status codes
  - Speed outliers (< 7 or > 102.2 knots)
  - Invalid coordinates
  - Invalid heading values (> 361°)
- Calculate vessel characteristics (e.g., Gross Tonnage)
- Standardize timestamps

### 3. Feature Engineering
- Data normalization
- Standardization to 0-1 range
- Outlier removal
- Environmental data integration

## Model Features

The model incorporates the following normalized parameters:
- Course Over Ground (COG)
- Gross Tonnage
- Wave Height (VHM0)
- Wave Direction (VMDR)
- Wave Period (VTPK)
- Water Temperature
- Salinity
- Ocean Thickness

## Installation

1. Clone the repository:
```bash
git clone [repository-url]
```

2. Install required dependencies:
```bash
pip install -r requirements.txt
```

3. Set up API access for CMEMS data

## Usage

1. First, run the data collection notebook:
```bash
jupyter notebook Data_Collection.ipynb
```

2. Then process the data and build the model:
```bash
jupyter notebook Model_building.ipynb
```

## Requirements

- Python 3.10+
- pandas
- numpy
- xarray
- matplotlib
- cartopy
- ftplib
- requests
- zipfile

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License

[MIT License](LICENSE)
