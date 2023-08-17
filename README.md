# TPT2 - Imports
#### Quick Naviation
- [Region/Diff Unlocking/Pushing](#regiondiff-unlockingpushing)



# Region/Diff Unlocking/Pushing
#### AI script for tower testing goal navigation in any game stage
- [Import Here](#import-code)
- [Instructions Here](#instructions)
- Navigates the tower testing menu for all regions and difficulties
  - Sorted by enemy health at wave 1e9
- Automatically launches each region/diff that's under the current targeted goal
- Automatically restarts tower testing when tower reaches zero health (dead)
  - Leaves the current region/diff if too many deaths occur
- Automatically leaves tower testing once goal is reached and moves onto the next region/diff

#### For any stage of the game:
<ul>
  <li>100 Waves Goal(s)</li>
  <li><details><summary>MT8+</summary><ul><li>Era Unlocking</li></ul></details></li>
  <li><details><summary>MT12+</summary><ul><li>Infinity Unlocking</li></ul></details></li>
  <li><details><summary>MT12+</summary><ul><li>Infinity Pushing</li></ul></details></li>
</ul>

### Configuration Support
- [Behavior](#behavior)
  - Configurable stage to skip already completed goals
- [Resolution / UI](#resolution--ui)
  - Supported with `(x, y)` click points in the configuration file
  - Default: `1920 x 1080 with Dynamic UI`
    - This is typically fullscreen on a `1080p` monitor
    - There usually is also a replacement config file for a windowed `1920 x 1017` resolution as that is typically the size of the game window on my machine


## Instructions
1. Open the tower testing menu
2. Select the forest region
3. Press `x` to start the script

## Import Code
- [Package Import - Main + Config]
- [Individual Import(s)]

## Configuration
### Behavior
<ul>
  <li><code>stage</code> - Adjusts the target stage of the game (the current goal)</li>
  <li><code>0</code> - normal mode wave goals (wave 100)</li>
  <li><details><summary>MT8+</summary>
    <ul>
      <li><code>1</code> = endless mode era wave goal (wave 1e11)</li>
    </ul>
  </details></li>
  <li><details><summary>MT12+</summary>
    <ul>
      <li><code>2+</code> = infinity wave goal(s) = <code>10 ^ (stage - 2)</code></li>
      <ul>
        <li><code>2</code> = Infinity 1</li>
        <li><code>3</code> = Infinity 10</summary></li>
        <li><code>4</code> = Infinity 100</summary></li>
        <li><code>5</code> = Infinity 1000</summary></li>
      </ul>
    </ul>
  </details></li>
</ul>


### Resolution / UI
#### Different Resolutions
<ul>
  <li> Adjustable pixel positions in the config file to match your own screen </li>
  <li> <code>(x, y)</code> positions should match co-ordinates on the debug <code>F2</code> overlay </li>
  <ul>
    <li>Line 2: <code>launch</code> - the launch button</li>
    <li>Line 3: <code>normal</code> - the normal button (top row)</li>
    <li>Line 4: <code>endless</code> - the endless button (top row)</li>
    <li>Line 5: <code>diff.easy</code> - the easy difficulty button</li>
    <li>Line 6: <code>diff.next</code> - the distance between difficulty buttons - e.g. (0.0, med - easy)</li>
    <li>Line 7: <code>region.next</code> - the next region arrow (below picture)</li>
    <li>Line 8: <code>region.prev</code> - the previous region arrow (below picture)</li>
  </ul>
</ul>

### Notes
#### Behavior
- This script will navigate and launch each region/diff, waits for the current goal to exit, and then reopens the testing window to go to the next region/diff
- This script only accounts for the navigation (e.g. no software changes, no active module skill usage)
- Provided wait times for my system, you may need to shorten/lengthen for your setup
- Script will end if you manually exit testing

#### Additional Information
- A Tower Restart Script may be helpful, I have one located here: [FSS's Discord Forum Post](https://discord.com/channels/488444879836413975/1136751561473798176/1136752917366439957)
- Made with [d0sboot's editor](https://d0sboots.github.io/perfect-tower/)
