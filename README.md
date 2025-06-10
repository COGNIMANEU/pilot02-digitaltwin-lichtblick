# Pilot02 Digital Twin Litchblick
This repository contains a Docker-based version of Lichtblick (https://github.com/lichtblick-suite/lichtblick), adapted as a real-time visualization tool for robotics solutions based on ROS 2. It leverages the capabilities of Foxglove (https://foxglove.dev/) to provide an intuitive and interactive interface for monitoring and analyzing robotic systems in real time.

### Key Features

- Dockerized deployment: Easy to set up and run in isolated environments without complex installation.
- Real-time visualization: Leverages Foxglove for monitoring live ROS 2 data streams (topics, transforms, logs, etc.).
- ROS 2 compatibility: Natively supports ROS 2 message types and tools for robotic system integration.
- 3D visualization: View robot models, environments, and sensor data (e.g., LIDAR, cameras) in an interactive 3D scene.
- Customizable panels: Flexible UI with panels for plotting, logging, time-series data, and more.
- Bag file playback support: Visualize and debug recorded `.db3` or `.mcap` data alongside live streams.
- Isolated environment: Ensures consistent behavior across different systems using containerization.
- Web-based interface: Access the visualization tool through a browser, no local GUI required.
- Multi-topic inspection: Subscribe to and inspect multiple ROS 2 topics in parallel.
- Easy configuration: Supports loading custom layouts and configurations at startup.

## Description

The repository includes the following components:
- Docker setup for easy containerization
- A Docker Compose-based test environment to verify end-to-end functionality

## Guidelines for build and test the component 

### 1. **Build the Main Docker Image:**

In this step, we build the Docker image using the provided `Dockerfile`. The image is named `pilot02-digitaltwin-lichtblick`.

```bash
cd lichtblick
docker build -t pilot02-digitaltwin-lichtblick .
```
Make sure the path to your configuration file is correctly mapped to the Docker container.

### 2. **Run the ROS 2 Container:**

After building the Docker image, you can run the container using the following command:

```bash
docker run pilot02-digitaltwin-lichtblick
```

### 3. **Build and Run the test automation:**

Test automation is integrated by docker-compose file:

Run: 
```bash
docker-compose up --build
```
After execution, you will be able to see at [Lichtblick →](https://localhost:8080) the web based board. By default only two topics with sample data are shown. Cameras and LIDAR demos are shown as follows:

![Board Demo](./test/pilot02-digitaltwin-lichtblick.gif)

Please note that, due to the large size of ROS bag files containing rich data (such as images, LiDAR point clouds, or video streams), example files with this type of content are not included in the repository. You can use your own ROS2 bag files with these types of data to explore more advanced visualizations.

## Contributing

Feel free to open issues or submit pull requests. Contributions are welcome!

## License

This project is licensed under Mozilla Public License v. 2.0 - see the [LICENSE](LICENSE) file for details.