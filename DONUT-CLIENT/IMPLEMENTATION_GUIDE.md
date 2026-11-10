DONUT CLIENT - Minecraft 1.21.11 Fabric Mod Implementation Guide
================================================================

PROJECT STATUS
--------------
Project structure is complete. The following files exist:
- build.gradle (dependencies declared)
- settings.gradle (Maven repository)
- DonutClient.java (mod entry point)
- mods.toml (mod descriptor)
- .git (version control)

DEPENDENCY SETUP OPTIONS
-----------------------

Option A: Manual Jar Installation (Recommended for immediate start)
1. Download Fabric API jar from: https://maven.fabricmc.net/net/fabricmc/fabric-api/0.88.0+1.21/fabric-api-0.88.0+1.21.jar
2. Download Yarn mappings from: https://maven.fabricmc.net/net/fabricmc/yarn-stable/20240101.00/yarn-stable-20240101.00.jar
3. Place jars in: DONUT-CLIENT/lib/
4. Add to build.gradle:
   implementation files('lib/fabric-api-0.88.0+1.21.jar')
   implementation files('lib/yarn-stable-20240101.00.jar')

Option B: Gradle 8.6 with Java 17/21
1. Switch Gradle wrapper to version 8.6
2. Use Java JDK 17 or 21 (not JDK 25)
3. The 'minechao' configuration will be recognized
4. Build will work, but JDK 25 compatibility is lost

Option C: External IDE Setup
1. Open project in IntelliJ IDEA or Eclipse
2. Add external jars for Fabric API and Yarn mappings
3. Configure SDK to JDK 25
4. Use gradle for building, IDE for development

REQUIRED MODULES (10 TOTAL)
==========================
1. Base Finder - Basic module detection and tracking
2. Fullbright - Illuminate all blocks/areas
3. Fly - Creative mode flight capabilities
5. Progress Bar - Visual progress indicators
6. Name Hider - Hide player/entity names
7. Hotbar - Hotbar management tools
8. Antighost Scanner - Detection and countermeasures
9. Light Debug - Light level debugging
10. Sound Detector - Audio analysis and detection

BLOCKESP - HIGHEST PRIORITY
==========================
Must reproduce prediction functionality from reference video.

Required settings:
- Opacity slider
- Tracers toggle
- Coordinates/distance HUD toggle
- Predictions setting
- Rescan Predictions button
- Description field
- Favorite toggle

Prediction engine requirements:
- Minecraft 1.21.11 world-generation calculations
- World seed: 6608149111735331168 (authorized test seed)
- Emerald and coal support where applicable
- ESP boxes around predicted locations
- Adjustable opacity and colors
- Tracers and coordinates display
- Configurable block selection
- Adjustable render distance
- Distinguish verified vs unverified predictions

Donut Module Control GUI Specifications
=======================================
Visual appearance:
- Dark charcoal background
- Rounded window corners
- Thin panel borders
- Lime/yellow accent colors
- Matching typography and font sizes
- Matching spacing and proportions
- Matching module cards, toggle switches, sliders
- Smooth transitions
- Selected-item highlights

Top navigation:
- Modules
- HUD
- Appearance

Left sidebar:
- All modules
- Visual category
- Blatant category
- Streaming category
- Favorites

Main panel:
- "YOUR MODULE DESK" heading
- Workspace title
- Search modules field
- Two-column module grid
- Module descriptions
- Active/inactive indicators
- Enabled-only filter

Right panel:
- "MODULE SETTINGS" heading
- Selected module name
- Category
- Description
- Module-specific controls
- Configuration options
- Favorite toggle

GUI features:
- Selecting modules
- Searching modules
- Filtering categories
- Adding favorites
- Toggling modules
- Editing settings
- Saving configurations
- Smooth animations

IMPLEMENTATION PRIORITY
=======================
1. Set up dependency installation (Option A or B above)
2. Implement all 10 modules with real functionality
3. Recreate DONUT MODULE CONTROL GUI with exact specifications
4. Implement BlockESP with prediction engine
5. Test with authorized seed: 6608149111735331168
6. Verify predictions against actual generated chunks

BUILD COMMANDS
==============
gradle tasks     - List available tasks
gradle build     - Attempt build (may fail on dependencies)
gradle classes   - Compile Java sources only
gradle runClient - Launch Minecraft client (if dependencies resolved)

For immediate module implementation, use:
gradlew classes  (compiles DonutClient.java without Fabric API)
Then add Fabric API manually and continue development.