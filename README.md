# Sentinel-3 LST Python Downloader & Processor
Downloading and processing Sentinel-3 Land Surface Temperature (LST) data using ESA SNAP's Python interface (snappy). 

## 1. Data Download Module: Download_Sen3LSTzip.ipynb
Python notebook for downloading Sentinel-3 Land Surface Temperature (LST) data in ZIP format. 
Uses the Copernicus Data Space Ecosystem OData API: https://documentation.dataspace.copernicus.eu/APIs/OData.html

Requirements:
- Valid Copernicus Data Space account credentials (username/password)
- Python requests library for API communication

## 2. Processing Module: SNAPPY_Sen3Preprocess.ipynb 
Python notebook for Sentinel-3 data preprocessing using ESA SNAP's snappy Python interface.

Processing workflow:
1. **Subsetting** - Geographic extraction using polygon boundaries
2. **Reprojection**
3. **Cloud Masking** - Band math operation to apply:
   - Remove Clouds using Probabilistic cloud mask (Bayesian approach)
4. **Quality Filtered Export**  
   - Saves output only when:  
     - Valid (non-NaN) pixels > user-defined threshold (default: 100)  
   - Output format: GeoTIFF

System Requirements:
- ESA SNAP installed locally
- snappy Python interface properly configured
- Adequate disk space for temporary processing files
