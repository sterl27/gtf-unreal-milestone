# Unreal Setup — Short Milestone

UE 5.4 or 5.5. Ends when you can drive the avenue, pick up one envelope, enter Satriale’s on foot, hear the line, exit back to the same car, and save/load.

## 1. Project + night map + avenue
- New Third Person project, World Partition on, 512 m cell.
- Empty level `District_Night`.
- Directional Light (cool, 2 cascades) + Sky Light with night HDR + Exponential Height Fog.
- Road spline: 12 m wide, 3 blocks each way from origin (block = 32 m).
- Sodium spot lamps every 22 m, every other casts shadows.

## 2. Formal sedan
- Enable Chaos Vehicles plugin.
- Blueprint from ChaosWheeledVehicle: `BP_Sedan_BigSal`.
- WASD / Shift / Space.
- Chase camera ~11 m back, 5.5 m up.
- Headlights cast; tail lamps brighten on brake.

## 3. Satriale’s door-swap
- Interior level or room geometry: 12 × 18 m.
- On-foot pawn with eye-height camera (1.65 m), walk speed ~4.2 m/s.
- Trigger at (-32, -24). E within 8 m: hide car, possess on-foot pawn inside room.
- Line once near the figure: “Gabagool is in the back. Do not touch the case.”
- E again: return to the same car at the door.

## 4. Envelopes + job + HUD + save
- Four pickups at the JSON coordinates. Each: +2500 ziti, +3 loyalty.
- After 3: objective becomes gold door.
- Gold door delivery: +10000.
- HUD: ziti, loyalty, Fed heat, objective.
- K saves cash, heat, loyalty, flags, position.

## Out of scope
- Fog ray-march
- Fed chase
- Genco interior
- Full city
- Crests / likenesses

See `PROMPT.md` for the full scene brief and exact numbers.
