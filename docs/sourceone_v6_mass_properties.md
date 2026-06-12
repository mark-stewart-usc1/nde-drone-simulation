# Source One V6 7" Deadcat Mass Properties

## Assembly Information

Frame: TBS Source One V6 7" Deadcat

Configuration:
- Pixhawk 6C Mini
- PM06
- Power Distribution Board
- Battery
- Camera
- H-Flow Sensor
- SiK Radio
- VTX
- RP1

---

## Total Mass

Mass = 0.88674 kg

---

## Center of Mass

Units: mm

X = -13.959
Y = -0.577

Notes:
- COM is slightly aft of frame center.
- COM remains near the geometric center of the aircraft.

---

## Moments of Inertia

Units: kg·m²

Ixx = 0.00384
Iyy = 0.00445
Izz = 0.00736

Products of Inertia:

Ixy = -0.0000406
Ixz = 0.0001117
Iyz = 0.0000189

---

## Rotor Positions

Reference Frame:
- Origin located at frame center
- Origin located on the top surface of the lower frame plate
- Units: meters

Rotor 0 (Front Right)

X = 0.029868
Y = -0.145252
Z = 0.020000

Rotor 1 (Rear Left)

X = -0.151792
Y = 0.095197
Z = 0.020000

Rotor 2 (Front Left)

X = 0.031745
Y = 0.145101
Z = 0.020000

Rotor 3 (Rear Right)

X = -0.150606
Y = -0.097140
Z = 0.020000

---

## Sensor Locations

### Camera

Units: meters

X = 0.070000
Y = 0.000000
Z = 0.013000

### H-Flow Sensor

Units: meters

X = 0.066000
Y = 0.000000
Z = -0.009000

---

## Notes

These values were extracted from the Fusion 360 detailed assembly and are intended to be used for:

- PX4 airframe updates
- Gazebo SDF development
- Sensor placement
- Inertial property validation
