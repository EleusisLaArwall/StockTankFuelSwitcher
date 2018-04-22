# StockTankFuelSwitcher mod for Kerbal Space Program
MM and PM scripts to patch stock tanks with fuel-switchers.
CC-BY-SA 4.0 International. 
By Eleusis La Arwall

### What is STFS?
STFS allows users to add fuel-switcher setups to the stock LFO tanks, configure them and also choose which fuel-switcher mod handles the task.

### What are the dependencies?
ModuleManager and PatchManager are hard-dependency and the mod will not work without them.
At least one Resource Switcher mod is also required. Currently InterstellarFuelSwitch (IFS), Firespitter (FS) and B9PartSwitch (B9PS) are supported.
Depending on the resource-setups you want to use, you may need CommunityResourcePack.

### How to use it?
When you install STFS, it will do nothing (*1) unless you configure it. To do so:
1. start KSP, load a savegame and at the KSC open the PatchManager window. Navigate to STFS000priority and expand it. Now choose a mod to handle the fuel-switching.
2. In the PatchManager window navigate to STFS100LFOtanks and expand it. Now choose the resources you want to have available on the stock tanks.
3. Apply the changes AND RESTART KSP!

### Will it interfere with other mods patching stock LFO tanks?
STFS always plays nicely (hopefully). By default the patching will take place at the end of MM load order (zzSTFS...). If fuel-switcher modules are detected, no further fuel-switcher modules will be applied. Even in aggressive mode, STFS will never add fuel-switchers to parts that already have a fuel-switcher module. 

### How does 'aggressive mode' work?
Aggressive mode adds a 'dummy' fuel-switcher in the :FIRST section of MM-patching and removes it right before STFS starts its usual patching. As long as your other mods also play nicely and don't apply switcher modules, STFS can do its job.

### How is STFS balanced?
That is the tricky part, which is mostly WIP currently:
 - Each setup uses the same volume for resource-storage. The Resource-Storage-Volume (RSV) is calculated from the amount of stored LiquidFuel and Oxidizer on each part.
 - Cost of each stock LFO tank is reduced to its dry-cost (KSP default cost include resource-cost)
 - Each setup uses the default tank-mass. The results are rather bad fuel2mass ratios on some setups. I'm open for suggestions!

### Notes:
(*1): The mod adds a useless key (stockLFO = true) to all stock tanks to make identification easier. The key will be removed at the end of MM-patching.
 - The cost of stock LFO tanks is set to their dry-cost instead of the default wet-cost.
 - The default RESOURCE nodes are removed.

### Warranty:
The mod is VERY WIP, so no warranty if it breaks craft- or save-files. Make backups in time!

### License:
CC-BY-SA 4.0 International 
https://creativecommons.org/licenses/by-sa/4.0/legalcode

### Changelog:
- #### 2018.04.22 - Initial release of 0.0.1 alpha
  - support for IFS, FS and B9PS
  - support for all stock LFO tanks

### Thanks to
- sarbian for ModuleManager
- linuxgurugamer for PatchManager
- FreeThinker for InterstellarFuelSwitch
- blowfish for B9PartSwitch
- Snjo & RoverDude for Firespitter
- RoverDude for Community Resource Pack
- NecroBones for FuelTanksPlus