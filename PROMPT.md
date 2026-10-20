# Prompt — Grand Theft Family, Unreal first milestone

You are implementing the first playable slice of Grand Theft Family in Unreal Engine 5.4 or 5.5. This is a night mob district, Sopranos and Godfather tone, GTA loop. It is not a city. Do not build Liberty City. Do not port the browser fog ray march.

## Source

Read `UNREAL-HANDOFF.md` and `gtf-district.json` before placing anything. Numbers below match that JSON. If they conflict, the JSON wins.

District name: North Jersey night.
Block size: 32 m. Road width: 12 m. Span: 3 blocks each way from origin.
Player start: x 0, z 18. Name on the HUD: Big Sal.
Satriale’s: -32, -24. Line: “Gabagool is in the back. Do not touch the case.”
The Bing: 32, 26. Line: “Tony is not here. Leave the envelope and go.”
Genco: 64, -32. Do not build this interior in this milestone.
Envelopes: (16,-12), (-22,22), (44,-8), (60,-28). Payout 2500 each.
Gold door payout: 10000. Bing sit-down payout: 8000, plus 15 loyalty.
Heat: Fed chase starts above 32. Objective panic line above 70. Do not implement chase in this milestone. Store the heat value only.

## Scene

Big Sal already knows the night. He does not arrive. He resumes. The cabin is warmer than the glass, and the glass is colder than the street, and none of that is comfort. The avenue is a place he has used. Asphalt #1c1f26 sticks in the lamp light. A tar snake. A broken yellow line. The curb grits if he clips it. He does not flinch. Sodium poles tick like a clock he is late for. Each cone is warm, #ffb15a, and the warmth ends where the cone ends. Between poles the street is the color of a held breath. Windows are mostly dead. A few burn like someone is still up, waiting on a call that will not be kind. Far blocks thin above the second floor. Do not ray-march that. Let the district feel smaller than his errand.

Satriale’s awning is dull red, the name painted by a man who expected to repaint it and did not. The gold door is a narrow warm slab, the only invitation on the block. Inside, the avenue becomes a muffled wash and a cooler hum, the sound of a room that has heard worse. Wood is louder under his shoe than the sidewalk was. Plaster is a dirty brick red, uneven, touched too often. Garlic and vinegar sit with the cold-meat case. That smell is the job. A cloth-shade lamp pools on the boards. The practical over the table casts, tungsten, the light of a conversation that already happened. A man in a dark coat, no readable face, says it once, and not kindly: gabagool is in the back. Do not touch the case. The warning is the affection. He will not say it twice.

The Bing is the same size and meaner. Plum walls. A black bar. A pink top. Four stools for men who are not here. Bass leaks through the wall with no lyric, a song for nobody. Smoke and spilled beer are the room. The practical is pink and dimmer, a light that flatters no one. The line, once, is that Tony is not here. Leave the envelope and go. Loyalty in this room is a number that can fall. Taking the envelope should feel like being trusted and being used in the same gesture.

The sedan is long and black. Clearcoat takes the night sky and gives little back. Vinyl roof is matte, the part of the car that does not perform. Seven dark bars in the chrome nose. A spear. No badge. Tail lamps stand up and flare when the brake bites harder than the throttle pulls, because stopping is the heavier act. The idle is a low V8, thicker as it rolls, a short chirp on a hard stop. The horn is a dull bleat, a sound that expects to be obeyed. Steal a lane car and the note does not change. The body changes. He does not. That is the point of the theft.

Traffic hisses past and does not know him. Walkers are coats and heads and do not speak. A clip is a tire bark and a little lost ziti, irritation, not a crash scene. No score until the gold door. Then one low note, not triumph. The HUD is cream on dark glass, gold labels, a red Fed bar, a gold family bar, a small map with him and the two doors. The map should feel like a debt, not a minimap.

No crest. No likenesses. Night stays night. He is not free when the ziti goes up.

## Map

- World Partition on. One 512 m cell. Night.
- Sky: the included `night.hdr` (Poly Haven moonlit golf, CC0) as the skylight cubemap. Background may be the same HDR.
- Moon: one directional light, cool, two cascaded shadow maps. Near cascade tight on the car. Far cascade covers the avenue.
- Avenue: one road spline through the origin, 12 m wide, three blocks each way. Sidewalks 3 m. Asphalt dark, worn. Sodium spot lamps along x = 10, every 22 m. Every other lamp casts a shadow.
- No hero buildings except a door volume at Satriale’s and a door volume at the Bing. Mid-rises can be simple instanced boxes with lit window materials. Do not sculpt a skyline.
- Kenney trucks in `vehicle-player.glb` and `vehicle-fed.glb` are parked props only. CC0. Do not drive them.

## Done when

From a cold start you can drive the avenue, pick up one envelope, enter Satriale’s on foot, hear the line, exit to the same car, and see ziti change. The Bing door swaps. Save and load restore position and cash. Nothing else is required.
