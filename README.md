markdown
# ATOMIC Advanced Anomaly Handler Model Training Script

## Overview

The **ATOMIC Advanced Anomaly Handler Model Training Script** is responsible for training a machine learning model to detect anomalies in shard behavior, resource usage, and node communication. This script uses training data provided by the `advanced-anomaly-handler-training-data` library to build and train the model.

### Author

- **Shawn Blackmore / ATOMIC Development Team**

### License

- SPDX-License-Identifier: ATOMIC-Limited-1.0

## Features

- Utilizes TensorFlow.js for deep learning model training.
- Processes training data for effective anomaly detection.
- Implements logging for monitoring training progress and errors.
- Saves the trained model for future use.

## Prerequisites

Before running the script, ensure you have the following installed:

- [Node.js](https://nodejs.org/) (v12 or later recommended)
- [npm](https://www.npmjs.com/get-npm) (comes with Node.js)

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/your-repo/advanced-anomaly-handler.git
   cd advanced-anomaly-handler
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

## Usage

### Running the Training Script

To start the training process, execute the following command in your terminal:

```bash
node path/to/training/script.js
```

Ensure to replace `path/to/training/script.js` with the actual path to the script.

### Training Process

- The script loads training data from the `advanced-anomaly-handler-training-data` library.
- It preprocesses the data for input into the model.
- The model is built using a sequential structure with layers tuned for anomaly detection.
- Training includes early stopping and model checkpointing.
- The trained model is saved to a specified directory upon completion.

### Logging

The script utilizes **Winston** for logging. Logs will be stored in:
- `../../../Logs/AI/Training/anomalyDetectionModelTraining.log`

Check this log for insights regarding the training progress and any issues that may arise.

## Expected Data Format

The training data used should be structured as follows:

- **shard**: Object containing shard-related metrics.
  - `bounceRate`: Bounce rate of the shard.
  - `size`: Size of the shard.
  - `latency`: Latency associated with the shard.
- **system**: Object containing system-related metrics.
  - `cpuLoad`: Current CPU load of the system.
  - `memoryUsed`: Amount of memory currently used.
  - `memoryFree`: Amount of memory currently free.
- **anomalyType**: The type of anomaly detected.

## Example Data Entry

```json
{
  "shard": {
    "bounceRate": 0.25,
    "size": 100,
    "latency": 50
  },
  "system": {
    "cpuLoad": 30,
    "memoryUsed": 2048,
    "memoryFree": 1024
  },
  "anomalyType": 1 // 1 for anomaly, 0 for no anomaly
}
```

## Contributing

Contributions are welcome! If you would like to contribute to this project, please fork the repository and submit a pull request.

## Acknowledgments

- Special thanks to the ATOMIC Development Team for their efforts in creating this model and related libraries.

For any issues or suggestions, please open an issue on the GitHub repository.
