# Sensing Systems — Project Ideas & Resources

A curated guide to sensing and remote sensing projects, organized by topic group. Each project is tagged with cost tier (💚 Affordable / 🟡 Moderate / 🔴 Advanced) and difficulty (⭐ = beginner → ⭐⭐⭐⭐⭐ = expert).

---

## Topic Group: Sonar & Acoustic Sensing

---

### Ultrasonic Distance Logger
💚 Affordable (~$3) | ⭐☆☆☆☆
**Hardware:** ESP32 + HC-SR04 ultrasonic sensor
**Tags:** `sonar` `infrastructure` `beginner`
**What it does:** Logs distance measurements over time to detect objects, vehicles, or water level. Sonar works by emitting a sound pulse and timing the echo return — same physics as submarine sonar at centimeter scale.
**Real-world analog:** Parking sensors, tank level monitoring, flood gauges
**Resources:**
- [HC-SR04 with ESP32 — Random Nerd Tutorials](https://randomnerdtutorials.com/esp32-hc-sr04-ultrasonic-arduino/)
- [Arduino NewPing library](https://www.arduino.cc/reference/en/libraries/newping/)

---

### Passive Acoustic Wildlife Monitor
💚 Affordable (~$20) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + USB microphone or I2S mic module
**Tags:** `acoustic` `environmental` `conservation` `intermediate`
**What it does:** Records audio clips triggered by sound events. Runs BirdNET or YAMNet to identify species from audio. Bioacoustic monitoring is how conservation researchers track bird populations, bat activity, and frog breeding cycles without cameras.
**Real-world analog:** Cornell Lab BirdNET, SmartWilds acoustic pipeline, AudioMoth field recorders
**Resources:**
- [BirdNET-Analyzer](https://github.com/kahst/BirdNET-Analyzer)
- [YAMNet on Raspberry Pi](https://www.tensorflow.org/hub/tutorials/yamnet)
- [AudioMoth field recorder](https://www.openacousticdevices.info/audiomoth)

---

### Noise Pollution Mapper
💚 Affordable (~$20) | ⭐⭐⭐☆☆
**Hardware:** ESP32 + INMP441 I2S microphone + GPS module
**Tags:** `acoustic` `urban` `environmental` `intermediate`
**What it does:** Logs dB SPL measurements with GPS coordinates to build a noise pollution map of a neighborhood or campus. Same methodology as WHO environmental noise guidelines monitoring.
**Real-world analog:** EU Environmental Noise Directive, SoundPrint crowdsourced noise database
**Resources:**
- [INMP441 with ESP32](https://randomnerdtutorials.com/esp32-i2s-microphone-inmp441/)

---

### Bat Echolocation Detector
🟡 Moderate (~$80–$200) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + Dodotronic Ultramic or Pettersson M500 USB ultrasonic mic
**Tags:** `acoustic` `ultrasonic` `environmental` `intermediate`
**What it does:** Records bat echolocation calls (20–120 kHz) and classifies species from call frequency, duration, and interpulse interval. Same approach as wind farm bat impact assessments and conservation monitoring.
**Real-world analog:** Bat Conservation International monitoring, AudioMoth bat surveys, wind farm impact assessments
**Resources:**
- [BatDetect2 classifier](https://github.com/macaodha/batdetect2)
- [AudioMoth ultrasonic guide](https://www.openacousticdevices.info/)

---

### Synthetic Aperture Sonar (SAS) Simulator
🟡 Moderate (~$150) | ⭐⭐⭐⭐☆
**Hardware:** Laptop + audio interface + transducers in water tank
**Tags:** `sonar` `signal processing` `defense` `advanced`
**What it does:** Simulates underwater sonar imaging using audio transducers. Implements delay-and-sum beamforming to reconstruct 2D images from acoustic echoes — the same principle as SAS used by naval mine-hunting vehicles.
**Real-world analog:** NOAA underwater terrain mapping, naval mine detection, fish finder sonar
**Resources:**
- [PySDR signal processing guide](https://pysdr.org/)
- [NumPy FFT/beamforming](https://numpy.org/doc/stable/reference/routines.fft.html)

---

### Acoustic Gunshot Localization
🔴 Advanced (~$300) | ⭐⭐⭐⭐☆
**Hardware:** 4x Raspberry Pi + microphones + network switch
**Tags:** `acoustic` `defense` `urban` `advanced`
**What it does:** Deploys a microphone array and uses TDOA (time difference of arrival) between nodes to triangulate the 3D origin of an impulsive sound event. Same principle as ShotSpotter, deployed in 100+ US cities.
**Real-world analog:** ShotSpotter gunshot detection, military acoustic shot detection, volcano eruption localization
**Resources:**
- [PyRoomAcoustics beamforming](https://github.com/LCAV/pyroomacoustics)

---

### DIY Underwater ROV Sonar
🟡 Moderate (~$150) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + BlueRobotics Ping sonar altimeter + waterproof housing
**Tags:** `sonar` `water` `environmental` `intermediate`
**What it does:** Builds a sonar depth profiler mountable on a small ROV. Generates 1D depth profiles or, with movement, basic bathymetric maps — same principle as ship-mounted multibeam echosounders used for ocean floor mapping.
**Real-world analog:** NOAA nautical chart bathymetry, fish finder sonar, submarine cable route surveys
**Resources:**
- [BlueRobotics Ping sonar](https://bluerobotics.com/store/sensors-sonars-cameras/sonar/ping-sonar-r2-rp/)
- [OpenROV community](https://openrov.com/)

---

### Acoustic Underwater Mammal Detector
🟡 Moderate (~$80–$200) | ⭐⭐⭐⭐☆
**Hardware:** Raspberry Pi + hydrophone + waterproof housing
**Tags:** `acoustic` `sonar` `water` `environmental` `advanced`
**What it does:** Records underwater audio and classifies cetacean vocalizations (whale calls, dolphin clicks) using a fine-tuned classifier. Passive acoustic monitoring is the primary way marine mammals are tracked without tagging.
**Real-world analog:** NOAA PIFSC passive acoustic monitoring, Scripps Whale Acoustics Lab
**Resources:**
- [DolphinEar hydrophone](https://www.dolphinear.com/)
- [Watkins Marine Mammal Sound Database](https://cis.whoi.edu/science/B/whalesounds/)

---

## Topic Group: RADAR & RF Sensing

---

### Software-Defined Radio (SDR) Spectrum Monitor
💚 Affordable (~$30) | ⭐⭐⭐⭐☆
**Hardware:** RTL-SDR dongle + Raspberry Pi or laptop
**Tags:** `RF` `SDR` `defense` `infrastructure`
**What it does:** Captures radio frequency spectrum from 24 MHz to 1.7 GHz. Visualize aircraft ADS-B transponders, ship AIS signals, weather balloon radiosondes, and RF interference patterns.
**Real-world analog:** Air traffic ADS-B surveillance, ship tracking AIS, NOAA weather radar receiver, SIGINT
**Resources:**
- [RTL-SDR quickstart](https://www.rtl-sdr.com/rtl-sdr-quick-start-guide/)
- [GNU Radio project](https://www.gnuradio.org/)
- [OpenSky ADS-B network](https://opensky-network.org/)

---

### Weather Balloon Radiosonde Receiver
💚 Affordable (~$30) | ⭐⭐☆☆☆
**Hardware:** RTL-SDR dongle + laptop
**Tags:** `RF` `SDR` `atmospheric` `beginner`
**What it does:** Receives live telemetry from NOAA weather balloon radiosondes launched twice daily. Decodes temperature, humidity, pressure, and GPS altitude profiles in real time with no hardware beyond the SDR dongle.
**Real-world analog:** NOAA upper-air sounding network, atmospheric reanalysis datasets
**Resources:**
- [Radiosonde Auto RX](https://github.com/projecthorus/radiosonde_auto_rx)
- [SondeHub global tracker](https://sondehub.org/)

---

### Lightning Detection Network (Blitzortung)
💚 Affordable (~$15) | ⭐⭐⭐☆☆
**Hardware:** ESP32 + AS3935 Franklin lightning sensor
**Tags:** `RF` `electromagnetic` `atmospheric` `citizen science`
**What it does:** The AS3935 detects the RF discharge signature of nearby lightning. With multiple nodes sharing timestamps, TDOA locates each strike within a few kilometers — the same technique Blitzortung uses with thousands of volunteer stations globally.
**Real-world analog:** Blitzortung.org global lightning map, NOAA National Lightning Detection Network, Vaisala GLD360
**Resources:**
- [AS3935 lightning sensor hookup](https://learn.sparkfun.com/tutorials/as3935-lightning-detector-hookup-guide/all)
- [Blitzortung participant guide](https://www.blitzortung.org/en/participate.php)

---

### LoRa Weather Station Mesh
💚 Affordable (~$40 total) | ⭐⭐⭐☆☆
**Hardware:** 2x ESP32 + LoRa SX1276 modules + BME280 sensor
**Tags:** `RF` `agriculture` `environmental` `intermediate`
**What it does:** Builds a multi-node sensor mesh transmitting temperature, humidity, and pressure over LoRa (915 MHz) to a central base station without WiFi. Same radio architecture as IoT agricultural monitoring networks.
**Real-world analog:** Smart agriculture sensor grids, wildfire weather monitoring, remote environmental sensing
**Resources:**
- [ESP32 LoRa with SX1276](https://randomnerdtutorials.com/esp32-lora-rfm95-transceiver-arduino-ide/)
- [The Things Network LoRaWAN](https://www.thethingsnetwork.org/)

---

### Meteor Radar via FM Scatter
💚 Affordable (~$30–$60) | ⭐⭐⭐⭐☆
**Hardware:** RTL-SDR dongle + directional antenna
**Tags:** `RF` `RADAR` `atmospheric` `citizen science`
**What it does:** Detects meteor entry by capturing forward scatter off ionized meteor trails using distant FM transmitters as illuminators — a passive bistatic radar. Each meteor appears as a brief "ping" in the RF spectrum.
**Real-world analog:** Canadian Meteor Orbit Radar (CMOR), GRAVES meteor radar (France)
**Resources:**
- [Society for Popular Astronomy meteor section](https://www.popastro.com/main_spa1/meteor/)

---

### RF Fingerprinting Device Identifier
🔴 Advanced (~$50–$350) | ⭐⭐⭐⭐☆
**Hardware:** RTL-SDR or HackRF One + laptop
**Tags:** `RF` `SDR` `defense` `cybersecurity`
**What it does:** Captures the unique RF emission characteristics of wireless devices and trains a classifier to identify them by hardware "fingerprint" — even when using the same protocol. Used in drone detection and unauthorized device tracking.
**Real-world analog:** DARPA RFMLS program, DHS RF fingerprinting for border security, DroneID systems
**Resources:**
- [HackRF One](https://greatscottgadgets.com/hackrf/)
- [DeepSig RF fingerprinting dataset](https://www.deepsig.ai/datasets)

---

### CubeSat Telemetry Ground Station
🟡 Moderate (~$100–$300) | ⭐⭐⭐⭐☆
**Hardware:** RTL-SDR + Yagi antenna + rotator
**Tags:** `RF` `SDR` `space` `citizen science`
**What it does:** Receives beacon telemetry from LEO CubeSats as they pass overhead. Decodes health data including power levels, temperature, and attitude. Contributing to SatNOGS network lets your station receive globally.
**Real-world analog:** SatNOGS global ground station network, AMSAT satellite tracking
**Resources:**
- [SatNOGS network](https://satnogs.org/)
- [GPredict satellite tracker](https://gpredict.oz9aec.net/)

---

### Passive Coherent Radar (FM Radio)
🟡 Moderate (~$60 hardware) | ⭐⭐⭐⭐⭐
**Hardware:** 2x RTL-SDR + Raspberry Pi 4 or laptop
**Tags:** `RADAR` `passive sensing` `defense`
**What it does:** Passive Coherent Location (PCL) uses ambient FM radio signals as illuminators to detect aircraft and vehicles without transmitting anything. Cross-correlation reveals range and Doppler shift of targets — actual stealth radar.
**Real-world analog:** NATO passive radar systems, AVEILLANT Gamekeeper 16U, silent border surveillance
**Resources:**
- [Passive radar with RTL-SDR](https://www.rtl-sdr.com/passive-radar-with-two-coherent-rtl-sdrs/)
- [PyPassiveRadar](https://github.com/passive-radar/PyPassiveRadar)

---

### FMCW Radar Gesture & Presence Detection
🔴 Advanced (~$300–$500) | ⭐⭐⭐⭐⭐
**Hardware:** Jetson Nano + TI IWR1843BOOST or Acconeer XR112
**Tags:** `RADAR` `defense` `infrastructure`
**What it does:** FMCW radar detects presence, breathing rate, and hand gestures through walls and in complete darkness. Unlike cameras, radar works through most solid materials — the same principle as automotive blind-spot radar.
**Real-world analog:** Automotive collision avoidance, search-and-rescue through-wall detection, airport ground movement radar
**Resources:**
- [TI mmWave SDK](https://www.ti.com/tool/MMWAVE-SDK)
- [Acconeer developer guide](https://developer.acconeer.com/)
- [OpenRadar community](https://github.com/presenseradar/openradar)

---

### SAR (Synthetic Aperture Radar) Data Processing
🔴 Advanced (free satellite data) | ⭐⭐⭐⭐⭐
**Hardware:** PC or cloud compute only — uses free ESA Sentinel-1 data
**Tags:** `SAR` `RADAR` `environmental` `infrastructure` `defense`
**What it does:** Processes free Sentinel-1 SAR data to detect floods, surface deformation, ship positions, and vegetation change. SAR sees through clouds and works day/night — used to track flood extents during Hurricane Harvey when optical satellites were blocked.
**Real-world analog:** Copernicus Emergency Management flood mapping, NISAR surface deformation, ICEYE rapid response satellite
**Resources:**
- [ESA Sentinel-1 open data](https://scihub.copernicus.eu/)
- [ASF SARVIEWS flood products](https://sarviews-hazards.alaska.edu/)
- [SNAP toolbox for SAR processing](https://step.esa.int/main/toolboxes/snap/)

---

### Ground Penetrating Radar (GPR) Scanner
🔴 Advanced (~$500–$2000) | ⭐⭐⭐⭐⭐
**Hardware:** ImpulseRadar Raptor or DIY UWB radar kit
**Tags:** `RADAR` `infrastructure` `defense` `geophysics`
**What it does:** Pulses ultra-wideband radar into the ground to reconstruct subsurface features from reflections. Used for utility mapping, landmine detection, archaeological survey, and soil moisture profiling — seeing underground without digging.
**Real-world analog:** GSSI SIR-4000 utility locating, HALO Trust landmine detection radar, NASA RIMFAX Mars rover ground radar
**Resources:**
- [OpenGPR project](https://github.com/opengpr/opengpr)
- [GPR data processing with Python](https://readgssi.readthedocs.io/)

---

## Topic Group: LiDAR & Depth Sensing

---

### Photogrammetry & 3D Point Cloud (SfM)
💚 Affordable (camera only) | ⭐⭐⭐⭐☆
**Hardware:** Camera (phone or Pi) + laptop for processing
**Tags:** `LiDAR (SfM)` `computer vision` `infrastructure` `agriculture`
**What it does:** Uses Structure from Motion (SfM) to reconstruct 3D point clouds from overlapping 2D images — the same technique used to map terrain from drone imagery without LiDAR hardware.
**Real-world analog:** Archaeological site mapping, crop field 3D modeling, building damage assessment, MorphoCam distance estimation
**Resources:**
- [COLMAP SfM tool](https://colmap.github.io/)
- [OpenDroneMap](https://www.opendronemap.org/)
- [Open3D point cloud processing](http://www.open3d.org/)

---

### Real-Time LiDAR 3D Mapping (SLAM)
🔴 Advanced (~$400–$600) | ⭐⭐⭐⭐⭐
**Hardware:** Jetson Nano + RPLiDAR A1 or RPLIDAR S2
**Tags:** `LiDAR` `infrastructure` `defense` `robotics`
**What it does:** Runs real-time Simultaneous Localization and Mapping using rotating LiDAR. Generates a 2D or 3D occupancy map. LiDAR uses laser pulses (Time of Flight) — the same principle as autonomous vehicle sensors and drone terrain mapping.
**Real-world analog:** Velodyne/Ouster AV LiDAR, USGS 3DEP national lidar dataset, drone-based forest canopy mapping
**Resources:**
- [RPLiDAR with ROS](https://github.com/Slamtec/rplidar_ros)
- [Cartographer SLAM](https://google-cartographer.readthedocs.io/)
- [USGS 3DEP LiDAR data portal](https://www.usgs.gov/3d-elevation-program)

---

### Drone-Mounted Multispectral + LiDAR Survey
🔴 Advanced (~$800–$3000) | ⭐⭐⭐⭐⭐
**Hardware:** DJI Mini 3 or Mavic + Sentera or MicaSense multispectral camera
**Tags:** `multispectral` `LiDAR` `agriculture` `environmental`
**What it does:** Acquires georeferenced multispectral imagery from the air. Processes into NDVI, NDRE, and false-color composites using OpenDroneMap. Field-level precision agriculture — same tech as commercial crop monitoring services.
**Real-world analog:** Planet Labs SkySat agriculture bands, John Deere See & Spray, NASA ABoVE Arctic vegetation mapping
**Resources:**
- [OpenDroneMap WebODM](https://www.opendronemap.org/webodm/)
- [MicaSense RedEdge documentation](https://support.micasense.com/)
- [QGIS for drone imagery analysis](https://qgis.org/)

---

## Topic Group: Optical & Multispectral Imaging

---

### NDVI Vegetation Index Camera
💚 Affordable (~$35) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + modified NoIR camera + blue filter
**Tags:** `multispectral` `agriculture` `environmental` `intermediate`
**What it does:** Captures near-infrared and visible images, computes NDVI — the ratio satellite imagery uses to measure plant health. Healthy vegetation absorbs red and reflects NIR; stressed plants don't.
**Real-world analog:** Landsat/Sentinel satellite NDVI, precision agriculture crop stress mapping, wildfire burn severity
**Resources:**
- [NDVI with Raspberry Pi](https://publiclab.org/notes/nedhorning/06-01-2014/raspberry-pi-camera-kit-for-ndvi-photography)
- [Public Lab NDVI guide](https://publiclab.org/wiki/ndvi)

---

### Laser Tripwire Perimeter System
💚 Affordable (~$8) | ⭐⭐☆☆☆
**Hardware:** ESP32 + laser diode + photodiode
**Tags:** `optical` `defense` `security` `beginner`
**What it does:** Establishes an invisible laser beam across a corridor or doorway. Detects beam interruption with microsecond precision and triggers an alarm or logs a timestamp. Modulating the laser with a carrier frequency defeats ambient light interference.
**Real-world analog:** Museum exhibit tripwire alarms, warehouse door edge sensors, military perimeter systems
**Resources:**
- [Laser tripwire with Arduino](https://www.instructables.com/Laser-Tripwire-Alarm-System-With-Arduino/)

---

### Tree Phenology Camera (PhenoCam)
💚 Affordable (~$80) | ⭐⭐☆☆☆
**Hardware:** Raspberry Pi + camera + weatherproof housing
**Tags:** `optical` `environmental` `agriculture` `beginner`
**What it does:** Takes fixed time-lapse photographs of a forest canopy or crop field. Extracts the Green Chromatic Coordinate (GCC) index from RGB values to track seasonal greenness — bud burst, peak green, leaf-off dates — with no spectral sensor needed.
**Real-world analog:** PhenoCam Network (Harvard, NEON), USA National Phenology Network
**Resources:**
- [PhenoCam network guide](https://phenocam.nau.edu/webcam/tools/)

---

### All-Sky Aurora Monitor
🟡 Moderate (~$120) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + fish-eye lens + IMX477 camera
**Tags:** `optical` `atmospheric` `space weather` `citizen science`
**What it does:** 180° fish-eye camera captures the full night sky. Software detects aurora events by monitoring green/red channel ratios and pixel intensity changes — a proxy for geomagnetic storm activity.
**Real-world analog:** AuroraMAX all-sky camera network, NOAA Dst geomagnetic index
**Resources:**
- [AllSky Camera software](https://github.com/thomasjacquin/allsky)

---

### Thermal Anomaly Detector
🟡 Moderate (~$50–$120) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + MLX90640 or AMG8833 thermal array sensor
**Tags:** `thermal` `infrared` `infrastructure` `defense` `intermediate`
**What it does:** Produces low-resolution thermal images (32×24 or 8×8 grid) and detects hotspots or temperature anomalies. Same class of sensor used in fever screening, building energy audits, and electronics fault finding.
**Real-world analog:** Building heat loss mapping, electrical panel fault detection, fever screening, wildlife body heat detection at night
**Resources:**
- [MLX90640 Thermal Camera on Pi](https://learn.adafruit.com/adafruit-mlx90640-ir-thermal-camera/python-circuitpython)
- [AMG8833 Grid-Eye sensor](https://www.sparkfun.com/products/14607)

---

### Hyperspectral Leaf Health Scanner
🟡 Moderate (~$60) | ⭐⭐⭐⭐☆
**Hardware:** Raspberry Pi + AS7265x spectral sensor trident
**Tags:** `multispectral` `agriculture` `environmental` `advanced`
**What it does:** Measures reflectance across 18 channels from UV to NIR (410–940 nm). Builds a spectral signature library for plant disease, chlorophyll content, and nitrogen deficiency — the same data Sentinel-2 satellite collects at 10m resolution, here at leaf scale.
**Real-world analog:** Sentinel-2 agriculture bands, precision spraying by spectral anomaly, NASA AVIRIS hyperspectral imager
**Resources:**
- [AS7265x SparkFun hookup guide](https://learn.sparkfun.com/tutorials/as7265x-multi-spectral-scanning-hookup-guide/all)
- [USGS spectral library](https://crustal.usgs.gov/speclab/QueryAll07a.php)

---

### Fruit Ripeness NIR Scanner
🟡 Moderate (~$40) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + AS7263 NIR sensor
**Tags:** `optical` `multispectral` `agriculture` `food` `intermediate`
**What it does:** Measures near-infrared absorbance of fruit to estimate Brix (sugar content) and detect internal bruising non-destructively. Commercial fruit sorting lines use NIR for 100% inspection.
**Real-world analog:** COMPAC sorting systems in apple packing houses, Zeltex handheld Brix meters
**Resources:**
- [AS7263 NIR sensor hookup](https://learn.sparkfun.com/tutorials/as7262-hookup-guide/all)

---

### Passive Optical SETI Receiver
🔴 Advanced (~$200+) | ⭐⭐⭐⭐☆
**Hardware:** Telescope + photomultiplier or fast photodetector + Raspberry Pi
**Tags:** `optical` `astronomy` `space` `citizen science`
**What it does:** Monitors individual star systems for nanosecond-scale optical pulses inconsistent with natural stellar variability — a potential technosignature. Optical SETI is a serious research program at Harvard and UC Berkeley.
**Real-world analog:** Harvard OSETI telescope, Breakthrough Listen optical SETI program
**Resources:**
- [Harvard OSETI program](https://www.cfa.harvard.edu/projects/oseti/)
- [Breakthrough Listen open data](https://seti.berkeley.edu/opendata.html)

---

## Topic Group: Computer Vision & Camera Traps

---

### PIR Motion + BLE Alert System
💚 Affordable (~$2) | ⭐☆☆☆☆
**Hardware:** ESP32 + PIR sensor
**Tags:** `passive IR` `defense` `environmental` `beginner`
**What it does:** Detects motion using passive infrared radiation from body heat. Sends BLE notifications to a phone when triggered. Same principle as security systems, wildlife camera traps, and thermal tripwires.
**Real-world analog:** Perimeter intrusion detection, wildlife camera triggers, occupancy sensing in smart buildings
**Resources:**
- [PIR with ESP32](https://randomnerdtutorials.com/esp32-pir-motion-sensor-interrupts-timers/)
- [ESP32 BLE Tutorial](https://randomnerdtutorials.com/esp32-bluetooth-low-energy-ble-arduino-ide/)
- [Completed Build](https://github.com/Bharathpillai06/Smart-Motion-Sensor)

---

### YOLOv8 Wildlife Camera Trap
🟡 Moderate (~$120) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi 4/5 + camera module + PIR sensor
**Tags:** `vision` `environmental` `conservation` `intermediate`
**What it does:** PIR-triggered image capture with on-device YOLOv8 inference for species detection. Outputs structured CSV per detection with optional GPS projection. Same pipeline as SmartWilds and WildSense.
**Real-world analog:** WWF camera trap networks, MegaDetector deployments, conservation area monitoring
**Resources:**
- [Ultralytics YOLOv8](https://docs.ultralytics.com/)
- [Pi Camera Module v3](https://www.raspberrypi.com/products/camera-module-3/)
- [SmartWilds dataset](https://arxiv.org/abs/2509.18894)

---

### Traffic Flow Counter
🟡 Moderate (~$80) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + camera module
**Tags:** `vision` `infrastructure` `urban` `intermediate`
**What it does:** Runs a YOLO vehicle detector on a fixed camera, counts vehicles crossing a virtual line, classifies by type (car, truck, bicycle), and logs counts with timestamps. Same pipeline as municipal traffic monitoring cameras.
**Real-world analog:** London ULEZ camera network, NYC DOT traffic signal optimization
**Resources:**
- [YOLOv8 vehicle counting](https://docs.ultralytics.com/guides/object-counting/)

---

### Insect Population Counter (UV Trap)
🟡 Moderate (~$70) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + camera + UV LED + light diffuser
**Tags:** `optical` `vision` `agriculture` `environmental` `intermediate`
**What it does:** UV light attracts insects into a camera's field of view. A CV model detects, counts, and classifies insects by species — automating what entomologists currently do by manually counting trap catch overnight.
**Real-world analog:** Trécé PHEROCON smart trap, Trapview digital pest monitoring, FAO desert locust monitoring
**Resources:**
- [AMI-Insect trap paper](https://arxiv.org/abs/2202.09270)
- [iNaturalist insect ID API](https://api.inaturalist.org/v1/docs/)

---

## Topic Group: Environmental & Atmospheric Sensing

---

### Environmental Air Quality Monitor
💚 Affordable (~$10) | ⭐⭐☆☆☆
**Hardware:** ESP32 + MQ-135 gas sensor + DHT22
**Tags:** `chemical sensing` `environmental` `beginner`
**What it does:** Measures CO₂, smoke, temperature, and humidity. Logs to SD card or sends to a web dashboard. Same sensor class as EPA air quality monitoring networks.
**Real-world analog:** Indoor air quality stations, wildfire smoke detection, agricultural greenhouse monitoring
**Resources:**
- [MQ sensor calibration guide](https://www.codrey.com/electronic-circuits/how-to-use-mq135-gas-sensor/)
- [ESP32 + DHT22](https://randomnerdtutorials.com/esp32-dht11-dht22-temperature-humidity-sensor-arduino-ide/)

---

### Wind Speed & Direction Logger
💚 Affordable (~$15–$50) | ⭐⭐☆☆☆
**Hardware:** ESP32 + reed switch anemometer kit or Davis anemometer
**Tags:** `mechanical sensing` `energy` `environmental` `beginner`
**What it does:** Counts cup anemometer rotations per unit time for wind speed; reads wind vane potentiometer for direction. Logs to SD with timestamps. Same sensors used in weather stations and wind farm site assessment.
**Real-world analog:** NOAA ASOS airport weather stations, wind farm micrositing, offshore wind assessment buoys
**Resources:**
- [DIY anemometer with ESP32](https://randomnerdtutorials.com/esp32-wind-speed-anemometer/)
- [Global Wind Atlas](https://globalwindatlas.info/)

---

### Ionospheric TEC Monitor
💚 Affordable (~$50) | ⭐⭐⭐☆☆
**Hardware:** RTL-SDR + GNSS antenna
**Tags:** `RF` `atmospheric` `space weather` `intermediate`
**What it does:** Measures Total Electron Content (TEC) in the ionosphere by comparing signal delay between GPS frequencies. Solar storms and space weather events are directly visible in TEC anomalies.
**Real-world analog:** NASA GNSS TEC monitoring, NOAA Space Weather Prediction Center, SuperDARN ionospheric radar
**Resources:**
- [GNSS-SDR software receiver](https://gnss-sdr.org/)
- [UNAVCO GNSS TEC data](https://www.unavco.org/)

---

### Water Quality Turbidity Sensor
💚 Affordable (~$15) | ⭐⭐☆☆☆
**Hardware:** ESP32 + TSW-10 turbidity sensor + TDS meter
**Tags:** `optical sensing` `environmental` `water` `beginner`
**What it does:** Measures water cloudiness and total dissolved solids in real time. Same parameter monitored by USGS stream gauges and municipal water treatment plants.
**Real-world analog:** EPA Clean Water Act monitoring, river sediment load monitoring, aquaculture pond health
**Resources:**
- [Turbidity sensor with Arduino](https://how2electronics.com/interfacing-turbidity-sensor-with-arduino/)
- [USGS water quality monitoring](https://waterdata.usgs.gov/)

---

### Salinity & pH Ocean Sensor Buoy
🟡 Moderate (~$200) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + Atlas Scientific EZO-pH + EZO-EC probes
**Tags:** `chemical sensing` `water` `environmental` `intermediate`
**What it does:** Logs salinity, pH, and temperature in a weatherproof float enclosure. Ocean acidification is one of the clearest measurable signals of climate change — this builds a real monitoring instrument at low cost.
**Real-world analog:** Argo float network, NOAA Ocean Acidification Program, coral reef bleaching research
**Resources:**
- [Atlas Scientific EZO circuits](https://atlas-scientific.com/embedded-solutions/ezo-circuits/)
- [Argo float data portal](https://argo.ucsd.edu/)

---

## Topic Group: Geophysics & Earth Sensing

---

### Seismic Activity Logger (Geophone)
💚 Affordable (~$8) | ⭐⭐⭐☆☆
**Hardware:** ESP32 + SW-420 vibration sensor or geophone module
**Tags:** `vibration sensing` `geophysics` `intermediate`
**What it does:** Detects ground vibration events, logs timestamps and amplitude. Same sensor class used in oil exploration and earthquake networks — you're building a personal seismometer.
**Real-world analog:** Earthquake early warning, pipeline leak detection via ground vibration, infrastructure monitoring
**Resources:**
- [SW-420 with Arduino](https://how2electronics.com/vibration-sensor-module-sw-420-arduino/)
- [OpenEEW open-source seismic network](https://openeew.com/)

---

### Magnetic Anomaly Detector (MAD)
💚 Affordable (~$5) | ⭐⭐⭐☆☆
**Hardware:** ESP32 + HMC5883L or QMC5883L magnetometer
**Tags:** `magnetometry` `defense` `geophysics` `intermediate`
**What it does:** Logs Earth's magnetic field vector and detects anomalies caused by passing ferrous metal objects — vehicles, buried pipes, unexploded ordnance. Same sensing principle as naval aircraft MAD systems for submarine hunting.
**Real-world analog:** Naval MAD boom, UXO detection, archaeological metal detection surveys
**Resources:**
- [HMC5883L with ESP32](https://randomnerdtutorials.com/esp32-hmc5883l-compass-arduino/)
- [NOAA magnetic field calculator](https://www.ngdc.noaa.gov/geomag/calculators/magcalc.shtml)

---

### Earthquake Early Warning Node (OpenEEW)
💚 Affordable (~$30) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + ADXL355 accelerometer
**Tags:** `vibration` `geophysics` `citizen science` `intermediate`
**What it does:** Joins the OpenEEW distributed seismic network. Detects P-waves and transmits alerts before the slower, more destructive S-waves arrive. A distributed IoT network can provide seconds of warning.
**Real-world analog:** Japan's JMA earthquake early warning, Mexico CIRES network, MyShake smartphone seismic network
**Resources:**
- [OpenEEW hardware guide](https://openeew.com/docs/hardware)
- [ShakeNet seismic network](https://shakenet.raspberryshake.org/)

---

### GPS + IMU Animal Movement Tracker
🟡 Moderate (~$80) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + u-blox NEO-M8N GPS + MPU-6050 IMU
**Tags:** `GPS` `accelerometer` `environmental` `agriculture` `intermediate`
**What it does:** Logs GPS coordinates and 6-axis motion data at configurable intervals. Builds a movement trajectory dataset — lighter version of the GPS collar systems used in wildlife ecology.
**Real-world analog:** Wildlife GPS collars, livestock tracking, vessel AIS tracking
**Resources:**
- [u-blox NEO-M8N with Raspberry Pi](https://gpsd.gitlab.io/gpsd/installation.html)
- [Movebank animal tracking platform](https://www.movebank.org/)

---

### Ground Penetrating Radar (GPR) Scanner
🔴 Advanced (~$500–$2000) | ⭐⭐⭐⭐⭐
**Hardware:** ImpulseRadar Raptor or DIY UWB radar kit
**Tags:** `RADAR` `infrastructure` `defense` `geophysics`
**What it does:** Pulses ultra-wideband radar into the ground to reconstruct subsurface features. Used for utility mapping, landmine detection, archaeological survey, and soil moisture profiling — seeing underground without digging.
**Real-world analog:** GSSI SIR-4000 utility locating, HALO Trust landmine detection, NASA RIMFAX Mars rover ground radar
**Resources:**
- [OpenGPR project](https://github.com/opengpr/opengpr)
- [GPR data processing with Python](https://readgssi.readthedocs.io/)

---

## Topic Group: Medical & Human Sensing

---

### PPG Heart Rate + SpO₂ Monitor
💚 Affordable (~$5) | ⭐⭐☆☆☆
**Hardware:** ESP32 + MAX30102 pulse oximeter sensor
**Tags:** `optical` `medical` `wearable` `beginner`
**What it does:** Uses infrared light absorption to detect blood volume changes with each heartbeat. Extracts heart rate and SpO₂ — same sensor principle as hospital pulse oximeters and smartwatch health sensors.
**Real-world analog:** Hospital bedside monitors, Apple Watch health sensor, COVID pulse oximetry screening
**Resources:**
- [MAX30102 with ESP32](https://how2electronics.com/max30102-pulse-oximeter-heart-rate-sensor-with-arduino/)

---

### EMG Gesture Classifier
🟡 Moderate (~$60) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + MyoWare 2.0 EMG sensor + ADS1115 ADC
**Tags:** `bioelectric` `medical` `wearable` `intermediate`
**What it does:** Captures electromyography signals from surface electrodes on muscle. Trains a classifier to distinguish gestures (fist, open, pinch). Same sensing modality used in prosthetic limb control.
**Real-world analog:** Ottobock prosthetic arm control, CTRL-Labs neural interface, OpenBCI
**Resources:**
- [MyoWare 2.0 hookup guide](https://learn.sparkfun.com/tutorials/myoware-20-muscle-sensor-kit-hookup-guide)
- [OpenBCI community](https://openbci.com/)

---

### Gait Analysis IMU Array
🟡 Moderate (~$30 total) | ⭐⭐⭐☆☆
**Hardware:** 2–4x ESP32 + MPU-6050 IMU
**Tags:** `inertial` `medical` `wearable` `intermediate`
**What it does:** Straps multiple IMUs to legs and feet, fuses accelerometer + gyroscope data to reconstruct joint angles and step patterns. Detects gait asymmetry, cadence, and fall risk.
**Real-world analog:** Vicon motion capture, Xsens MVN wearable mocap, Nike+ running form analysis
**Resources:**
- [Madgwick AHRS filter](https://github.com/xioTechnologies/Fusion)

---

### EEG Brainwave Monitor
🔴 Advanced ($280–$500) | ⭐⭐⭐⭐☆
**Hardware:** Raspberry Pi + OpenBCI Cyton board or Muse S headband
**Tags:** `bioelectric` `medical` `neuroscience` `advanced`
**What it does:** Records EEG signals across multiple scalp electrodes. Classifies alpha, beta, theta, and delta brainwave bands. Enables motor imagery BCI and sleep stage classification.
**Real-world analog:** Emotiv EPOC clinical BCI, Neuralink, sleep staging polysomnography, DARPA neural interface research
**Resources:**
- [OpenBCI documentation](https://docs.openbci.com/)
- [MNE-Python EEG analysis](https://mne.tools/stable/index.html)

---

## Topic Group: Infrastructure & Structural Sensing

---

### Smart Energy Monitor (CT Clamp)
💚 Affordable (~$15) | ⭐⭐☆☆☆
**Hardware:** ESP32 + SCT-013 current transformer clamp + ZMPT101B voltage sensor
**Tags:** `electrical` `energy` `infrastructure` `beginner`
**What it does:** Non-invasively measures AC current using a clamp-on transformer. Computes real power, apparent power, and power factor. Builds a home energy monitor equivalent to commercial smart meters.
**Real-world analog:** Sense home energy monitor, Emporia Vue, commercial smart meters
**Resources:**
- [OpenEnergyMonitor emonLib](https://openenergymonitor.org/emonlib/)

---

### Smart Parking Space Detector
🟡 Moderate (~$10–$80) | ⭐⭐⭐☆☆
**Hardware:** ESP32 + VL53L0X ToF sensor or Raspberry Pi + camera
**Tags:** `vision` `RF` `urban` `infrastructure` `intermediate`
**What it does:** Detects whether a parking space is occupied using either a time-of-flight distance sensor (single space) or computer vision (overhead camera, multiple spaces). Logs occupancy and sends MQTT events to a dashboard.
**Real-world analog:** SFpark San Francisco smart parking, ParkMobile API, Las Vegas downtown smart parking grid
**Resources:**
- [VL53L0X with ESP32](https://randomnerdtutorials.com/esp32-vl53l0x-laser-distance-sensor/)
- [Smart parking CV with YOLOv8](https://docs.ultralytics.com/guides/parking-management/)

---

### Solar I-V Curve Tracer
🟡 Moderate (~$50) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + Si1145 irradiance sensor + DAC/ADC
**Tags:** `optical` `electrical` `energy` `intermediate`
**What it does:** Sweeps current-voltage curves of a solar cell to extract efficiency, fill factor, and maximum power point — core measurements for evaluating solar panel performance degradation.
**Real-world analog:** NREL solar resource assessment, SolarEdge module-level monitoring
**Resources:**
- [Si1145 solar sensor](https://learn.adafruit.com/adafruit-si1145-breakout-board-uv-ir-visible-sensor)

---

### Structural Health Monitor (SHM)
🟡 Moderate (~$100) | ⭐⭐⭐⭐☆
**Hardware:** Raspberry Pi + ADXL355 accelerometer
**Tags:** `vibration` `acoustic` `infrastructure` `advanced`
**What it does:** Monitors bridges or buildings for subtle vibration signatures indicating crack propagation or material fatigue. Runs FFT to extract natural frequency shifts — the primary indicator of structural damage.
**Real-world analog:** ASCE SHM on Golden Gate Bridge, NASA structural health monitoring for aircraft, offshore wind turbine towers
**Resources:**
- [PyOMA operational modal analysis](https://github.com/dagghe/pyOMA)

---

## Topic Group: Agriculture & Food Systems

---

### Soil Moisture & NPK Array
💚 Affordable (~$25) | ⭐⭐☆☆☆
**Hardware:** ESP32 + capacitive soil moisture sensor + RS485 NPK sensor
**Tags:** `chemical` `agriculture` `environmental` `beginner`
**What it does:** Reads volumetric water content and nitrogen/phosphorus/potassium levels. Triggers irrigation relay when moisture drops below threshold.
**Real-world analog:** John Deere Operations Center soil sensors, USDA NRCS soil moisture network
**Resources:**
- [Capacitive soil moisture with ESP32](https://randomnerdtutorials.com/esp32-soil-moisture-sensor-arduino-ide/)

---

### Greenhouse CO₂ + Light Control
💚 Affordable (~$40) | ⭐⭐⭐☆☆
**Hardware:** ESP32 + SCD41 CO₂ sensor + BH1750 light sensor + relay module
**Tags:** `chemical` `optical` `agriculture` `intermediate`
**What it does:** Monitors CO₂ ppm and PAR inside a greenhouse. Automatically controls ventilation and supplemental lighting to optimize plant growth. CO₂ enrichment to 1000–1500 ppm is standard commercial greenhouse practice.
**Real-world analog:** Dutch greenhouse climate computers (Priva, Ridder), vertical farm atmosphere control
**Resources:**
- [SCD41 CO₂ sensor guide](https://learn.adafruit.com/adafruit-scd-40-and-scd-41/python-circuitpython)

---

### Fruit Ripeness NIR Scanner
🟡 Moderate (~$40) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + AS7263 NIR sensor
**Tags:** `optical` `multispectral` `agriculture` `food` `intermediate`
**What it does:** Measures near-infrared absorbance of fruit to estimate Brix (sugar content) and detect internal bruising non-destructively. Commercial fruit sorting lines use NIR for 100% inspection.
**Real-world analog:** COMPAC sorting systems in apple packing houses, Zeltex handheld Brix meters
**Resources:**
- [AS7263 NIR sensor hookup](https://learn.sparkfun.com/tutorials/as7262-hookup-guide/all)

---

### Hyperspectral Soil Carbon Estimator
🔴 Advanced (~$300) | ⭐⭐⭐⭐☆
**Hardware:** Raspberry Pi + Hamamatsu C12666MA micro spectrometer
**Tags:** `multispectral` `agriculture` `environmental` `advanced`
**What it does:** Captures soil reflectance spectrum (340–780 nm) and applies a PLS regression model to estimate soil organic carbon — no lab analysis needed. SOC is both a fertility indicator and a carbon sequestration metric.
**Real-world analog:** LUCAS soil survey hyperspectral library, NASA EMIT soil mineral mapping, carbon farming credit verification
**Resources:**
- [Hamamatsu C12666MA spectrometer](https://www.hamamatsu.com/us/en/product/optical-sensors/spectrometers/mini-spectrometer/C12666MA.html)
- [Open Soil Spectral Library (OSSL)](https://soilspectroscopy.org/)

---

## Topic Group: Defense & Security Sensing

---

### Laser Tripwire Perimeter System
💚 Affordable (~$8) | ⭐⭐☆☆☆
**Hardware:** ESP32 + laser diode + photodiode
**Tags:** `optical` `defense` `security` `beginner`
**What it does:** Establishes a laser beam across a corridor. Detects beam interruption with microsecond precision and triggers an alarm. Modulating the laser with a carrier frequency defeats ambient light interference.
**Real-world analog:** Museum exhibit tripwire alarms, warehouse edge sensors, military perimeter systems
**Resources:**
- [Laser tripwire with Arduino](https://www.instructables.com/Laser-Tripwire-Alarm-System-With-Arduino/)

---

### Magnetic Anomaly Detector (MAD)
💚 Affordable (~$5) | ⭐⭐⭐☆☆
**Hardware:** ESP32 + HMC5883L magnetometer
**Tags:** `magnetometry` `defense` `geophysics` `intermediate`
**What it does:** Detects magnetic field anomalies from ferrous objects — vehicles, buried pipes, unexploded ordnance. Same sensing principle as naval MAD systems for locating submarines.
**Real-world analog:** Naval MAD boom, UXO detection, archaeological metal surveys
**Resources:**
- [HMC5883L with ESP32](https://randomnerdtutorials.com/esp32-hmc5883l-compass-arduino/)

---

### RF Fingerprinting Device Identifier
🔴 Advanced (~$50–$350) | ⭐⭐⭐⭐☆
**Hardware:** RTL-SDR or HackRF One + laptop
**Tags:** `RF` `SDR` `defense` `cybersecurity`
**What it does:** Captures unique RF emission characteristics of wireless devices and trains a classifier to identify them by hardware fingerprint — even when using the same protocol. Used in drone detection and unauthorized device tracking.
**Real-world analog:** DARPA RFMLS program, DHS RF fingerprinting for border security
**Resources:**
- [HackRF One](https://greatscottgadgets.com/hackrf/)
- [DeepSig RF fingerprinting dataset](https://www.deepsig.ai/datasets)

---

### Acoustic Gunshot Localization
🔴 Advanced (~$300) | ⭐⭐⭐⭐☆
**Hardware:** 4x Raspberry Pi + microphones + network switch
**Tags:** `acoustic` `defense` `urban`
**What it does:** Deploys a microphone array and uses TDOA to triangulate the 3D origin of an impulsive sound event. Same principle as ShotSpotter, deployed in 100+ US cities.
**Real-world analog:** ShotSpotter, military acoustic shot detection, volcano eruption localization
**Resources:**
- [PyRoomAcoustics beamforming](https://github.com/LCAV/pyroomacoustics)

---

### Passive Coherent Radar (FM Radio)
🟡 Moderate (~$60 hardware) | ⭐⭐⭐⭐⭐
**Hardware:** 2x RTL-SDR + Raspberry Pi 4
**Tags:** `RADAR` `passive sensing` `defense`
**What it does:** Uses ambient FM radio signals to detect aircraft and vehicles without transmitting. Cross-correlation reveals range and Doppler shift of targets — actual stealth radar with off-the-shelf hardware.
**Real-world analog:** NATO passive radar systems, AVEILLANT Gamekeeper 16U, silent border surveillance
**Resources:**
- [PyPassiveRadar](https://github.com/passive-radar/PyPassiveRadar)

---

### FMCW Radar Through-Wall Detection
🔴 Advanced (~$300–$500) | ⭐⭐⭐⭐⭐
**Hardware:** Jetson Nano + TI IWR1843BOOST
**Tags:** `RADAR` `defense` `infrastructure`
**What it does:** FMCW radar detects presence and breathing rate through walls and in complete darkness. Unlike cameras, radar works through most solid materials.
**Real-world analog:** Search-and-rescue through-wall detection, automotive collision avoidance, airport ground movement radar
**Resources:**
- [TI mmWave SDK](https://www.ti.com/tool/MMWAVE-SDK)
- [OpenRadar community](https://github.com/presenseradar/openradar)

---

## Topic Group: Space & Atmospheric Sensing

---

### Weather Balloon Radiosonde Receiver
💚 Affordable (~$30) | ⭐⭐☆☆☆
**Hardware:** RTL-SDR dongle + laptop
**Tags:** `RF` `SDR` `atmospheric` `citizen science`
**What it does:** Receives live NOAA weather balloon telemetry and decodes temperature, humidity, pressure, and GPS altitude profiles in real time. No hardware beyond the SDR dongle.
**Real-world analog:** NOAA upper-air sounding network, atmospheric reanalysis datasets
**Resources:**
- [Radiosonde Auto RX](https://github.com/projecthorus/radiosonde_auto_rx)
- [SondeHub global tracker](https://sondehub.org/)

---

### Meteor Radar via FM Scatter
💚 Affordable (~$30–$60) | ⭐⭐⭐⭐☆
**Hardware:** RTL-SDR dongle + directional antenna
**Tags:** `RF` `RADAR` `atmospheric` `citizen science`
**What it does:** Detects meteor entry by capturing forward scatter off ionized meteor trails using distant FM transmitters — passive bistatic radar. Each meteor appears as a brief "ping" in the RF spectrum.
**Real-world analog:** Canadian Meteor Orbit Radar (CMOR), GRAVES meteor radar (France)
**Resources:**
- [Society for Popular Astronomy meteor section](https://www.popastro.com/main_spa1/meteor/)

---

### Ionospheric TEC Monitor
💚 Affordable (~$50) | ⭐⭐⭐☆☆
**Hardware:** RTL-SDR + GNSS antenna
**Tags:** `RF` `atmospheric` `space weather` `intermediate`
**What it does:** Measures Total Electron Content (TEC) in the ionosphere by comparing GPS signal delay between frequencies. Solar storms are directly visible in TEC anomalies.
**Real-world analog:** NASA GNSS TEC monitoring, NOAA Space Weather Prediction Center
**Resources:**
- [GNSS-SDR software receiver](https://gnss-sdr.org/)

---

### All-Sky Aurora Monitor
🟡 Moderate (~$120) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + fish-eye lens + IMX477 camera
**Tags:** `optical` `atmospheric` `space weather` `citizen science`
**What it does:** 180° fish-eye camera detects aurora events by monitoring green/red channel ratios — a proxy for geomagnetic storm activity.
**Real-world analog:** AuroraMAX all-sky camera network, NOAA Dst geomagnetic index
**Resources:**
- [AllSky Camera software](https://github.com/thomasjacquin/allsky)

---

### CubeSat Telemetry Ground Station
🟡 Moderate (~$100–$300) | ⭐⭐⭐⭐☆
**Hardware:** RTL-SDR + Yagi antenna + rotator
**Tags:** `RF` `SDR` `space` `citizen science`
**What it does:** Receives beacon telemetry from LEO CubeSats as they pass overhead. Decodes power, temperature, and attitude health data. Contributing to SatNOGS lets your station receive satellite data globally.
**Real-world analog:** SatNOGS global ground station network, AMSAT satellite tracking
**Resources:**
- [SatNOGS network](https://satnogs.org/)
- [GPredict satellite tracker](https://gpredict.oz9aec.net/)

---

### Passive Optical SETI Receiver
🔴 Advanced (~$200+) | ⭐⭐⭐⭐☆
**Hardware:** Telescope + photomultiplier or fast photodetector + Raspberry Pi
**Tags:** `optical` `astronomy` `space` `citizen science`
**What it does:** Monitors star systems for nanosecond optical pulses inconsistent with natural stellar variability — a potential technosignature. Optical SETI is a serious research program at Harvard and UC Berkeley.
**Real-world analog:** Harvard OSETI telescope, Breakthrough Listen optical SETI program
**Resources:**
- [Harvard OSETI program](https://www.cfa.harvard.edu/projects/oseti/)
- [Breakthrough Listen open data](https://seti.berkeley.edu/opendata.html)

---

## Topic Group: Citizen Science & Open Networks

---

### Lightning Detection Network (Blitzortung)
💚 Affordable (~$15) | ⭐⭐⭐☆☆
**Hardware:** ESP32 + AS3935 Franklin lightning sensor
**Tags:** `RF` `electromagnetic` `atmospheric` `citizen science`
**What it does:** AS3935 detects the RF discharge signature of nearby lightning. Multiple nodes sharing timestamps use TDOA to locate each strike within a few kilometers.
**Real-world analog:** Blitzortung.org global lightning map, NOAA National Lightning Detection Network
**Resources:**
- [AS3935 lightning sensor hookup](https://learn.sparkfun.com/tutorials/as3935-lightning-detector-hookup-guide/all)
- [Blitzortung participant guide](https://www.blitzortung.org/en/participate.php)

---

### Earthquake Early Warning Node (OpenEEW)
💚 Affordable (~$30) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + ADXL355 accelerometer
**Tags:** `vibration` `geophysics` `citizen science`
**What it does:** Joins the OpenEEW distributed seismic network. Detects P-waves and transmits alerts before the slower, more destructive S-waves arrive.
**Real-world analog:** Japan's JMA earthquake early warning, Mexico CIRES network, MyShake smartphone network
**Resources:**
- [OpenEEW hardware guide](https://openeew.com/docs/hardware)
- [ShakeNet seismic network](https://shakenet.raspberryshake.org/)

---

### Cosmic Ray Muon Detector
💚 Affordable (~$40) | ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + Geiger-Muller tube (SBM-20) + HV circuit
**Tags:** `particle sensing` `physics` `citizen science`
**What it does:** Detects cosmic ray muons using a Geiger counter circuit. Count rate correlates with altitude, atmospheric pressure, and solar activity. Two coincidence detectors can track muon direction.
**Real-world analog:** CERN's DECO project, CosmicWatch muon detector, IceCube Neutrino Observatory
**Resources:**
- [CosmicWatch detector](https://www.cosmicwatch.lns.mit.edu/)

---

### CubeSat Telemetry Ground Station
🟡 Moderate (~$100–$300) | ⭐⭐⭐⭐☆
**Hardware:** RTL-SDR + Yagi antenna + rotator
**Tags:** `RF` `SDR` `space` `citizen science`
**What it does:** Receives beacon telemetry from LEO CubeSats. Contributing to SatNOGS network lets your station participate in a global satellite ground network.
**Real-world analog:** SatNOGS, AMSAT
**Resources:**
- [SatNOGS network](https://satnogs.org/)

---

## Sensing Modality Quick-Reference

| Modality | Works in Dark | Works Through Clouds | Works Underwater | Range |
|---|---|---|---|---|
| Optical camera | No | No | No | Line-of-sight |
| Thermal / IR | Yes | No | No | Short–medium |
| LiDAR | Yes | Partially | No | 0–300m typical |
| RADAR / SAR | Yes | **Yes** | Partially | Short–1000+ km |
| Sonar / acoustic | N/A | N/A | **Yes** | mm–km (water) |
| Multispectral | No | No | No | Line-of-sight |
| Passive RF / SDR | Yes | Yes | No | km–global |
| Ground Penetrating Radar | Yes | Yes | No | 0–10m subsurface |
| Bioelectric (EMG/EEG) | Yes | Yes | No | Surface contact |
| Magnetometry | Yes | Yes | Partially | cm–100m |

---

## Learning Resources by Topic Group

### Sonar & Acoustic
- [PyRoomAcoustics](https://github.com/LCAV/pyroomacoustics) — beamforming and room acoustics
- [librosa documentation](https://librosa.org/doc/latest/index.html) — Python audio analysis
- [BirdNET-Analyzer](https://github.com/kahst/BirdNET-Analyzer) — bird species from audio
- [BatDetect2](https://github.com/macaodha/batdetect2) — bat species classifier
- [AudioMoth field recorder](https://www.openacousticdevices.info/audiomoth)

### RADAR & RF
- [PySDR — A Guide to SDR and DSP using Python](https://pysdr.org/) — free, excellent
- [RTL-SDR.com blog](https://www.rtl-sdr.com/) — extensive SDR project catalog
- [GNU Radio tutorials](https://wiki.gnuradio.org/index.php/Tutorials) — open-source SDR framework
- [PyPassiveRadar](https://github.com/passive-radar/PyPassiveRadar) — passive coherent location
- [TI mmWave training](https://www.ti.com/tool/MMWAVE-TRAINING) — FMCW radar SDK and labs

### LiDAR & Point Clouds
- [Open3D documentation](http://www.open3d.org/docs/release/) — point cloud processing in Python
- [PDAL point cloud processing](https://pdal.io/)
- [CloudCompare](https://www.cloudcompare.org/) — free, open-source 3D viewer
- [USGS 3DEP LiDAR portal](https://www.usgs.gov/3d-elevation-program) — free national LiDAR data
- [COLMAP SfM tool](https://colmap.github.io/)

### Optical & Multispectral
- [Public Lab NDVI guide](https://publiclab.org/wiki/ndvi)
- [USGS spectral library](https://crustal.usgs.gov/speclab/QueryAll07a.php)
- [Open Soil Spectral Library (OSSL)](https://soilspectroscopy.org/)
- [PhenoCam network](https://phenocam.nau.edu/webcam/tools/)

### Computer Vision
- [Ultralytics YOLOv8 docs](https://docs.ultralytics.com/)
- [OpenCV tutorials](https://docs.opencv.org/4.x/d9/df8/tutorial_root.html)
- [PyImageSearch](https://pyimagesearch.com/) — applied CV tutorials

### Environmental & Earth Observation
- [NASA ARSET training programs](https://appliedsciences.nasa.gov/arset) — free online courses
- [ESA Earth Observation training](https://eo4society.esa.int/trainings/) — SAR, optical, climate
- [Google Earth Engine](https://earthengine.google.com/) — free cloud compute for satellite data
- [ESA SNAP toolbox](https://step.esa.int/main/toolboxes/snap/) — SAR processing
- [ASF SARVIEWS flood products](https://sarviews-hazards.alaska.edu/)

### Medical & BCI
- [MNE-Python](https://mne.tools/stable/index.html) — EEG/MEG signal processing
- [OpenBCI documentation](https://docs.openbci.com/)
- [BCI Competition datasets](https://www.bbci.de/competition/)
- [Madgwick AHRS filter](https://github.com/xioTechnologies/Fusion)

### Citizen Science Platforms
- [SatNOGS network](https://satnogs.org/) — global CubeSat ground station network
- [OpenEEW](https://openeew.com/) — distributed earthquake early warning
- [Blitzortung](https://www.blitzortung.org/) — global lightning detection
- [CosmicWatch](https://www.cosmicwatch.lns.mit.edu/) — cosmic ray muon detectors
- [Breakthrough Listen open data](https://seti.berkeley.edu/opendata.html)

### Embedded Systems (All Tiers)
- [Random Nerd Tutorials](https://randomnerdtutorials.com/) — ESP32 + Raspberry Pi
- [Adafruit Learning System](https://learn.adafruit.com/) — sensors and hardware guides
- [SparkFun hookup guides](https://learn.sparkfun.com/) — every sensor has a walkthrough
- [Raspberry Pi documentation](https://www.raspberrypi.com/documentation/)
- [Think DSP — Digital Signal Processing in Python](https://greenteapress.com/wp/think-dsp/) — free book
