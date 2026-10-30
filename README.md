Bomberman World — Pick and Destroy

**Student:** Ilze Poskute

> Replace the prompts below and remove these instructions. Keep answers brief. Your implementation explanations and reflection belong in the presentation; you do not need to write them out here. Complete the final section only if seeking Pass with Distinction (VG).

## How to play
- **Controls:**
	Movement- WASD
	Bombs- Space
	Restart- R key
	Quit- Q or Esc
 
- **Objective and rules:**
	How to win: Destroy 5 enemies with bomb explosions 
	How to lose: Come in contact with one of the enemies or explosion blasts
	Pickups: One pickup protects the player from enemies and blasts for 3 seconds and increases the next explosion size. Default explosion size is 2 tiles, but each pickup adds one more tile in length. Max explosion size is 5 tiles. Once the bomb is placed, the collected pickup number goes back to 0 and the explosion size becomes 2 tiles again.
- **Configurations:** 
	Run the executable with the executable (default configurations)
	Exit with Q ir Esc
	L- automatically commands players death
	V- automatically increases maximum destroyed enemies
	M- automatically increases maximum pickups (the maximum explosion tile length) and adds 3 seconds to the protector timer
	

## Features and validation

| Feature | Check, observed result, and expected behaviour |
| --- | --- |
| 1. Player damage and death | Bypassed and made contact with enemies from different sides and bomb explosions in different positions as well as entering it after explosion. The player dies (change of gameplay state) only after the visible contact is made and the state remains "lost" until restart. This matches the behavior expectations. |
| 2. Round states and objective | I put HUD that informs about the game state, amount of enemies that were destroyed and tried reaching both winning condition (destroying 5 enemies with bombs) and losing condition (touching an enemy or blast). In both cases, the HUD showed immediate change in game state and increasement of destroyed enemy number. The gameplay stops and the camera remains in place despite the player being gone. This matches the expectations|
| 3. Safe restart | Tried restarting the game after winning, after losing, after placing bombs and waiting for the explosions.  The count of destroyed enemies, protection time, collected pickup count was displayed by HUD. Each time a new map was generated, old graphics were removed and the HUD displayed reset values. This matches the behavior expectations. Only improvement would be keeping the same map for each round|
| 4. Solid bombs with owner escape | I planted bombs and tried to move the player, step back on the bombs before and after detonation and see how the enemies interact with it. Enemies never entered a bomb, player could not enter after stepping off. Entities could enter the area again after the bomb detonated. This matches the behavior expectations |
| 5. Blast-range pickup | I passed by the pickups, collected them, tried to get back on the same area after collecting them, tried planting bombs before collecting pickups and then each time with an increasing number of pickups (1, 2, 3, 4), I also observed the pickup count in HUD. One pickup could be collected only once, they increased the blast range by 1 tile and it went up to 5 possible blast tiles. This behavior matches the expectations |
| 6. Multiple bombs per owner | Tried placing bombs multiple times (before and after any of them detonated) and viewed the HUD. They player could only place 3 bombs and was allowed to place more only when one of them detonated. HUD kept accurate count of the bombs. This matches the expected behavior |
| 7. Chain reactions | I tried placing multiple bombs near each other and observe HUD bomb count. Each bomb affected by a blast also detonated, they are no longer counted. This matches the expected behavior|
| 8. Shield or temporary invulnerability | I tried picking up a pickup and afterwards collide with entities and explosions (before 3 second timer ended and afterwards). I also viewed the HUD timer and the color of the player. Once the player picked up a pickup it turned white for 3 seconds and for that time was not affected by the threats. Afterwards, the player takes damage as usual until it picks up another pickup. This matches the expected behavior  |

Example: “I ended a round with live bombs and restarted three times to check that old-round state was cleared. No old explosions appeared, and bomb capacity reset each time.” Report your actual results, including any failures or remaining limitations; stating that something “works” does not describe a check.

**Known issues:** None known after testing

## Sources and assistance

This project builds on the shared Kotte foundations.
Feedback was received from Ulf Benjaminsson.
Research about coding was done using https://www.w3schools.com/
AI chatbot (Gemini) and Visual Studio's copilot was used to investigate errors and warnings