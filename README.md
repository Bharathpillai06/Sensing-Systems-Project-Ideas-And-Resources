# Sensing Systems — Project Ideas & Resources

A curated guide to remote sensing and embedded sensing projects, organized by cost tier and difficulty. Tags indicate sensing modality and application domain.

---

## Tier 1 — Affordable ($0–$80)
> SunFounder ESP32 kit, a Raspberry Pi you already own, or just a laptop + cheap sensors

---

### 1. Ultrasonic Distance Logger
**Tags:** `sonar` `infrastructure` `beginner`
**Difficulty:** ⭐☆☆☆☆
**Hardware:** ESP32 + HC-SR04 ultrasonic sensor (~$3)
**What it does:** Logs distance measurements over time to detect objects, vehicles, or water level. Sonar works by emitting a sound pulse and timing the echo return — same physics as submarine sonar, just at centimeter scale.
**Real-world analog:** Parking sensors, tank level monitoring, flood gauges
**Resources:**
- [HC-SR04 with ESP32 — Random Nerd Tutorials](https://randomnerdtutorials.com/esp32-hc-sr04-ultrasonic-arduino/)
- [Arduino Sonar Shield docs](https://www.arduino.cc/reference/en/libraries/newping/)

---

### 2. PIR Motion + BLE Alert System
**Tags:** `passive IR` `defense` `environmental` `beginner`
**Difficulty:** ⭐☆☆☆☆
**Hardware:** ESP32 + PIR sensor (~$2)
**What it does:** Detects motion using passive infrared radiation from body heat. Sends BLE notifications to a phone when triggered. Passive IR is the same principle used in security systems, wildlife camera traps, and thermal tripwires.
**Real-world analog:** Perimeter intrusion detection, wildlife camera triggers, occupancy sensing in smart buildings
**Resources:**
- [PIR with ESP32](https://randomnerdtutorials.com/esp32-pir-motion-sensor-interrupts-timers/)
- [ESP32 BLE Tutorial](https://randomnerdtutorials.com/esp32-bluetooth-low-energy-ble-arduino-ide/)

---

### 3. Environmental Air Quality Monitor
**Tags:** `chemical sensing` `environmental` `beginner`
**Difficulty:** ⭐⭐☆☆☆
**Hardware:** ESP32 + MQ-135 or MQ-2 gas sensor + DHT22 (~$10)
**What it does:** Measures CO₂, smoke, temperature, and humidity. Logs to SD card or sends to a web dashboard. Same sensor class as EPA air quality monitoring networks.
**Real-world analog:** Indoor air quality stations, wildfire smoke detection, agricultural greenhouse monitoring
**Resources:**
- [MQ sensor calibration guide](https://www.codrey.com/electronic-circuits/how-to-use-mq135-gas-sensor/)
- [ESP32 + DHT22](https://randomnerdtutorials.com/esp32-dht11-dht22-temperature-humidity-sensor-arduino-ide/)

---

### 4. Seismic Activity Logger (Geophone)
**Tags:** `vibration sensing` `geophysics` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** ESP32 + SW-420 vibration sensor or geophone module (~$8)
**What it does:** Detects ground vibration events, logs timestamps and amplitude. Geophones are the same sensor class used in oil exploration and earthquake networks — you're building a personal seismometer.
**Real-world analog:** Earthquake early warning, pipeline leak detection via ground vibration, infrastructure monitoring
**Resources:**
- [SW-420 with Arduino](https://how2electronics.com/vibration-sensor-module-sw-420-arduino/)
- [OpenEEW open-source seismic network](https://openeew.com/)

---

### 5. Passive Acoustic Wildlife Monitor
**Tags:** `acoustic` `environmental conservation` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + USB microphone or I2S mic module (~$20)
**What it does:** Records audio clips triggered by sound events. Runs a pre-trained BirdNET or YAMNet model to identify species from audio. Bioacoustic monitoring is how conservation researchers track bird populations, bat activity, and frog breeding cycles without cameras.
**Real-world analog:** SmartWilds dataset (acoustic + camera trap fusion), Cornell Lab BirdNET, bat echolocation detectors
**Resources:**
- [BirdNET-Analyzer](https://github.com/kahst/BirdNET-Analyzer)
- [YAMNet on Raspberry Pi](https://www.tensorflow.org/hub/tutorials/yamnet)
- [AudioMoth field recorder](https://www.openacousticdevices.info/audiomoth)

---

### 6. NDVI Vegetation Index Camera
**Tags:** `multispectral imaging` `agriculture` `environmental` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + modified NoIR camera + blue filter (~$35)
**What it does:** Captures near-infrared and visible images, computes NDVI (Normalized Difference Vegetation Index) — the ratio that satellite imagery uses to measure plant health. Healthy vegetation absorbs red and reflects NIR; stressed plants don't.
**Real-world analog:** Landsat/Sentinel satellite NDVI, precision agriculture crop stress mapping, wildfire burn severity assessment
**Resources:**
- [NDVI with Raspberry Pi](https://publiclab.org/notes/nedhorning/06-01-2014/raspberry-pi-camera-kit-for-ndvi-photography)
- [Public Lab NDVI guide](https://publiclab.org/wiki/ndvi)

---

### 7. LoRa Weather Station Network
**Tags:** `RF sensing` `environmental` `agriculture` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** 2x ESP32 + LoRa SX1276 modules + BME280 sensor (~$40 total)
**What it does:** Builds a multi-node sensor mesh where weather stations transmit temperature, humidity, and pressure over LoRa (915 MHz) to a central base station without WiFi. Same radio architecture as IoT agricultural monitoring networks.
**Real-world analog:** Smart agriculture soil + weather grids, wildfire weather monitoring, remote environmental sensing
**Resources:**
- [ESP32 LoRa with SX1276](https://randomnerdtutorials.com/esp32-lora-rfm95-transceiver-arduino-ide/)
- [The Things Network LoRaWAN](https://www.thethingsnetwork.org/)

---

## Tier 2 — Moderate ($80–$400)
> Raspberry Pi 4/5 + accessories, additional sensors, small compute boards

---

### 8. YOLOv8 Wildlife Camera Trap
**Tags:** `computer vision` `environmental conservation` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi 4/5 + camera module + PIR sensor (~$120)
**What it does:** PIR-triggered image capture with on-device YOLOv8 inference for species detection. Output structured CSV per detection. Same pipeline as SmartWilds and WildSense.
**Real-world analog:** WWF camera trap networks, MegaDetector deployments, conservation area monitoring
**Resources:**
- [Ultralytics YOLOv8](https://docs.ultralytics.com/)
- [Pi Camera Module v3](https://www.raspberrypi.com/products/camera-module-3/)
- [WildSense project (SmartWilds)](https://arxiv.org/abs/2509.18894)

---

### 9. GPS + IMU Animal Movement Tracker
**Tags:** `GPS` `accelerometer` `environmental` `agriculture` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + u-blox NEO-M8N GPS + MPU-6050 IMU (~$80)
**What it does:** Logs GPS coordinates and 6-axis motion data at configurable intervals. Builds a movement trajectory dataset. Lighter version of the GPS collar systems used in wildlife ecology (Hebblewhite & Haydon, 2010).
**Real-world analog:** Wildlife GPS collars, livestock tracking, vessel AIS tracking
**Resources:**
- [u-blox NEO-M8N with Raspberry Pi](https://gpsd.gitlab.io/gpsd/installation.html)
- [Movebank animal tracking platform](https://www.movebank.org/)

---

### 10. Thermal Anomaly Detector
**Tags:** `thermal imaging` `infrared` `infrastructure` `defense` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + MLX90640 or AMG8833 thermal array sensor (~$50–$120)
**What it does:** Produces low-resolution thermal images (32x24 or 8x8 grid) and detects hotspots or temperature anomalies. Same class of sensor used in fever screening, building energy audits, and electronics fault finding. Thermal imaging was critical for field triage during COVID (mass fever detection in crowds).
**Real-world analog:** Building heat loss mapping, electrical panel fault detection, fever screening, wildlife body heat detection at night
**Resources:**
- [MLX90640 Thermal Camera on Pi](https://learn.adafruit.com/adafruit-mlx90640-ir-thermal-camera/python-circuitpython)
- [AMG8833 Grid-Eye sensor](https://www.sparkfun.com/products/14607)

---

### 11. Synthetic Aperture Sonar (SAS) Simulator
**Tags:** `sonar` `signal processing` `defense` `advanced`
**Difficulty:** ⭐⭐⭐⭐☆
**Hardware:** Laptop/PC + audio interface + transducers (~$150)
**What it does:** Simulates underwater sonar imaging using audio transducers in a water tank. Implements delay-and-sum beamforming to reconstruct 2D images from acoustic echoes — the same principle as SAS used by naval mine-hunting vehicles.
**Real-world analog:** NOAA underwater terrain mapping, naval mine detection, fish finder SONAR
**Resources:**
- [PySDR signal processing guide](https://pysdr.org/)
- [Sonar beamforming tutorial](https://numpy.org/doc/stable/reference/routines.fft.html)

---

### 12. Software-Defined Radio (SDR) Spectrum Monitor
**Tags:** `RADAR/RF` `defense` `infrastructure` `advanced`
**Difficulty:** ⭐⭐⭐⭐☆
**Hardware:** RTL-SDR dongle + Raspberry Pi (~$30)
**What it does:** Captures radio frequency spectrum from 24 MHz to 1.7 GHz. Visualize weather radar signals, aircraft ADS-B transponders, ship AIS signals, weather balloon radiosondes, and RF interference patterns.
**Real-world analog:** NOAA weather radar receiver, air traffic ADS-B surveillance, ship tracking AIS, signals intelligence (SIGINT)
**Resources:**
- [RTL-SDR quickstart](https://www.rtl-sdr.com/rtl-sdr-quick-start-guide/)
- [GNU Radio project](https://www.gnuradio.org/)
- [OpenSky ADS-B network](https://opensky-network.org/)

---

### 13. Photogrammetry & 3D Point Cloud from Images
**Tags:** `LiDAR (photogrammetric)` `computer vision` `infrastructure` `agriculture` `advanced`
**Difficulty:** ⭐⭐⭐⭐☆
**Hardware:** Camera (phone or Pi) + laptop for processing
**What it does:** Uses Structure from Motion (SfM) to reconstruct 3D point clouds from overlapping 2D images. This is how aerial photogrammetry works — the same technique used to map terrain from drone imagery without LiDAR hardware.
**Real-world analog:** Archaeological site mapping, crop field 3D modeling, building damage assessment, MorphoCam distance estimation from camera traps
**Resources:**
- [COLMAP SfM tool](https://colmap.github.io/)
- [OpenDroneMap](https://www.opendronemap.org/)
- [Open3D point cloud processing](http://www.open3d.org/)

---

### 14. Hyperspectral Leaf Health Scanner
**Tags:** `multispectral` `agriculture` `environmental` `advanced`
**Difficulty:** ⭐⭐⭐⭐☆
**Hardware:** Raspberry Pi + AS7265x spectral sensor trident (~$60)
**What it does:** Measures reflectance across 18 channels from UV to NIR (410–940 nm) for individual leaves or soil samples. Builds a spectral signature library for plant disease, chlorophyll content, and nitrogen deficiency — the same data that Sentinel-2 satellite collects at 10m resolution, here at leaf scale.
**Real-world analog:** Sentinel-2 agriculture bands, precision spraying by spectral anomaly, NASA AVIRIS airborne hyperspectral imager
**Resources:**
- [AS7265x Sparkfun hookup guide](https://learn.sparkfun.com/tutorials/as7265x-multi-spectral-scanning-hookup-guide/all)
- [USGS spectral library](https://crustal.usgs.gov/speclab/QueryAll07a.php)

---

## Tier 3 — Advanced ($400+)
> Jetson Nano/Orin, actual LiDAR sensors, radar modules, dedicated SDR hardware, drone platforms

---

### 15. Real-Time LiDAR 3D Mapping (SLAM)
**Tags:** `LiDAR` `infrastructure` `defense` `advanced`
**Difficulty:** ⭐⭐⭐⭐⭐
**Hardware:** Jetson Nano + RPLiDAR A1 or RPLIDAR S2 (~$400–$600)
**What it does:** Runs real-time Simultaneous Localization and Mapping (SLAM) using rotating LiDAR. Generates a 2D or 3D occupancy map of an environment. LiDAR uses laser pulses (Time of Flight) to measure distance — the same principle as the sensors on autonomous vehicles and drone-based terrain mapping.
**Real-world analog:** Velodyne/Ouster autonomous vehicle LiDAR, USGS 3DEP national lidar dataset, drone-based forest canopy height mapping
**Resources:**
- [RPLiDAR with ROS](https://github.com/Slamtec/rplidar_ros)
- [Cartographer SLAM](https://google-cartographer.readthedocs.io/)
- [USGS 3DEP LiDAR data portal](https://www.usgs.gov/3d-elevation-program)

---

### 16. FMCW Radar Gesture & Presence Detection
**Tags:** `RADAR` `defense` `infrastructure` `advanced`
**Difficulty:** ⭐⭐⭐⭐⭐
**Hardware:** Jetson Nano + TI IWR1843BOOST or Acconeer XR112 (~$300–$500)
**What it does:** FMCW (Frequency Modulated Continuous Wave) radar detects presence, breathing rate, and hand gestures through walls and in darkness. The same principle as automotive blind-spot radar and military through-wall radar. Unlike cameras, radar works in complete darkness and through most solid materials.
**Real-world analog:** Automotive collision avoidance, search-and-rescue through-wall detection, airport ground movement radar, airborne weather radar (Doppler)
**Resources:**
- [TI mmWave SDK](https://www.ti.com/tool/MMWAVE-SDK)
- [Acconeer developer guide](https://developer.acconeer.com/)
- [OpenRadar community](https://github.com/presenseradar/openradar)

---

### 17. SAR (Synthetic Aperture Radar) Data Processing
**Tags:** `SAR` `RADAR` `environmental` `infrastructure` `defense` `advanced`
**Difficulty:** ⭐⭐⭐⭐⭐
**Hardware:** PC/cloud compute (no custom hardware — uses free satellite data)
**What it does:** Processes free Sentinel-1 SAR data from ESA to detect floods, surface deformation, ship positions, and vegetation change. SAR sees through clouds and works day/night — it was used to track flood extents during Hurricane Harvey when optical satellites were blocked. No hardware purchase needed — Sentinel-1 data is free.
**Real-world analog:** Copernicus Emergency Management flood mapping, NISAR surface deformation monitoring, ICEYE rapid response satellite, arctic sea ice tracking
**Resources:**
- [ESA Sentinel-1 open data](https://scihub.copernicus.eu/)
- [ASF SARVIEWS flood products](https://sarviews-hazards.alaska.edu/)
- [SNAP toolbox for SAR processing](https://step.esa.int/main/toolboxes/snap/)
- [FloodNet SAR flood detection paper](https://arxiv.org/abs/2012.02745)

---

### 18. Drone-Mounted Multispectral Survey Platform
**Tags:** `multispectral` `LiDAR` `agriculture` `environmental` `advanced`
**Difficulty:** ⭐⭐⭐⭐⭐
**Hardware:** DJI Mini 3 or Mavic + Sentera or MicaSense multispectral camera (~$800–$3000)
**What it does:** Acquires georeferenced multispectral imagery from the air. Processes into NDVI, NDRE, and false-color composites using OpenDroneMap. Field-level precision agriculture — the same tech used by commercial crop monitoring services.
**Real-world analog:** Planet Labs SkySat agriculture bands, John Deere See & Spray, NASA ABoVE Arctic vegetation mapping
**Resources:**
- [OpenDroneMap WebODM](https://www.opendronemap.org/webodm/)
- [MicaSense RedEdge documentation](https://support.micasense.com/)
- [QGIS for drone imagery analysis](https://qgis.org/)

---

### 19. Passive Radar (PCSS) Using FM Radio
**Tags:** `RADAR` `passive sensing` `defense` `advanced`
**Difficulty:** ⭐⭐⭐⭐⭐
**Hardware:** 2x RTL-SDR + Raspberry Pi 4 or laptop (~$60 hardware, high compute demand)
**What it does:** Passive Coherent Location (PCL) uses ambient FM radio or DAB signals as illuminators to detect aircraft and vehicles without transmitting anything. One antenna captures the direct FM signal; the other captures reflections from moving objects. Cross-correlation reveals range and Doppler shift of targets — actual stealth radar.
**Real-world analog:** NATO passive radar systems, AVEILLANT Gamekeeper 16U, silent border surveillance
**Resources:**
- [Passive radar with RTL-SDR](https://www.rtl-sdr.com/passive-radar-with-two-coherent-rtl-sdrs/)
- [PyPassiveRadar](https://github.com/passive-radar/PyPassiveRadar)

---

### 20. Ground Penetrating Radar (GPR) Scanner
**Tags:** `RADAR` `infrastructure` `defense` `agriculture` `expert`
**Difficulty:** ⭐⭐⭐⭐⭐
**Hardware:** ImpulseRadar Raptor or DIY UWB radar kit (~$500–$2000)
**What it does:** Pulses ultra-wideband radar into the ground and reconstructs subsurface features from reflections. Used for utility mapping, landmine detection, archaeological survey, and soil moisture profiling — seeing underground without digging.
**Real-world analog:** GSSI SIR-4000 utility locating, HALO Trust landmine detection radar, NASA RIMFAX Mars rover ground radar
**Resources:**
- [OpenGPR project](https://github.com/opengpr/opengpr)
- [ImpulseRadar developer docs](https://www.impulseradar.se/)
- [GPR data processing with Python](https://readgssi.readthedocs.io/)

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

## Learning Resources by Tier

### Tier 1 — Affordable (ESP32 / Raspberry Pi basics)

**Embedded Systems**
- [Random Nerd Tutorials](https://randomnerdtutorials.com/) — ESP32 + Raspberry Pi, huge project library
- [Adafruit Learning System](https://learn.adafruit.com/) — sensors, breakout boards, and hardware guides
- [Raspberry Pi documentation](https://www.raspberrypi.com/documentation/) — official Pi docs
- [Arduino Project Hub](https://projecthub.arduino.cc/) — community sensor projects

**Signal Processing Basics**
- [Think DSP — Digital Signal Processing in Python](https://greenteapress.com/wp/think-dsp/) — free book, great starting point
- [PySDR — A Guide to SDR and DSP using Python](https://pysdr.org/) — excellent, free, covers RTL-SDR basics

**Sensors & Datasheets**
- [SparkFun Hookup Guides](https://learn.sparkfun.com/) — every sensor has a walkthrough
- [Adafruit CircuitPython guides](https://learn.adafruit.com/category/circuitpython) — quick sensor bringup

---

### Tier 2 — Moderate (Raspberry Pi + additional hardware)

**Computer Vision**
- [Ultralytics YOLOv8 docs](https://docs.ultralytics.com/) — object detection, tracking, counting
- [OpenCV tutorials](https://docs.opencv.org/4.x/d9/df8/tutorial_root.html) — image processing fundamentals
- [PyImageSearch](https://pyimagesearch.com/) — applied CV tutorials with Pi and cameras

**Remote Sensing & Earth Observation**
- [NASA ARSET training programs](https://appliedsciences.nasa.gov/arset) — free online courses, certificates
- [ESA Earth Observation training](https://eo4society.esa.int/trainings/) — SAR, optical, climate applications
- [Google Earth Engine](https://earthengine.google.com/) — free cloud compute for satellite imagery

**RF & SDR**
- [RTL-SDR.com blog](https://www.rtl-sdr.com/) — extensive SDR project catalog and tutorials
- [GNU Radio tutorials](https://wiki.gnuradio.org/index.php/Tutorials) — open-source SDR framework
- [SondeHub radiosonde tracker](https://sondehub.org/) — live weather balloon data

**Acoustic & Audio**
- [librosa documentation](https://librosa.org/doc/latest/index.html) — Python audio analysis
- [PyRoomAcoustics](https://github.com/LCAV/pyroomacoustics) — beamforming and room acoustics
- [BirdNET-Analyzer](https://github.com/kahst/BirdNET-Analyzer) — bird species from audio

---

### Tier 3 — Advanced (Jetson / specialized hardware / satellite data)

**LiDAR & Point Clouds**
- [Open3D documentation](http://www.open3d.org/docs/release/) — point cloud processing in Python
- [PDAL point cloud processing](https://pdal.io/) — pipeline-based LPC processing
- [CloudCompare](https://www.cloudcompare.org/) — free, open-source 3D point cloud viewer
- [USGS 3DEP LiDAR portal](https://www.usgs.gov/3d-elevation-program) — free national LiDAR data

**RADAR & SAR**
- [ESA SNAP toolbox](https://step.esa.int/main/toolboxes/snap/) — SAR processing (Sentinel-1)
- [ASF SARVIEWS flood products](https://sarviews-hazards.alaska.edu/) — SAR flood detection
- [TI mmWave training](https://www.ti.com/tool/MMWAVE-TRAINING) — FMCW radar SDK and labs
- [PyPassiveRadar](https://github.com/passive-radar/PyPassiveRadar) — passive coherent location

**Medical / BCI**
- [MNE-Python](https://mne.tools/stable/index.html) — EEG/MEG signal processing
- [OpenBCI documentation](https://docs.openbci.com/) — open-source BCI hardware
- [BCI Competition datasets](https://www.bbci.de/competition/) — benchmark EEG datasets

**Citizen Science Platforms**
- [SatNOGS network](https://satnogs.org/) — global CubeSat ground station network
- [OpenEEW](https://openeew.com/) — distributed earthquake early warning
- [Blitzortung](https://www.blitzortung.org/) — global lightning detection network
- [CosmicWatch](https://www.cosmicwatch.lns.mit.edu/) — cosmic ray muon detectors
- [Breakthrough Listen open data](https://seti.berkeley.edu/opendata.html) — SETI datasets

---

## Topic Group: Ocean & Water Sensing

---

### 21. Water Quality Turbidity Sensor
**Tags:** `optical sensing` `environmental` `water` `beginner`
**Difficulty:** ⭐⭐☆☆☆
**Hardware:** ESP32 + TSW-10 turbidity sensor + TDS meter (~$15)
**What it does:** Measures water cloudiness (turbidity) and total dissolved solids in real time. Logs to SD or streams to a dashboard. Same parameter monitored by USGS stream gauges and municipal water treatment plants.
**Real-world analog:** EPA Clean Water Act monitoring, river sediment load after rain events, aquaculture pond health tracking
**Resources:**
- [Turbidity sensor with Arduino](https://how2electronics.com/interfacing-turbidity-sensor-with-arduino/)
- [USGS water quality monitoring](https://waterdata.usgs.gov/)

---

### 22. DIY Underwater ROV Sonar
**Tags:** `sonar` `water` `environmental` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + BlueRobotics Ping sonar altimeter + waterproof housing (~$150)
**What it does:** Builds a sonar depth profiler mountable on a small ROV. Generates 1D depth profiles or, with movement, basic bathymetric maps. Same principle as ship-mounted multibeam echosounders used for ocean floor mapping.
**Real-world analog:** NOAA nautical chart bathymetry, fish finder sonar, submarine cable route surveys
**Resources:**
- [BlueRobotics Ping sonar](https://bluerobotics.com/store/sensors-sonars-cameras/sonar/ping-sonar-r2-rp/)
- [OpenROV community](https://openrov.com/)

---

### 23. Salinity & pH Ocean Sensor Buoy
**Tags:** `chemical sensing` `water` `environmental` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + Atlas Scientific EZO-pH + EZO-EC probes (~$200)
**What it does:** Logs salinity, pH, and temperature in a weatherproof float enclosure. Ocean acidification is one of the clearest measurable signals of climate change — this builds a real monitoring instrument at low cost.
**Real-world analog:** Argo float network, NOAA Ocean Acidification Program, coral reef bleaching research
**Resources:**
- [Atlas Scientific EZO circuits](https://atlas-scientific.com/embedded-solutions/ezo-circuits/)
- [Argo float data portal](https://argo.ucsd.edu/)

---

### 24. Acoustic Underwater Mammal Detector
**Tags:** `acoustic` `sonar` `water` `environmental` `advanced`
**Difficulty:** ⭐⭐⭐⭐☆
**Hardware:** Raspberry Pi + hydrophone (~$80–$200) + waterproof housing
**What it does:** Records underwater audio and classifies cetacean vocalizations (whale calls, dolphin clicks) using a fine-tuned classifier. Passive acoustic monitoring is the primary way marine mammals are tracked without tagging.
**Real-world analog:** NOAA PIFSC passive acoustic monitoring, Scripps Whale Acoustics Lab, DCLDE whale detection challenge
**Resources:**
- [DolphinEar hydrophone](https://www.dolphinear.com/)
- [Watkins Marine Mammal Sound Database](https://cis.whoi.edu/science/B/whalesounds/)

---

## Topic Group: Space & Atmospheric Sensing

---

### 25. Weather Balloon Radiosonde Receiver
**Tags:** `RF` `SDR` `atmospheric` `beginner`
**Difficulty:** ⭐⭐☆☆☆
**Hardware:** RTL-SDR dongle + laptop (~$30)
**What it does:** Receives live telemetry from NOAA weather balloon radiosondes. Decodes temperature, humidity, pressure, and GPS altitude profiles in real time. No special hardware beyond the SDR dongle.
**Real-world analog:** NOAA upper-air sounding network, atmospheric reanalysis datasets
**Resources:**
- [Radiosonde Auto RX](https://github.com/projecthorus/radiosonde_auto_rx)
- [SondeHub global tracker](https://sondehub.org/)

---

### 26. All-Sky Aurora Monitor
**Tags:** `optical` `atmospheric` `space weather` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + fish-eye lens + IMX477 camera (~$120)
**What it does:** 180° fish-eye camera captures the full night sky. Software detects aurora events by monitoring green/red channel ratios and pixel intensity changes — a proxy for geomagnetic storm activity.
**Real-world analog:** AuroraMAX all-sky camera network, NOAA Dst geomagnetic index
**Resources:**
- [AllSky Camera software](https://github.com/thomasjacquin/allsky)

---

### 27. CubeSat Telemetry Ground Station
**Tags:** `RF` `SDR` `space` `advanced`
**Difficulty:** ⭐⭐⭐⭐☆
**Hardware:** RTL-SDR + Yagi antenna + rotator (~$100–$300)
**What it does:** Receives beacon telemetry from LEO CubeSats as they pass overhead. Decodes health data including power levels, temperature, and attitude. Contributing to SatNOGS network lets your station receive globally.
**Real-world analog:** SatNOGS global ground station network, AMSAT satellite tracking
**Resources:**
- [SatNOGS network](https://satnogs.org/)
- [GPredict satellite tracker](https://gpredict.oz9aec.net/)

---

### 28. Meteor Radar via FM Scatter
**Tags:** `RF` `RADAR` `atmospheric` `advanced`
**Difficulty:** ⭐⭐⭐⭐☆
**Hardware:** RTL-SDR dongle + directional antenna (~$30–$60)
**What it does:** Detects meteor entry by capturing forward scatter off ionized meteor trails using distant FM transmitters as illuminators — a passive bistatic radar. Each meteor appears as a brief "ping" in the RF spectrum.
**Real-world analog:** Canadian Meteor Orbit Radar (CMOR), GRAVES meteor radar (France)
**Resources:**
- [Society for Popular Astronomy meteor section](https://www.popastro.com/main_spa1/meteor/)

---

## Topic Group: Medical & Human Sensing

---

### 29. PPG Heart Rate + SpO₂ Monitor
**Tags:** `optical` `medical` `wearable` `beginner`
**Difficulty:** ⭐⭐☆☆☆
**Hardware:** ESP32 + MAX30102 pulse oximeter sensor (~$5)
**What it does:** Uses infrared light absorption to detect blood volume changes with each heartbeat. Extracts heart rate and SpO₂ — the same sensor principle as hospital pulse oximeters and smartwatch health sensors.
**Real-world analog:** Hospital bedside monitors, Apple Watch health sensor, COVID pulse oximetry screening
**Resources:**
- [MAX30102 with ESP32](https://how2electronics.com/max30102-pulse-oximeter-heart-rate-sensor-with-arduino/)

---

### 30. EMG Gesture Classifier
**Tags:** `bioelectric` `medical` `wearable` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + MyoWare 2.0 EMG sensor + ADS1115 ADC (~$60)
**What it does:** Captures electromyography signals from surface electrodes on muscle. Trains a classifier to distinguish gestures (fist, open, pinch) from signal patterns. Same sensing modality used in prosthetic limb control.
**Real-world analog:** Ottobock prosthetic arm control, CTRL-Labs neural interface, OpenBCI
**Resources:**
- [MyoWare 2.0 hookup guide](https://learn.sparkfun.com/tutorials/myoware-20-muscle-sensor-kit-hookup-guide)
- [OpenBCI community](https://openbci.com/)

---

### 31. EEG Brainwave Monitor
**Tags:** `bioelectric` `medical` `neuroscience` `advanced`
**Difficulty:** ⭐⭐⭐⭐☆
**Hardware:** Raspberry Pi + OpenBCI Cyton board (~$500) or Muse S headband (~$280)
**What it does:** Records EEG signals across multiple scalp electrodes. Classifies alpha, beta, theta, and delta brainwave bands. Enables motor imagery BCI and sleep stage classification.
**Real-world analog:** Emotiv EPOC clinical BCI, Neuralink, sleep staging polysomnography
**Resources:**
- [OpenBCI documentation](https://docs.openbci.com/)
- [MNE-Python EEG analysis](https://mne.tools/stable/index.html)

---

### 32. Gait Analysis IMU Array
**Tags:** `inertial` `medical` `wearable` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** 2–4x ESP32 + MPU-6050 IMU (~$30 total)
**What it does:** Straps multiple IMUs to legs and feet, fuses accelerometer + gyroscope data to reconstruct joint angles and step patterns. Detects gait asymmetry, cadence, and fall risk — used in rehabilitation and sports science.
**Real-world analog:** Vicon motion capture, Xsens MVN wearable mocap, Nike+ running form analysis
**Resources:**
- [Madgwick AHRS filter](https://github.com/xioTechnologies/Fusion)

---

## Topic Group: Urban & Smart City Sensing

---

### 33. Traffic Flow Counter
**Tags:** `vision` `infrastructure` `urban` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + camera module (~$80)
**What it does:** Runs a YOLO vehicle detector on a fixed camera, counts vehicles crossing a virtual line, classifies by type (car, truck, bicycle), and logs counts with timestamps. Same pipeline as municipal traffic monitoring cameras.
**Real-world analog:** London ULEZ camera network, NYC DOT traffic signal optimization
**Resources:**
- [YOLOv8 vehicle counting](https://docs.ultralytics.com/guides/object-counting/)

---

### 34. Noise Pollution Mapper
**Tags:** `acoustic` `urban` `environmental` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** ESP32 + INMP441 I2S microphone + GPS (~$20)
**What it does:** Logs dB SPL measurements with GPS coordinates to build a noise pollution map. Same methodology as WHO environmental noise guidelines monitoring.
**Real-world analog:** EU Environmental Noise Directive, SoundPrint crowdsourced noise database
**Resources:**
- [INMP441 with ESP32](https://randomnerdtutorials.com/esp32-i2s-microphone-inmp441/)

---

### 35. Structural Health Monitor (SHM)
**Tags:** `vibration` `acoustic` `infrastructure` `advanced`
**Difficulty:** ⭐⭐⭐⭐☆
**Hardware:** Raspberry Pi + ADXL355 accelerometer (~$100)
**What it does:** Monitors bridges or buildings for subtle vibration signatures indicating crack propagation or material fatigue. Runs FFT to extract natural frequency shifts — the primary indicator of structural damage.
**Real-world analog:** ASCE SHM on Golden Gate Bridge, NASA structural health monitoring for aircraft
**Resources:**
- [PyOMA operational modal analysis](https://github.com/dagghe/pyOMA)

---

## Topic Group: Agriculture & Food Systems

---

### 36. Soil Moisture & NPK Array
**Tags:** `chemical` `agriculture` `environmental` `beginner`
**Difficulty:** ⭐⭐☆☆☆
**Hardware:** ESP32 + capacitive soil moisture sensor + RS485 NPK sensor (~$25)
**What it does:** Reads volumetric water content and nitrogen/phosphorus/potassium levels from soil. Triggers irrigation relay when moisture drops below threshold.
**Real-world analog:** John Deere Operations Center soil sensors, USDA NRCS soil moisture network
**Resources:**
- [Capacitive soil moisture with ESP32](https://randomnerdtutorials.com/esp32-soil-moisture-sensor-arduino-ide/)

---

### 37. Greenhouse CO₂ + Light Control
**Tags:** `chemical` `optical` `agriculture` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** ESP32 + SCD41 CO₂ sensor + BH1750 light sensor + relay module (~$40)
**What it does:** Monitors CO₂ ppm and PAR inside a greenhouse. Automatically controls ventilation and supplemental lighting to optimize plant growth.
**Real-world analog:** Dutch greenhouse climate computers (Priva, Ridder), vertical farm atmosphere control
**Resources:**
- [SCD41 CO₂ sensor guide](https://learn.adafruit.com/adafruit-scd-40-and-scd-41/python-circuitpython)

---

### 38. Fruit Ripeness NIR Scanner
**Tags:** `optical` `multispectral` `agriculture` `food` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + AS7263 NIR sensor (~$40)
**What it does:** Measures near-infrared absorbance of fruit to estimate Brix (sugar content) and detect internal bruising non-destructively. Commercial fruit sorting lines use NIR for 100% inspection.
**Real-world analog:** COMPAC sorting systems in apple packing houses, Zeltex handheld Brix meters
**Resources:**
- [AS7263 NIR sensor](https://learn.sparkfun.com/tutorials/as7262-hookup-guide/all)

---

## Topic Group: Defense & Security Sensing

---

### 39. RF Fingerprinting Device Identifier
**Tags:** `RF` `SDR` `defense` `cybersecurity` `advanced`
**Difficulty:** ⭐⭐⭐⭐☆
**Hardware:** RTL-SDR or HackRF One + laptop (~$50–$350)
**What it does:** Captures unique RF emission characteristics of wireless devices and trains a classifier to identify them by hardware "fingerprint" — even when using the same protocol. Used in drone detection and unauthorized device tracking.
**Real-world analog:** DARPA RFMLS program, DHS RF fingerprinting for border security
**Resources:**
- [HackRF One](https://greatscottgadgets.com/hackrf/)
- [DeepSig RF fingerprinting dataset](https://www.deepsig.ai/datasets)

---

### 40. Acoustic Gunshot Localization
**Tags:** `acoustic` `defense` `urban` `advanced`
**Difficulty:** ⭐⭐⭐⭐☆
**Hardware:** 4x Raspberry Pi + microphones + network switch (~$300)
**What it does:** Deploys a microphone array and uses TDOA between nodes to triangulate the 3D origin of an impulsive sound event. Same principle as ShotSpotter, deployed in 100+ US cities.
**Real-world analog:** ShotSpotter gunshot detection, military acoustic shot detection, volcano eruption localization
**Resources:**
- [PyRoomAcoustics beamforming](https://github.com/LCAV/pyroomacoustics)

---

### 41. Magnetic Anomaly Detector
**Tags:** `magnetometry` `defense` `geophysics` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** ESP32 + HMC5883L magnetometer (~$5)
**What it does:** Logs Earth's magnetic field vector and detects anomalies from passing ferrous metal objects — vehicles, buried pipes, unexploded ordnance. Same sensing principle as naval aircraft submarine detection.
**Real-world analog:** Naval MAD boom for sub hunting, UXO detection, archaeological metal surveys
**Resources:**
- [HMC5883L with ESP32](https://randomnerdtutorials.com/esp32-hmc5883l-compass-arduino/)

---

## Topic Group: Energy & Power Systems

---

### 42. Smart Energy Monitor (CT Clamp)
**Tags:** `electrical` `infrastructure` `energy` `beginner`
**Difficulty:** ⭐⭐☆☆☆
**Hardware:** ESP32 + SCT-013 current transformer clamp + ZMPT101B voltage sensor (~$15)
**What it does:** Non-invasively measures AC current using a clamp-on transformer. Computes real power, apparent power, and power factor. Builds a home energy monitor equivalent to commercial smart meters.
**Real-world analog:** Sense home energy monitor, Emporia Vue, commercial smart meters
**Resources:**
- [OpenEnergyMonitor emonLib](https://openenergymonitor.org/emonlib/)

---

### 43. Solar I-V Curve Tracer
**Tags:** `optical` `electrical` `energy` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + Si1145 irradiance sensor + DAC/ADC (~$50)
**What it does:** Sweeps current-voltage curves of a solar cell to extract efficiency, fill factor, and maximum power point — the core measurements used to evaluate solar panel performance degradation.
**Real-world analog:** NREL solar resource assessment, SolarEdge module-level monitoring
**Resources:**
- [Si1145 solar sensor](https://learn.adafruit.com/adafruit-si1145-breakout-board-uv-ir-visible-sensor)

---

## Topic Group: Biological & Ecological Sensing

---

### 44. Bat Echolocation Detector
**Tags:** `acoustic` `ultrasonic` `environmental` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + Dodotronic Ultramic or Pettersson M500 USB mic (~$80–$200)
**What it does:** Records bat echolocation calls (20–120 kHz) and classifies species from call frequency, duration, and interpulse interval. Same approach as wind farm bat impact assessments.
**Real-world analog:** Bat Conservation International monitoring, AudioMoth bat surveys
**Resources:**
- [BatDetect2 classifier](https://github.com/macaodha/batdetect2)
- [AudioMoth ultrasonic guide](https://www.openacousticdevices.info/)

---

### 45. Insect Population Counter (UV Trap)
**Tags:** `optical` `vision` `agriculture` `environmental` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + camera + UV LED + light diffuser (~$70)
**What it does:** UV light attracts insects into a camera's field of view. A computer vision model detects, counts, and classifies insects by species — automating what entomologists currently do by manually counting trap catch overnight.
**Real-world analog:** Trécé PHEROCON smart trap, Trapview digital pest monitoring, FAO desert locust monitoring
**Resources:**
- [AMI-Insect trap paper](https://arxiv.org/abs/2202.09270)
- [iNaturalist insect ID API](https://api.inaturalist.org/v1/docs/)

---

### 46. Tree Phenology Camera (PhenoCam)
**Tags:** `optical` `environmental` `agriculture` `beginner`
**Difficulty:** ⭐⭐☆☆☆
**Hardware:** Raspberry Pi + camera + weatherproof housing (~$80)
**What it does:** Takes fixed time-lapse photographs of a forest canopy or crop field. Extracts the Green Chromatic Coordinate (GCC) index from RGB values to track seasonal greenness — bud burst, peak green, leaf-off dates — with no spectral sensor needed.
**Real-world analog:** PhenoCam Network (Harvard, NEON), USA National Phenology Network
**Resources:**
- [PhenoCam network guide](https://phenocam.nau.edu/webcam/tools/)

---

## Topic Group: Citizen Science & Open Data

---

### 47. Cosmic Ray Muon Detector
**Tags:** `particle sensing` `physics` `citizen science` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + Geiger-Muller tube (SBM-20) + HV circuit (~$40)
**What it does:** Detects ionizing radiation events (primarily cosmic ray muons at sea level) using a Geiger counter. Two coincidence detectors can track muon direction. Count rate correlates with altitude, pressure, and solar activity.
**Real-world analog:** CERN's DECO project, CosmicWatch muon detector, IceCube Neutrino Observatory
**Resources:**
- [CosmicWatch detector](https://www.cosmicwatch.lns.mit.edu/)

---

### 48. Earthquake Early Warning Node (OpenEEW)
**Tags:** `vibration` `geophysics` `citizen science` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** Raspberry Pi + ADXL355 accelerometer (~$30)
**What it does:** Joins the OpenEEW distributed seismic network. Detects P-waves and transmits alerts before the slower, more destructive S-waves arrive. A distributed IoT network can provide seconds of warning.
**Real-world analog:** Japan's JMA earthquake early warning, Mexico CIRES network, MyShake smartphone seismic network
**Resources:**
- [OpenEEW hardware guide](https://openeew.com/docs/hardware)
- [ShakeNet seismic network](https://shakenet.raspberryshake.org/)

---

### 49. Lightning Detection Network (Blitzortung)
**Tags:** `RF` `electromagnetic` `atmospheric` `citizen science` `intermediate`
**Difficulty:** ⭐⭐⭐☆☆
**Hardware:** ESP32 + AS3935 Franklin lightning sensor (~$15)
**What it does:** The AS3935 detects the RF discharge signature of nearby lightning. With multiple nodes sharing timestamps, TDOA locates each strike to within a few kilometers — the same technique Blitzortung uses with thousands of volunteer stations globally.
**Real-world analog:** Blitzortung.org global lightning map, NOAA National Lightning Detection Network, Vaisala GLD360
**Resources:**
- [AS3935 lightning sensor hookup](https://learn.sparkfun.com/tutorials/as3935-lightning-detector-hookup-guide/all)
- [Blitzortung participant guide](https://www.blitzortung.org/en/participate.php)

---

### 50. Passive Optical SETI Receiver
**Tags:** `optical` `astronomy` `citizen science` `advanced`
**Difficulty:** ⭐⭐⭐⭐☆
**Hardware:** Telescope + photomultiplier or fast photodetector + Raspberry Pi (~$200+)
**What it does:** Monitors individual star systems for nanosecond-scale optical pulses that would be inconsistent with natural stellar variability — a potential technosignature. Optical SETI is a serious research program at Harvard, UC Berkeley, and other institutions.
**Real-world analog:** Harvard OSETI telescope, SETI@home (defunct), Breakthrough Listen optical SETI program
**Resources:**
- [Harvard OSETI program](https://www.cfa.harvard.edu/projects/oseti/)
- [Breakthrough Listen open data](https://seti.berkeley.edu/opendata.html)

