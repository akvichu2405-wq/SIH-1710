# Smart India Hackathon Workshop

## Date
18-09-2026

## Register Number
212225230309

## Name
VISHNU PRIYA A K

## Problem Title
**SIH 1710: Enhancing Navigation for Railway Station Facilities and Locations**

## Problem Description

Railway stations contain many interconnected areas, including platforms, ticketing zones, waiting halls, restrooms, shops, food areas, lifts, escalators and entry or exit points. In a crowded or unfamiliar station, passengers may spend considerable time trying to identify the correct route.

The proposed problem focuses on creating a digital indoor navigation solution that can guide passengers to their required destination while considering station layout, accessibility and changing facility information.

A useful system should work across smartphones and public touchscreen kiosks and should provide clear directions rather than only displaying a static station map.

### Major Requirements

- Digital representation of railway station facilities
- Indoor route generation
- Simple destination search
- Accessibility-aware route selection
- Voice instructions for passengers who need audio assistance
- Kiosk-based navigation
- Updated information about station facilities
- Mobile-friendly interface

## Problem Creator's Organization
**Ministry of Railway**

# Idea

## StationGuide – Intelligent Indoor Railway Navigation

StationGuide is a passenger assistance platform that converts a railway station into a searchable digital environment.

Instead of asking passengers to understand a complicated station map, the system allows them to enter a destination such as **Platform 5**, **Restroom**, **Food Court**, or **Exit Gate**. It then determines a suitable path from the passenger's starting point.

The system can provide different route preferences depending on the passenger's needs.

### Route Preferences

| Passenger Requirement | Route Preference |
|---|---|
| General passenger | Efficient walking route |
| Wheelchair user | Accessible route using lifts and ramps |
| Elderly passenger | Fewer stairs and simpler path |
| Visually impaired passenger | Audio instructions |
| Emergency situation | Route towards designated exit |

### Core Modules

1. Station Map Module
2. Destination Search Module
3. Indoor Routing Module
4. Accessibility Module
5. Voice Assistance Module
6. Kiosk Interface
7. Station Management Module
8. QR Route Transfer Module

# Proposed Solution / Architecture Diagram

```text
                       USER
                        |
              +---------+---------+
              |                   |
              v                   v
        MOBILE / WEB         STATION KIOSK
              |                   |
              +---------+---------+
                        |
                        v
                 APPLICATION API
                        |
        +---------------+---------------+
        |               |               |
        v               v               v
  LOCATION DATA     FACILITY DATA   USER OPTIONS
        |               |               |
        +---------------+---------------+
                        |
                        v
                 ROUTE ENGINE
                        |
              +---------+---------+
              |                   |
              v                   v
        ACCESSIBILITY       ROUTE OPTIMIZER
          FILTER             A* / Dijkstra
              |                   |
              +---------+---------+
                        |
                        v
               NAVIGATION OUTPUT
                        |
             +----------+----------+
             |                     |
             v                     v
        VISUAL ROUTE          VOICE GUIDANCE
```

## System Workflow

```text
Launch StationGuide
        |
        v
Choose Station
        |
        v
Set Starting Point
        |
        v
Search Destination
        |
        v
Choose Route Preference
        |
        v
Generate Suitable Route
        |
        v
Display Directions
        |
        v
Start Navigation
        |
        v
Destination Reached
```

## Route Generation Concept

The station is represented as a network of connected points.

```text
Location = Node
Walking Path = Edge
Facility = Destination Node
```

Example:

```text
Entrance
   |
   v
Main Concourse
   |
   +----------+
   |          |
   v          v
Ramp        Stairs
   |          |
   v          v
Footbridge   Platform Area
   |
   v
Platform 5
```

# Use Cases

### 1. Platform Navigation
Passengers can search for a platform and receive step-by-step directions from their current location.

### 2. Facility Navigation
Passengers can locate:

- Ticket counters
- Platforms
- Restrooms
- Food courts
- Waiting areas
- Lifts
- Escalators
- Information counters
- Entrances and exits

### 3. Wheelchair Navigation
The system provides routes that avoid stairs and prioritize accessible paths and lifts.

### 4. Voice Navigation
Visually impaired passengers can receive voice-based navigation instructions.

Example:

```text
"Continue straight for 20 metres."
"Turn left at the information counter."
"Take the lift to the next floor."
"Platform 3 is ahead."
```

### 5. Digital Kiosk
Passengers can use touch-screen kiosks installed throughout the railway station to search for facilities and destinations.

### 6. QR Code Navigation
The kiosk can generate a QR code for the selected route. Passengers can scan it and continue navigation on their mobile phone.

### 7. Emergency Navigation
Passengers can use the system to find emergency exits and other important safety locations.

# Technology Stack

### Frontend
- React.js
- Vite
- JavaScript
- HTML5
- CSS3
- Three.js

### Backend
- Node.js
- Express.js
- RESTful APIs

### Database
- MongoDB
- MongoDB Atlas

### Navigation Engine
- Python
- NetworkX
- A* Search
- Dijkstra's Algorithm

### Voice and Accessibility
- Web Speech API
- Text-to-Speech
- Speech Recognition

### Tools
- Visual Studio Code
- Git
- GitHub
- Postman

# Dependencies

## Frontend

```text
react
react-dom
react-router-dom
three
@react-three/fiber
@react-three/drei
axios
```

## Backend

```text
express
mongoose
cors
dotenv
```

## Navigation / Python

```text
python
networkx
numpy
```

## Development

```text
vite
nodemon
```

# Sample API Design

## Facility Search

```http
GET /api/stations/{stationId}/facilities?type=restroom
```

Example response:

```json
{
  "name": "Restroom",
  "floor": "Ground Floor",
  "accessible": true,
  "location": {
    "x": 145,
    "y": 82
  }
}
```

## Route Request

```http
POST /api/navigation
```

Example request:

```json
{
  "station": "Station01",
  "source": "Entrance_A",
  "destination": "Platform_5",
  "mode": "accessible"
}
```

Example response:

```json
{
  "distance": 320,
  "estimatedTime": "5 minutes",
  "route": [
    "Entrance_A",
    "Main_Concourse",
    "Lift_01",
    "Footbridge",
    "Platform_5"
  ]
}
```

# Expected Outcome

The proposed platform is expected to provide a clear and convenient way for passengers to navigate railway stations.

The system will:

- Make important facilities easier to locate
- Provide route instructions inside the station
- Support passengers with accessibility requirements
- Provide audio-based assistance
- Extend navigation to public kiosks
- Allow routes to be transferred from kiosks to phones
- Reduce dependence on manually reading complex station maps
- Support administrators in updating station information

# Future Scope

### 1. Indoor Positioning
BLE beacons, Wi-Fi positioning or other indoor-location technologies can be incorporated to automatically determine the passenger's approximate position.

### 2. Augmented Reality
Future versions can overlay navigation arrows onto the camera view of a smartphone.

### 3. Crowd-Aware Navigation
Live crowd information can be used to identify heavily congested areas and provide alternative routes.

### 4. Multilingual Assistance
The application can provide navigation instructions in multiple Indian languages.

### 5. AI Passenger Assistant
A conversational assistant can answer questions such as:

```text
"Where is Platform 2?"
"Find the nearest restroom."
"How do I reach the food court?"
"Show me a wheelchair-accessible route."
```

### 6. Emergency Management
The platform can be extended to provide evacuation guidance based on blocked areas and available emergency exits.

# Project Advantages

- User-friendly navigation
- Multi-platform support
- Accessibility-focused design
- Interactive station visualization
- Route customization
- Kiosk integration
- Voice assistance
- Expandable architecture
- Support for dynamic station information

# Project Status

**Prototype / Development Phase**

# Project Information

**Problem ID:** SIH 1710

**Problem:** Enhancing Navigation for Railway Station Facilities and Locations

**Organization:** Ministry of Railway

**Domain:** Smart Transportation / Indoor Navigation / Accessibility

**Project Name:** StationGuide
