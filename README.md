# FAWNCalc MVP

## Overview
FAWNCalc is a tool designed to compare and analyze the performance of various **System on Chips (SoCs), Single Board Computers (SBCs), and System on Modules (SoMs)**. Users can upload system specifications, manually add new systems, and visualize their performance using bar charts and radar charts.

## Features
- **Upload System Database**: Users can upload a JSON file with system definitions.
- **Manually Add New Systems**: Input specifications directly into the app.
- **Download System Database**: The current database can be downloaded for offline use.
- **Visualization**:
  - **Bar Chart**: Displays CPU MIPS and efficiency scores.
  - **Radar Chart**: Compares CPU performance, memory bandwidth, and power efficiency.
- **Local Storage Persistence**: All user-added systems persist in local storage.

## Installation

### Prerequisites
Ensure you have the following installed:
- **Node.js** (v14+ recommended)
- **npm** or **yarn**

### Clone the Repository
```sh
git clone https://github.com/wjkennedy/sonoffawncalc.git
cd sonoffawncalc
```

### Install Dependencies
```sh
npm install  # or yarn install
```

### Run the Application
```sh
npm run dev  # or yarn dev
```
This will start a local development server, typically at `http://localhost:3000/`.

## Usage

### Uploading a System Database
1. Click the **Upload JSON** button.
2. Select a JSON file that matches the system schema.
3. The system list updates automatically.

### Adding a New System Manually
1. Enter details into the form under **Create a New System**.
2. Click **Add System** to save the entry.
3. The system will be added to local storage and displayed in the table and charts.

### Downloading the Current Database
Click on the **Download Current Database** link in the header to save the current system data as a JSON file.

## Data Schema
Each system entry should follow this structure:
```json
{
  "soc": "Rockchip RK3588",
  "architecture": "ARMv8.2-A",
  "cores": 8,
  "threads": 8,
  "clockSpeedGHz": 2.4,
  "cpuMIPS": 42000,
  "cacheL1KB": 512,
  "cacheL2KB": 4096,
  "cacheL3KB": 8192,
  "fp64GFLOPS": 280,
  "simdExtensions": ["NEON"],
  "memoryType": "LPDDR5",
  "memoryBandwidthGBps": 68,
  "memoryChannels": 4,
  "maxRAMGB": 32,
  "busInterfaces": ["PCIe Gen3", "AXI"],
  "networkBandwidthGbps": 2.5,
  "pciELanes": 8,
  "usbPorts": ["USB 3.2", "USB-C"],
  "wireless": ["WiFi 6", "Bluetooth 5.0"],
  "storageInterfaces": ["NVMe", "SDIO"],
  "tdpWatts": 15,
  "efficiencyScore": 2800.0,
  "processNodeNM": 8,
  "aiAcceleration": "Rockchip NPU",
  "securityFeatures": ["TrustZone"],
  "cryptoExtensions": ["AES-NI"],
  "useCase": "SBC, Edge Computing"
}
```

## Extending FAWNCalc

### Adding New Features
1. Fork the repository and clone your fork.
2. Create a new feature branch:
   ```sh
   git checkout -b feature-new-component
   ```
3. Modify the React components or database logic.
4. Test your changes locally.
5. Commit and push your changes:
   ```sh
   git commit -m "Added new component"
   git push origin feature-new-component
   ```
6. Open a pull request.

### Modifying Charts
- The charts are built using `recharts`. Modify `FAWNCalcMVP.js` to add new data fields.
- Ensure labels and axis configurations match the expected schema.

### Adding an API Backend
- Currently, FAWNCalc is **local-storage based**.
- To integrate an API, update `handleFileUpload()` and `handleAddSystem()` to send/receive data from a server.

## License
This project is licensed under the MIT License.

