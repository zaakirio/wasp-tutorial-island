# WaspScripts Tutorials

> All tutorials scraped from [waspscripts.com/tutorials](https://waspscripts.com/tutorials) (Pages 1-3)
> Scraped on: 2026-02-28

---

## Table of Contents

### Page 1 - Setup & Fundamentals
1. [Setup (Windows)](#1-setup-windows)
2. [Simba Setup (Debian Linux)](#2-simba-setup-debian-linux)
3. [RuneLite Setup (Debian)](#3-runelite-setup-debian)
4. [Simba Packages](#4-simba-packages)
5. [Introduction to Development](#5-introduction-to-development)
6. [Lape Syntax](#6-lape-syntax)
7. [Simba Interface](#7-simba-interface)
8. [Simba Tools](#8-simba-tools)
9. [Basic Script](#9-basic-script)
10. [Overriding](#10-overriding)

### Page 2 - Intermediate Concepts
11. [Caching](#11-caching)
12. [Compiler Directives](#12-compiler-directives)
13. [Arrays](#13-arrays)
14. [TPoints](#14-tpoints)
15. [Records](#15-records)
16. [Debugging](#16-debugging)
17. [Git Introduction](#17-git-introduction)
18. [WaspStats Virtual Levels](#18-waspstats-virtual-levels)
19. [WaspScripts GitHub Action](#19-waspscripts-github-action)
20. [RuneScape Walker - How it Works](#20-runescape-walker---how-it-works)

### Page 3 - Advanced Topics
21. [Script Stats](#21-script-stats)
22. [Programming Introduction](#22-programming-introduction)
23. [RuneLite OSRS Cache Dumping](#23-runelite-osrs-cache-dumping)
24. [TRSObjectV2 Finding & Usage](#24-trsobjectv2-finding--usage)
25. [Walker and Doors](#25-walker-and-doors)
26. [Insight into WebWalking with Doors](#26-insight-into-webwalking-with-doors)
27. [Minimap Dot Tiles](#27-minimap-dot-tiles)
28. [Simba Editor Keyboard Shortcuts](#28-simba-editor-keyboard-shortcuts)
29. [Bolt Launcher Setup (Debian)](#29-bolt-launcher-setup-debian)
30. [Sending Discord Messages with Simba](#30-sending-discord-messages-with-simba)

---

# Page 1 - Setup & Fundamentals

---

## 1. Setup (Windows)

**Author:** Baconadors | **Created:** 2022-03-22 | **Updated:** 2024-09-26
**Description:** Full installation setup of Simba, SRL, WaspLib and Scripts

### Introduction

The Legacy Java Client faces deprecation, making 64-bit installations the recommended approach. This comprehensive guide covers installing both Simba 64-bit and RuneLite 64-bit.

**Important compatibility notes:**
- The Legacy Java Client requires Simba 32-bit
- 32-bit Simba pairs with 32-bit OSRS clients
- 64-bit Simba pairs with 64-bit OSRS clients

### (Optional) Automated Installation

An automated .bat file exists that backs up existing installations, uninstalls current versions, and installs correct versions. Users experiencing installation errors can safely ignore them if previous installations don't exist. Those using automation should skip to Step 6.

### Step 1: Download simba-setup.exe

1. Navigate to waspscripts.com
2. Click "Setup" in navigation
3. Select yellow "setup.exe" button
4. Save file to memorable location (desktop recommended)

### Step 2: Download RuneLite 64-bit

1. Navigate to runelite.net
2. Click dropdown arrow on orange "Download" button
3. Select "Download for Windows (64-bit)"
4. Verify filename reads "RuneLiteSetup.exe"
5. Save to memorable location

### Step 3: Install Simba

1. Exit Jagex Launcher and all OSRS clients completely
2. Navigate to saved simba-setup.exe
3. Double-click to begin installation
4. Note: Installer includes both 32-bit and 64-bit versions
5. Click "Run Anyway" if security prompts appear
6. Click "Install" and await completion
7. Uncheck "Run Simba" before clicking "Finish"
8. Delete Simba32 shortcut from desktop

### Step 4: Install RuneLite 64-bit

1. Navigate to saved RuneLiteSetup.exe
2. Double-click to initiate installation
3. Click "Next" then "Install"
4. Uncheck "Open RuneLite" box before clicking "Finish"
5. **Note:** First-time installations may show runtime errors—manually open and close RuneLite if this occurs

### Step 5: Launch Simba 64-bit and Authenticate

1. Open Simba64 desktop shortcut
2. Click "Yes" for script association prompt
3. Press green play button twice (load launcher, then start)
4. Browser window opens for Discord authorization
5. Alternative: Email/password login available if configured on waspscripts.com profile
6. Complete authorization to access launcher

### Step 6: Install WaspScripts RuneLite Profile

1. Click "Install RuneLite Profile" button (bottom right of launcher)
2. Note profile name from dialog box
3. Click "OK" to proceed
4. Manually open RuneLite (executable or Jagex launcher)
5. Click wrench icon and select Profiles
6. Profile name uses first 8 characters of WaspScripts ID
7. Verify orange line appears left of profile name (indicating active status)
8. Double-click profile to activate if needed
9. Close sidebar and RuneLite
10. Close wasp-launcher

### Step 7: Configure RuneLite Layout

1. Open RuneLite manually
2. Log into game account
3. Click wrench icon for settings
4. Click monitor icon for display settings
5. Change "Game client layout:" to "Fixed - Classic layout"

### Step 8: Validate In-Game Settings

1. Download Settings Searcher script from launcher
2. Use target selector icon to highlight client window
3. Press green play button to execute
4. Script automatically verifies all settings

### Step 9: Save Account Credentials

1. Open wasp-launcher
2. Select Credentials script
3. Click "Install" in top right
4. Click "Open script" in bottom right
5. Use target selector on client window
6. Press green play button
7. Follow GUI instructions for account setup
8. Click "CLICK HERE TO FINISH" upon completion

### Step 10: Run First Script

This example uses Wasp Miner at Varrock East with similar steps for other scripts.

1. Open wasp-launcher
2. Select Wasp Miner
3. Click "Install" and "Open script"
4. Target client window with selector
5. Press green play button
6. Select "Copper" for rock type
7. Choose "Power mine (mine and drop)" for banking
8. Click "Start" to begin automation

### Step 11: Important Usage Notes

- **Always use the WaspScripts RuneLite profile** unless directed otherwise for NEON community scripts
- **Never open the RuneLite sidebar** during script execution (causes graphical issues)
- Free scripts available before purchasing premium versions
- Some scripts require code editing instead of GUI configuration

### Troubleshooting & Reinstallation

For installation difficulties or unexpected failures, use the automated .bat file that backs up, uninstalls, and reinstalls correct versions. Alternatively, manually uninstall using uninstall.exe located in "%LOCALAPPDATA%\Simba" and repeat installation steps.

---

## 2. Simba Setup (Debian Linux)

**Author:** Torwent | **Created:** 2022-03-22 | **Updated:** 2024-08-28
**Description:** Full installation setup of Simba in Linux

### Prerequisites

This guide assumes you are using Debian 10+. It might work on other distros, but you might need to do tweaks, in which case you are on your own.

> **Warning:** Before running any scripts, it is strongly recommended that you inspect the contents of the scripts to ensure they are safe and do not perform any actions that could harm your system.

### Simba Installation

#### 1. Download the Installation Script

```bash
wget https://raw.githubusercontent.com/Torwent/wasp-setup/master/linux/simba-setup.sh
```

#### 2. Make the Script Executable

```bash
chmod +x simba-setup.sh
```

#### 3. Run the Installation Script

```bash
./simba-setup.sh
```

The script will:
- Install required dependencies
- Set up the necessary directories for Simba
- Download the Simba binary and related files
- Set up the necessary permissions using `setcap` for remote input functionality
- Add a `simba` alias to your `.bashrc`
- Create a `.desktop` entry for easy access from the desktop environment

### Simba Uninstallation

#### 1. Download the Uninstallation Script

```bash
wget https://raw.githubusercontent.com/Torwent/wasp-setup/master/linux/simba-uninstall.sh
```

#### 2. Make the Script Executable

```bash
chmod +x simba-uninstall.sh
```

#### 3. Run the Uninstallation Script

```bash
./simba-uninstall.sh
```

> **Note:** After running the installation or uninstallation scripts, you may need to restart your session or log out and back in for all changes to take effect.

---

## 3. RuneLite Setup (Debian)

**Author:** TazE
**Description:** Full installation setup of RuneLite in Debian Linux

### RuneLite Installation

#### Step 1: Download the Profile Properties File

```bash
wget https://raw.githubusercontent.com/Torwent/wasp-setup/master/linux/myprofile.properties
```

#### Step 2: Download the Installation Script

```bash
wget https://raw.githubusercontent.com/Torwent/wasp-setup/master/linux/runelite-setup.sh
```

#### Step 3: Make the Script Executable

```bash
chmod +x runelite-setup.sh
```

#### Step 4: Run the Installation Script

```bash
./runelite-setup.sh
```

The script performs these actions:
- Installs required dependencies
- Downloads and places the latest `RuneLite.jar` in `/usr/local/bin`
- Sets appropriate file permissions
- Adds a `runelite` command alias to `/etc/bash.bashrc`
- Downloads and configures the RuneLite icon
- Creates a desktop application entry
- Copies the properties file to the RuneLite profiles directory

### RuneLite Uninstallation

#### Step 1: Download the Uninstallation Script

```bash
wget https://raw.githubusercontent.com/Torwent/wasp-setup/master/linux/runelite-uninstall.sh
```

#### Step 2: Make the Script Executable

```bash
chmod +x runelite-uninstall.sh
```

#### Step 3: Run the Uninstallation Script

```bash
./runelite-uninstall.sh
```

The script removes:
- The `RuneLite.jar` file from `/usr/local/bin`
- The command alias from `/etc/bash.bashrc`
- The icon from `/usr/local/share`
- The desktop entry from `/usr/share/applications`

> **Note:** Before running any scripts, inspect the contents to ensure they are safe. You may need to restart your session for changes to take effect.

---

## 4. Simba Packages

**Author:** Torwent | **Created:** 2022-04-06

### Introduction

Three methods exist for installing packages: GUI installation, manual installation, and Git installation. The GUI approach offers automatic update notifications. Git installation suits developers well, while manual installation requires more effort.

### GUI Installation

Recommended for regular users:

1. Open Simba application
2. Click the package icon
3. In the opened window, click the plus icon (top left corner)
4. Paste the package repository link (example: `https://github.com/Torwent/wasp-free`)
5. Click **Ok** then **Install**

The package icon displays a green plus indicator when updates are available. To update, access the package manager, open the desired package, and click install again.

### Git Installation

Requires Git to be pre-installed:

1. Locate the repository and open its `.simbapackage` file
2. Note the `directory=` parameter (installation location)
3. Navigate to the Simba directory and open the command line
4. Execute: `git clone https://github.com/Torwent/wasp-free.git`

To update:

```
cd Simba/Scripts/wasp-free
git pull
```

### Manual Installation

1. Download the desired package (or use a release version for stability)
2. Unzip the downloaded file
3. Verify files are directly in the root folder (not nested)
4. Consult the `.simbapackage` file for the intended directory name and destination
5. Rename folder and move to destination (typically `Simba/Scripts`)

Updating requires repeating the entire process.

---

## 5. Introduction to Development

**Author:** Torwent | **Created:** 2022-03-22

### Overview

This tutorial provides foundational resources for aspiring developers interested in coding for Simba.

> "I've never actually studied programming and I try to explain things the way I understand them!"

### Essential Resources

#### Community Channels
- **Wasp Scripts Discord:** https://discord.gg/YMYUahmww9
- **SRL Discord:** https://discord.gg/W4bh4jdzzp

#### Official Documentation
- **FreePascal Documentation:** https://www.freepascal.org/docs-html/current/ref/ref.html
- **SRL Documentation:** https://ollydev.github.io/SRL-Development
- **WaspLib Documentation:** https://torwent.github.io/WaspLib

---

## 6. Lape Syntax

**Author:** Torwent | **Created:** 2022-03-22

### What is Lape?

Lape is a scripting engine with a Pascal derived syntax for Free Pascal and Delphi. The syntax maintains backward compatibility with Pascal Script.

### Variables and Constants

**Constants** store unchangeable values:
```pascal
const
  CONSTANT_STRING: String = 'Hello world';
  CONSTANT_INT: Int32 = 5;
```

**Variables** store changeable values:
```pascal
var
  VariableString: String := 'Hello world';
  VariableInt: Int32 := 5;
```

Variables can be declared without initial values:
```pascal
var
  VariableString: String;
  VariableInt: Int32;

begin
  VariableString := 'Hello world';
  VariableInt := 5;
end.
```

Multiple variables of the same type:
```pascal
var
  Str1, Str2, Str3: String;
  VariableInt1, VariableInt2: Int32;
```

### Code Style Conventions

- FPC is case-insensitive but conventions improve readability
- **Constants**: UPPERCASE_WITH_UNDERSCORES
- **Variables**: CamelCase
- **Reserved words**: lowercase (const, var, for, while, etc.)

### Comments

```pascal
(*
  This is a multilined
  comment block.
*)

//This is a single line comment.

var
  VariableInt: Int32; //Inline comments work too.
```

### Code Blocks

```pascal
begin
  //Your code.
end
```

### Conditional Statements

#### If Statements

```pascal
var
  VariableString: String;
  BooleanVariable: Boolean;

begin
  BooleanVariable := True;

  if BooleanVariable then
  begin
    VariableString := 'Hello world';
    Writeln(VariableString);
  end;

  BooleanVariable := False;

  if not BooleanVariable then
    Writeln('The statement was false');
end.
```

#### If-Else Statements

```pascal
var
  VariableString: String;
  IntVariable: Int32;

begin
  IntVariable := 1;

  if IntVariable = 0 then
  begin
    VariableString := 'Hello world';
    Writeln(VariableString);
  end
  else if IntVariable = 1 then
    Writeln('The statement was false')
  else
    Writeln('IntVariable is neither 0 nor 1');
end.
```

Single-line if-else:
```pascal
if True then Writeln('True')
else Writeln('False');
```

### Punctuation Rules

- **Semicolons** (`;`) end code lines/blocks
- **Periods** (`.`) end the entire script

**Critical:** A semicolon before `else` breaks the code:
```pascal
if True then
begin
  Writeln('Hello');
end; //Semicolon breaks the else connection
else if False then
  Writeln('Never runs');
```

### Loops

#### While Loops

```pascal
while True do
begin
  //Loops forever
end;
```

With variables:
```pascal
BooleanVariable := True;

while BooleanVariable do
begin
  BooleanVariable := False;
end;
```

#### Repeat Until Loops

```pascal
repeat
  Writeln('Runs at least once');
until 1 > 0;
```

#### For Loops

Incrementing:
```pascal
var
  i: Int32;

begin
  for i := 0 to 50 do
  begin
    Writeln('i is currently at: ', i);
  end;
end.
```

Decrementing:
```pascal
var
  i: Int32;

begin
  for i := 50 downto 0 do
    Writeln('i is currently at: ', i);
end.
```

#### Loop Control

**Break** exits prematurely:
```pascal
var
  i: Int32;

begin
  for i := 0 to 50 do
  begin
    if i >= 30 then
      Break;
    Writeln('i is currently at: ', i);
  end;
end.
```

**Continue** skips to next iteration:
```pascal
var i: Int32;

begin
  for i := 0 to 50 do
  begin
    Writeln('i is currently at: ', i);
    if i >= 30 then Continue;
    Writeln('This prints until i >= 30');
  end;
end.
```

### Arrays

Basic array declaration:
```pascal
var StringArray: TStringArray := ['String1', 'String2', 'String3'];
```

Custom array types:
```pascal
type
  MyCustomArray: array of String;

var StringArray: MyCustomArray:= ['String1', 'String2', 'String3'];
```

#### Accessing Array Elements

```pascal
var
  IntArray: TIntegerArray:= [1, 5, 3];
  Result: Int32;

begin
  Result := IntArray[0] + IntArray[2]; //(1 + 3) = 4
  Writeln(Result);
end.
```

#### Iterating Arrays

Using `Low()` and `High()`:
```pascal
var
  i: Int32;
  IntArray: TIntegerArray := [5, 2, 3, 7];

begin
  for i := Low(IntArray) to High(IntArray) do
    Writeln(IntArray[i]);
end.
```

Using `in` keyword:
```pascal
var
  i: Int32;
  IntArray: TIntegerArray := [5, 2, 3, 7];

begin
  for i in IntArray do
    Writeln(i);
end.
```

#### Adding to Arrays

```pascal
var
  i: Int32;
  IntArray: TIntegerArray := [5, 2, 3, 7];

begin
  for i := 0 to 2 do
    IntArray += i;

  Writeln(IntArray); //[5, 2, 3, 7, 0, 1, 2]
end.
```

**Important:** Using `in` with modification doesn't work (modifies a copy, not the array).

### Functions and Procedures

**Procedures** execute code without returning values. **Functions** execute code and return results.

```pascal
procedure MyProcedure;
begin
  //Your code.
end;

function MyFunction: Boolean;
begin
  Result := True;
end;

begin
  if MyFunction then
    MyProcedure;
end.
```

#### Parameters

```pascal
var
  JoinedStr: String;

function StringJoiner(Str1, Str2: String): String;
begin
  Result := Str1 + Str2;
end;

procedure MyProcedure(Str: String);
begin
  JoinedStr := StringJoiner('Hello', Str);
end;

begin
  MyProcedure('World');
  Writeln(JoinedStr); //HelloWorld
end.
```

### Records

Records bundle multiple variables together (similar to objects):

```pascal
type
  TRSScript = record
    Name: String;
    Version: Double;
  end;

procedure TRSScript.Setup;
begin
  Self.Name := 'My script';
  Self.Version := 3.2;
end;

var
  Script: TRSScript;

begin
  Script.Setup;
  Writeln(Script.Name); //My script
end.
```

#### Multiple Record Instances

```pascal
type
  TRSScript = record
    Name: String;
    Version: Double;
  end;

  TRSScriptArray = array of TRSScript;

procedure TRSScript.Setup(ScriptName: String; ScriptVersion: Double);
begin
  Self.Name := ScriptName;
  Self.Version := ScriptVersion;
end;

var
  Script: TRSScript;
  Script1, Script2, Script3: TRSScript;
  ScriptArray: TRSScriptArray;

begin
  Script1.Setup('First script', 3.2);
  Script2.Setup('Second script', 1.2);
  Script3.Setup('Third script', 0.1);

  ScriptArray := [Script1, Script2, Script3];

  for Script in ScriptArray do
    Writeln('This is the ', Script.Name, ' with version number ', Script.Version);
end.
```

---

## 7. Simba Interface

**Author:** Torwent | **Created:** 2022-03-22

### Left Panel: Function List

The Function List displays all accessible variables and functions for the current script. Functions organize automatically by source:
- **Script directory**: Variables and functions from your actual script
- **Plugins**: Functions from imported plugins
- **Includes**: Functions from imported includes like SRL and WaspLib
- **Simba directory**: Built-in Simba variables and functions

Hovering over functions reveals tooltips with parameter information. Double-clicking a library function opens its file.

### Center Panel: Editor

The text editor where you write scripts. Supports multiple tabs and displays current mouse X and Y coordinates relative to the focused client window.

### Right Panel: File Browser

File explorer for opening scripts and files from includes. Right-click to refresh if newly added files don't appear.

### Bottom Panel: Output

Console for printing script progress and debugging information. Displays warnings and errors during compilation and execution.

### Toolbar Tools

Key buttons: New/Open/Save, Compile, Run/Pause/Stop, Target selector, Color picker, Clean output, Package manager.

### Menu System

- **Edit** menu: Useful hotkeys
- **View** menu: Hide panels and reset layouts
- **Tools** menu: Additional functionality

---

## 8. Simba Tools

**Author:** Torwent | **Created:** 2022-03-22

### Overview

Two primary categories: Simba built-in tools and Script tools. Script tools are located in `Simba/Includes/WaspLib/tools`.

### Bitmap Conversion

Converts image files to string representations for script inclusion:

```simba
var
  YellowClickBitmapString: String := 'meJxjZGBgBKP/DP+xIkaYAiCCiGFVjCwLZ2MqxpTCqhiXCWjieCxCU4xHGVbF+AOEDAOJcSQeHxEZSsSHPEmxSWQKAQAWmB8k';
```

Convert strings to bitmaps using `BitmapFromString`:

```simba
var
  Bitmap: Int64;

begin
  Bitmap := BitmapFromString(14, 14, YellowClickBitmapString);
end.
```

**Memory management is essential.** Always free bitmaps:

```simba
var
  Bitmap: Int64;

begin
  Bitmap := LoadBitmap('path to your bitmap');
  //Use your bitmap...
  FreeBitmap(Bitmap);
end.
```

### DTM Editor

**DTM** (Deformable Template Model) — a list of coordinates of points in relation to one main point and their respective colors. DTMs offer accuracy and speed.

**Creating a DTM:**
1. Focus the OSRS Client and launch DTM Editor
2. Zoom using CTRL + Scroll
3. Select a starting point (typically the outline)
4. Pick random points within the target item
5. Debug using the Find DTM button
6. Test against similar items for specificity

Example output:
```simba
DTM := DTMFromString('mKgEAAHic42NgYJjGBMGTgbgfiOcC8RQg7oWy5wHxTCCeAcQTgXg6EM8B4lmMDAx9QNzDCGHPBeLlQLwYiJcC8XwgngLE/VA+SHwhELsEeTPsXpsEtJkRL64tcWTwjgpicAv1ZTC0MWUgF+C3BTdGBQC+VRdu');
```

**Important:** Bitmaps and DTMs should only be used for static things — items, buttons, etc.

### ACA (Auto Color Aid)

ACA builds **CTS** (ColorToleranceSpeed) colors:

```simba
type
  TCTS0Color = record
    Color: Int32;
    Tolerance: Int32;
  end;

  TCTS1Color = type TCTS0Color;

  TCTS2Color = record
    Color: Int32;
    Tolerance: Int32;
    HueMod: Extended;
    SatMod: Extended;
  end;
```

**CTS0** is fastest but least accurate; **CTS2** is slowest but most accurate.

**Building a CTS:**
1. Open ACA (zoom with CTRL + Scroll)
2. Click colors unique to target
3. Use Debug button to test detection
4. Rotate screen and update the image
5. Press CTRL+C to copy the generated CTS

**Practical example:**

```simba
{$I SRL/osr.simba}
var
  GEClerk: TCTS2Color;
  TPA: TPointArray;

begin
  GEClerk := CTS2(5717309, 13, 0.67, 0.65);

  SRL.FindColors(TPA, GEClerk, MainScreen.Bounds);

  Mouse.Move(TPA);
  if MainScreen.IsUpText('Clerk') then
    Mouse.Click(MOUSE_LEFT);
end.
```

---

## 9. Basic Script

**Author:** Torwent | **Created:** 2022-03-22
**Description:** Create a basic Simba script from scratch

### Step 1: Include SRL

```pascal
{$I SRL-T/osr.simba}
```

### Step 2: Basic Structure

```pascal
{$I SRL-T/osr.simba}

begin

end.
```

### Step 3: Login Setup

```pascal
{$I SRL-T/osr.simba}

procedure Init;
begin
  Login.AddPlayer('username', 'password', 'bankpin');
  if not RSClient.IsLoggedIn then
    Login.LoginPlayer;
end;

begin
  Init;
end.
```

### Step 4: Setup RSWalker

```pascal
{$I SRL-T/osr.simba}

var
  RSW: TRSWalker;

procedure Init;
begin
  RSW.Setup('world');
  Login.AddPlayer('username', 'password', 'bankpin');
  if not RSClient.IsLoggedIn then
    Login.LoginPlayer;
end;

begin
  Init;
end.
```

### Step 5: Get Tile Coordinates

```pascal
begin
  Init;
  Writeln(RSW.GetMyPos);
  RSW.DebugPosition;
end.
```

### Step 6-7: Store Tile and Check Position

```pascal
var
  RSW: TRSWalker;
  GETile: TPoint := [4477, 2491];

function AtTile(Tile: TPoint; Distance: Int32 = 15): Boolean;
begin
  Result := RSW.GetMyPos.DistanceTo(Tile) <= Distance;
end;
```

### Complete Final Script

```pascal
{$I SRL/osr.simba}

var
  Item: TRSItem := 'Tuna';
  RSW: TRSWalker;
  GETile: TPoint := [4477, 2491];

procedure Init;
begin
  RSW.Setup('world');
  Login.AddPlayer('username', 'password', 'bankpin');
  if not RSClient.IsLoggedIn then
    Login.LoginPlayer;
end;

function AtTile(Tile: TPoint; Distance: Int32 = 15): Boolean;
begin
  Result := RSW.GetMyPos.DistanceTo(Tile) <= Distance;
end;

begin
  Init;

  while True do
  begin
    if not AtTile(GETile) then
      RSW.WebWalk(GETile, 10, 0.2);

    if Bank.IsOpen then
    begin
      if Inventory.FindItem(Item) and Inventory.IsFull then
        Bank.Close
      else
      begin
        Bank.WithdrawItem([Item, BANK_WITHDRAW_ALL, False], True);
        Wait(700, 1000);
      end;
    end
    else
    begin
      if Inventory.FindItem(Item) then
      begin
        Inventory.ClickItem(Item);
        Wait(700, 1000);
      end
      else
        Bank.Open(ERSBankLocation.GRAND_EXCHANGE);
    end;
  end;
end.
```

---

## 10. Overriding

**Author:** Torwent | **Created:** 2022-03-22

### Overview

Function overriding and overloading lets you modify library functions within individual scripts without affecting other code or losing changes during updates.

### The Problem

Directly editing library files impacts all scripts using that function, and updating libraries risks losing custom work.

### Function Overloading Example

The original `FindItem` function:
```simba
TRSInventory.FindItem(Item: TRSItem; out Slots: TIntegerArray): Boolean
```

Custom overload (simpler interface):
```simba
function TRSInventory.FindItem(Item: TRSItem): Boolean; overload;
var
  Slots: TIntegerArray;
begin
  Result := Self.FindItems([Item], Slots);
end;
```

This calls the original function while providing a cleaner interface.

---

# Page 2 - Intermediate Concepts

---

## 11. Caching

**Author:** Torwent | **Created:** 2022-03-22 | **Level:** Beginner

### Overview

Caching is storing a result or a variable in another variable to use later.

### Example: Measuring Execution Time

```pascal
var
  RSW: TRSWalker;
  TickCountCache: UInt64;

begin
  RSW.Setup('world');

  while True do
  begin
    TickCountCache := GetTickCount;
    WriteLn('Position: ', RSW.GetMyPos);
    WriteLn('This took ', GetTickCount - TickCountCache, 'ms to compute');
  end;
end;
```

### Example: Caching Static Position

```pascal
var
  RSW: TRSWalker;
  Position: TPoint;
  TickCountCache: UInt64;

begin
  RSW.Setup('world');
  Position := RSW.GetMyPos;

  while True do
  begin
    TickCountCache := GetTickCount;
    WriteLn('Position: ', Position);
    WriteLn('This took ', GetTickCount - TickCountCache, 'ms to compute');
  end;
end;
```

### Example: Optimized Change Detection

```pascal
var
  RSW: TRSWalker;
  PrevPos, NewPos: TPoint;

begin
  RSW.Setup('world');
  PrevPos := RSW.GetMyPos;

  while True do
  begin
    NewPos := RSW.GetMyPos;
    if PrevPos = NewPos then
      WriteLn('Position didn''t change')
    else
    begin
      PrevPos := NewPos;
      WriteLn('New position: ', NewPos);
    end;
  end;
end;
```

---

## 12. Compiler Directives

**Author:** Torwent | **Created:** 2022-03-22 | **Level:** Beginner

### What Are Compiler Directives?

Red lines at the beginning of scripts that instruct Simba to perform actions during compilation.

### Common Compiler Directives

```
{$DEFINE}
{$UNDEF}
{$IFDEF}
{$IFNDEF}
{$ELSE}
{$IFHASFILE}
{$ENDIF}
{$INCLUDE} //can be shortened to {$I}
{$LOADLIB}
{$IFDECL}
```

### Inclusion Directives

Import files and plugins:
```
{$INCLUDE SRL/osr.simba}
{$LOADLIB ../plugins/libremoteinput}
```

### Conditional Compilation

```
{$DEFINE MY_SYMBOL}

{$IFDEF MY_SYMBOL}
WriteLn 'MY_SYMBOL is defined';
{$ELSE}
WriteLn 'MY_SYMBOL is not defined';
{$ENDIF}
```

### Real-World Use Case

```
{$IFDEF WINDOWS}
{$I windows.simba}
{$ELSE}
{$I linux.simba}
{$ENDIF}
```

All conditional statements require a closing `{$ENDIF}`.

---

## 13. Arrays

**Author:** Torwent | **Created:** 2022-03-22 | **Level:** Beginner

### Introduction

An array is a list of something — characters, numbers, strings, or any data type.

### Creating Arrays

```simba
{$I SRL/osr.simba}

var
  MyArray: TIntegerArray;

begin
  MyArray := [0, 1, 2, 3, 4, 5];
end.
```

Appending:
```simba
MyArray += 0;
MyArray += 1;
```

### Accessing Elements

```simba
var
  MyArray: TStringArray;

begin
  MyArray := ['first', 'second', 'third', 'fourth', 'fifth'];
  Writeln MyArray[3]; //prints 'fourth'
  Writeln MyArray[High(MyArray)]; //prints 'fifth'
end.
```

### Looping

```simba
var
  Arr: TStringArray;
  i: Int32;

begin
  Arr := ['first', 'second', 'third', 'fourth', 'fifth'];
  for i := 0 to High(Arr) do
    Writeln Arr[i];
end.
```

### Index Out of Range Errors

Occurs when accessing non-existent indices. Common with `Login.PlayerIndex` when set too high without enough saved accounts.

### Other Types

`TPointArray`, `TBoxArray`, and 2D Arrays (e.g., ATPAs) follow identical principles.

---

## 14. TPoints

**Author:** Torwent | **Created:** 2022-03-22

### What is a TPoint?

A single coordinate with X and Y values:

```pascal
type
  TPoint = record
    X: Int32;
    Y: Int32;
  end;
```

### Creating TPoints

```pascal
var P: TPoint;
begin
  P := [100, 50];
  //or
  P := Point(100, 50);
end;
```

### Mouse Interaction

```pascal
var P: TPoint;
begin
  P := [100, 50];
  Mouse.Move(P);
  Mouse.Click(P, MOUSE_LEFT);
end;
```

### TPointArrays (TPAs)

Finding colored regions:
```pascal
var TPA: TPointArray;
begin
  SRL.FindColors(TPA, RS_ITEM_BORDER, Inventory.Bounds);
  Debug(TPA);
end;
```

### ATPAs (Array of TPointArrays)

Clustering example:
```pascal
var
  ATPA: T2DPointArray;
  TPA: TPointArray;
begin
  SRL.FindColors(TPA, RS_ITEM_BORDER, Inventory.Bounds);
  ATPA := TPA.Cluster(3);
  Debug(ATPA);
end;
```

---

## 15. Records

**Author:** Torwent | **Created:** 2022-03-22 | **Level:** Intermediate

### Record Inheritance

```pascal
type
  TBaseScript = record
    Name: String;
    Version: String;
    IsSetup: Boolean;
    TimeRunning: TStopwatch;
    Action: String;
    TotalActions: Int32;
    TotalProfit: Int32;
  end;

  TBaseWalkerScript = record(TBaseScript)
    RSW: TRSWalker;
  end;

  TBaseBankScript = record(TBaseWalkerScript)
    ScriptBank: PRSObject;
    BankTab: Int32;
  end;
```

### Creating Specialized Scripts

```pascal
type
  TWoodcutter = record(TBaseBankScript)
    LogType: TRSItem;
    AxeType: TRSItem;
  end;
```

### Method Overriding with `inherited`

```pascal
procedure TBaseBankScript.Init; override;
begin
  inherited;
  BankTab := -1;
  CollectTimer.Init(600000);
end;

procedure TWoodcutter.Init; override;
begin
  inherited;
  RSW.Setup('world');
  LogType := 'Willow logs';
  AxeType := 'Rune axe';
end;
```

---

## 16. Debugging

**Author:** Torwent | **Created:** 2022-03-22 | **Level:** Beginner

### Method 1: Printing Variables

```simba
begin
  WriteLn Options.GetZoomLevel;
end.
```

```simba
begin
  Inventory.FindItem('Mithril bar');
  Inventory.CountItem('Mithril bar');
end;
```

### Method 2: Drawing Shapes

```simba
function TScript.GetSackCount: Int32;
var B: TBox;
begin
  B := [10, 25, 70, 70];
  Debug(B);
  Result := OCR.RecognizeNumber(B, TOCRShadowRule.Create(20), RS_FONT_QUILL);
  WriteLn Result;
end;
```

### Debugging TPAs

```simba
{$I SRL/osr.simba}
{$I WaspLib/osr.simba}

var TPA: TPointArray;
begin
  SRL.FindColors(TPA, 2105392, Inventory.Bounds);
  Debug(TPA);
end;
```

---

## 17. Git Introduction

**Author:** Torwent | **Created:** 2022-03-22 | **Level:** Beginner

### Git vs. GitHub

Git is a version control system. GitHub hosts Git repositories.

### Setup Requirements

- GitHub Desktop (includes Git)
- GitHub account
- Text editor (Simba)

### Step-by-Step Process

1. **Fork the Project** on GitHub
2. **Clone Locally** via GitHub Desktop or command line:
   ```
   cd C:/Simba/Includes/
   git clone https://github.com/torwent/wasplib.git
   ```
3. **Create a Branch** for your changes
4. **Make Changes** in Simba
5. **Commit Changes** using conventional commits:
   - `fix: description`
   - `feat: description`
   - `fix(TRSWalker): description`
6. **Publish Branch** to GitHub
7. **Create Pull Request** via GitHub web interface
8. **Post-PR Management** — delete branch when done

> "Not everything you think is a good change might be considered as such by everyone."

---

## 18. WaspStats Virtual Levels

**Author:** Torwent | **Created:** 2022-03-22

### The Formula

Level 99 is reached at 13,034,431 experience. The virtual level formula uses linear progression:

```
level = floor(xp / (13034431 / 99))
```

Experience is divided by the experience-per-level ratio, with the result rounded down.

---

## 19. WaspScripts GitHub Action

**Author:** Torwent | **Created:** 2022-03-22

### Overview

Set up a GitHub Action for automatically uploading scripts and updating revisions with each commit.

### Prerequisites

- Repository with properly formatted scripts containing `SCRIPT_ID` and `SCRIPT_REVISION` fields
- WaspScripts account with email/password credentials configured

### Setup Instructions

#### 1. Create Workflow Directory

```
.github/workflows/
```

#### 2. Create Workflow File (`version.yml`)

```yaml
name: Version
on:
  push:
    branches: [master]
  pull_request:
    branches: [master]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3.2.0

      - name: Get changed files
        id: changed-files
        uses: tj-actions/changed-files@v35.2.0

      - name: Upload to waspscripts.com
        uses: Torwent/wasp-upload-action@master
        with:
          SB_URL: ${{ secrets.SB_URL }}
          SB_ANON_KEY: ${{ secrets.SB_ANON_KEY }}
          EMAIL: ${{ secrets.EMAIL }}
          PASSWORD: ${{ secrets.PASSWORD }}
          MODIFIED_FILES: ${{ steps.changed-files.outputs.all_changed_files }}

      - name: Commit and push changes
        run: |
          git config --global user.name 'WaspBot'
          git config --global user.email 'wasp@waspscripts.com'
          git commit -am "chore: github action"
          git push
```

#### 3. Configure Repository Secrets

Navigate to **Settings > Secrets and Variables > Actions** and add:

```
SB_URL: https://db.waspscripts.com
SB_ANON_KEY: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJzdXBhYmFzZSIsImlhdCI6MTcxOTQ5MDgwMCwiZXhwIjo0ODc1MTY0NDAwLCJyb2xlIjoiYW5vbiJ9.pKuuhYK-xxOWBHg3mqaxNptyvCpE5n-cjhxN3GQKr2I
EMAIL: your_email@mail.com
PASSWORD: your_password
```

#### 4. Configure Workflow Permissions

Enable **Read and write permissions** and **Allow GitHub Actions to create and approve pull requests**.

---

## 20. RuneScape Walker - How it Works

**Author:** Torwent | **Created:** 2022-03-22

### Key Concept

Take a screenshot of the minimap and search for that image in your loaded map.

### Map Selection

- **SRL-T map**: Located in `.SimbaIncludesSRL-Tosrwalker`
- **WaspLib map**: Located in `.SimbaIncludesWaspLibosrwalker`

Coordinates are relative to your map.

### Coordinate System

`RSW.GetMyPos()` returns pixel X and Y positions on the loaded map.

### Performance

- Position detection: 100-150ms typically
- Map size directly impacts speed (10,000x10,000 is 10x slower than 1,000x1,000)
- Maintain 80-pixel radius around walking areas
- Default downscaling: 8x reduction (speed vs. accuracy tradeoff)

---

# Page 3 - Advanced Topics

---

## 21. Script Stats

**Author:** Torwent | **Created:** 2022-03-22

### Requirements

- A script ID (automatically assigned upon first upload)
- Stat limits configured on the website (per 5-minute interval)

### Setting Stat Limits

Apply 20% margin. Example for 100k-200k XP/hour:
- Minimum: 6,500 XP per 5 minutes
- Maximum: 20,000 XP per 5 minutes

### Using TBaseScript (Easiest)

If using WaspLib's `TBaseScript` with XPBar methods, tracking is automatic. Call `TBaseScript.PrintReport()` to submit.

### Custom Tracking

```
APIClient.UpdatePayload(100, 2000, 0)  // First increment
APIClient.UpdatePayload(300, 3000, 0)  // Next increment
```

### Manual Submission

```
APIClient.SubmitStats(APIClient.GetUUID());
```

**Critical:** Submit every 5-15 minutes. More frequent triggers rate limiting (1 hour).

### Server Rejections

- Negative XP values
- Negative time values
- Submissions outside configured limits
- Negative GP is acceptable (tracking losses)

---

## 22. Programming Introduction

**Author:** Torwent | **Created:** 2022-03-22 | **Status:** Work in progress

### Introduction

Simba uses Lape, a Pascal dialect. Learning through Simba provides transferable programming knowledge to JavaScript, C, Python, and similar languages.

### Basic Datatypes

- **Integer** — Whole numbers (byte, shortint, integer, int64)
- **Float** — Decimal numbers (Single, Double, Extended)
- **Boolean** — True or False
- **Char** — Single character
- **String** — Character collection

### Complex Structures

#### Enums

```lape
type
  EDayOfWeek = (Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday)

var DayOfWeek = EDayOfWeek;
begin
  DayOfWeek := Wednesday;
  WriteLn DayOfWeek;
end.
```

#### Records

```lape
type
  TStudent = record
    Name: string;
    Age: Int32;
    GPA: Double;
  end;

var john: TStudent;
begin
  john := ['John Smith', 19, 4.6];
  WriteLn john;
end;
```

#### Arrays

```lape
var myArray: array of Int32;
begin
  myArray := [1,2,3,4,5,4,3,2,1];
  WriteLn myArray[0];           // first element
  WriteLn myArray[High(myArray)]; // last element
end;
```

### Why Specify Types

Different types demand different handling. Size reference:

| Size (bytes) | Unsigned Range |
|---|---|
| 1 | 0-255 |
| 2 | 0-65,535 |
| 4 | 0-4,294,967,295 |
| 8 | 0-18,446,744,073,709,551,615 |

### Keywords

**Basic:** program, begin, end, if/then/else, repeat/until, for/to/do, while/do, writeln, break, continue, case

**Declarative:** function, procedure, var, const, type, array, record

### Operators

#### Assignment

| Operator | Symbol | Example |
|---|---|---|
| Assign | `:=` | `a := 100` |
| Add & assign | `+=` | `a += 100` |
| Subtract & assign | `-=` | `a -= 100` |
| Multiply & assign | `*=` | `a *= 2` |
| Divide & assign | `/=` | `a /= 2` |
| Power & assign | `**=` | `a **= 2` |

#### Comparison

| Operator | Symbol |
|---|---|
| Equal to | `=` |
| Not equal to | `<>` |
| Less than | `<` |
| Greater than | `>` |
| Less/equal | `<=` |
| Greater/equal | `>=` |

### Variables

Named containers holding values. Rules:
- Allow letters and underscores
- Numbers permitted after initial characters
- Cannot start with numbers
- Case-insensitive

### Functions

```lape
function Gravity(mass, radius: Double): Double;
var gc: Double;
begin
  gc := 6.67*10**-11;
  Result := gc * (mass*10**24) / (radius*1000)**2;
end;

var earthGravity: Double;
begin
  earthGravity := Gravity(5.974, 6371);
  WriteLn('Gravity on Earth: ', earthGravity, ' m/s^2');
end;
```

### Control Flow

#### If-Statements

```lape
if 100 = 100 then
  WriteLn('It seems that 100 is in fact 100!')
else
  WriteLn('Well, this is interesting...');
```

#### For-Loops

```lape
var i: Int32;
begin
  for i := 0 to 10 do
    WriteLn(i);
end;
```

#### While-Loops

```lape
var counter: Int32;
begin
  counter := 1;
  while counter <= 10 do
  begin
    WriteLn('The value is: ', counter);
    Sleep(1000);
    counter += 1;
  end;
end;
```

---

## 23. RuneLite OSRS Cache Dumping

**Author:** Torwent | **Published:** 2024-06-20

### Required Downloads

- **IntelliJ IDEA** — Java IDE
- **RuneLite fork** — https://github.com/Torwent/runelite
- **OpenRS2Archive** — https://archive.openrs2.org/caches

### Setup

1. Install IntelliJ IDEA
2. Download the RuneLite fork
3. Build following official RuneLite guide

### Cache Acquisition

From OpenRS2Archive (filter: oldschool, live, en). Need:
1. Cache (.dat2/.idx files)
2. Keys (JSON format)

### Directory Structure

```
cache/
  input/
    cache-openrs2#1819/
      cache/
        main_file_cache.dat2
        main_file_cache.idx0
        main_file_cache.idx255
      keys-openrs2#1819.json
  output/
```

### Available Dumpers

- **SimbaMapImageDumper** — Map imagery
- **SimbaHeightmapDumper** — Terrain elevation
- **SimbaCollisionMapDumper** — Collision boundaries
- **SimbaObjectInfoDumper** — Object metadata

### Configuration

Main class: `net.runelite.cache.SimbaCacheDumper`

Arguments:
```
-cachedir "C:\path\to\cache\input"
-cachename "cache-openrs2#1819"
-outputdir "C:\path\to\cache\output"
```

Output contains: maps.zip, heightmaps.zip, collision.zip, objectinfo.zip

---

## 24. TRSObjectV2 Finding & Usage

**Author:** Goobtacular

### Part 1: Basic Object Finding

#### Setting Up Map and Chunks

Reference [Mejrs' chunk map](https://mejrs.github.io/osrs?m=-1&z=2&p=0&x=3244&y=3415&layer=grid) for coordinates.

```simba
type
  TRSMapChunk = record
    Chunk: TBox;
    Planes: TIntegerArray;
  end;
```

#### Loading Chunks

```simba
{$I SRL-T/osr.simba}
{$I WaspLib/osr.simba}

begin
  Map.SetupChunk(Chunk([49, 55, 51, 52], 0), 8);
  Objects.Setup(Map.Objects, @Map.Walker);
end.
```

#### Finding and Interacting with Objects

```simba
var
  InfoBooth: Array of TRSObjectV2;
  ActualBooth: TRSObjectV2;

begin
  Map.SetupChunk(Chunk([49, 55, 51, 52], 0), 8);
  Objects.Setup(Map.Objects, @Map.Walker);
  InfoBooth := Objects.GetAll('Information booth');

  if Length(InfoBooth) > 0 then
  begin
    ActualBooth := InfoBooth[0];
    ActualBooth.WalkClick(True, 10);
  end;
end.
```

### Part 2: Multiple Chunks, Positioning, and Refinement

#### Loading Multiple Chunks

```simba
const
  FAL_CHUNK: TRSMapChunk = [[45, 55, 47, 51], [0]];
  DWV_CHUNK: TRSMapChunk = [[45, 154, 48, 150], [0]];

begin
  Map.SetupChunksEx([FAL_CHUNK.Chunk, DWV_CHUNK.Chunk], [0], 8);
  Objects.Setup(Map.Objects, @Map.Walker);
end.
```

#### Position Tracking

```simba
WriteLN(Map.Position);
```

Each tile = 4 pixels in collision map.

#### Manual Path Walking

```simba
OurPath := [[7972, 36629],[7972, 36599],[7972, 36569],[7972, 36539],[7972, 36509]];
Map.Walker.WalkPath(OurPath, 0, False);
```

#### WebWalk Navigation

```simba
Map.Walker.WebWalk([7972, 36629], 0, 0.5, False);
```

#### Refining GetAll Results

Filter by coordinates from cache JSON files:

```simba
AllTrapdoors := Objects.GetAll('Trapdoor');

for I := 0 to High(AllTrapdoors) do
  for II := 0 to High(AllTrapdoors[I].Coordinates) do
    if AllTrapdoors[I].Coordinates[II] = Point(7982, 36630) then
      ActualTrapdoor := AllTrapdoors[I];
```

#### Complete Example: Trapdoor Navigation

```simba
{$I SRL-T/osr.simba}
{$I WaspLib/osr.simba}

const
  FAL_CHUNK: TRSMapChunk = [[45, 55, 47, 51], [0]];
  DWV_CHUNK: TRSMapChunk = [[45, 154, 48, 150], [0]];

var
  AllTrapdoors: Array of TRSObjectV2;
  ActualTrapdoor: TRSObjectV2;
  I, II: Integer;

begin
  Map.SetupChunksEx([FAL_CHUNK.Chunk, DWV_CHUNK.Chunk], [0], 8);
  Objects.Setup(Map.Objects, @Map.Walker);

  AllTrapdoors := Objects.GetAll('Trapdoor');

  for I := 0 to High(AllTrapdoors) do
    for II := 0 to High(AllTrapdoors[I].Coordinates) do
      if AllTrapdoors[I].Coordinates[II] = Point(7982, 36630) then
        ActualTrapdoor := AllTrapdoors[I];

  ActualTrapdoor.WalkClick(False, 5);

  if ChooseOption.IsOpen(2000, 50) then
    ChooseOption.Select('Climb-down', MOUSE_LEFT, False, True);
end.
```

---

## 25. Walker and Doors

**Author:** bootje2000 | **Published:** 2024-08-15

### Setting up TRSMap

```simba
{$I WaspLib/osr.simba}
begin
  Map.SetupChunks([[[49, 54, 51, 52],[0]]]); //Varrock area
end.
```

### Walking Through Doors

Enable the door handler (disabled by default):

```simba
{$I WaspLib/osr.simba}

var destination: TPoint;
begin
  Map.SetupChunks([[[49, 54, 51, 52],[0]]]);
  Map.Loader.Graph.UseCollisionData := True;
  Map.Walker._DoorHandler.Enabled := True;

  destination := [8856, 36778];
  Map.Walker.WebWalk(destination);
end.
```

### Bonus: Finding Map Points

```simba
{$DEFINE SRL_DISABLE_REMOTEINPUT}
{$I SRL-T/osr.simba}
{$I WaspLib/osr.simba}

const USE_KEYBOARD = True;

procedure Run();
var p: TPoint;
begin
  while True do
  begin
    Wait(1000);
    p := map.walker.Position();

    if not USE_KEYBOARD then
    begin
      Writeln('[', p.X, ', ', p.Y, '];');
      Continue;
    end;

    if Keyboard.IsKeyDown(VK_SPACE) then
    begin
      Writeln('[', p.X, ', ', p.Y, '];');
      Wait(1000);
    end
  end;
end;

begin
  Map.SetupChunks([[[47,49,49,47],[0]], [[25,196,27,194],[0]]]);
  ClearDebug();
  Run();
end.
```

---

## 26. Insight into WebWalking with Doors

**Author:** bootje2000 | **Published:** 2024-08-16

### Chapter 1: Identifying Doors

The system analyzes collision maps where white = walkable, black = walls, red = doors. Doors are discovered by clustering red pixels.

**Door Classification:**
- **Normal doors:** Size 4
- **Wide doors:** Size 8

**Integration with WebGraph:**
1. Create nodes 2 pixels away on both sides of door center
2. Connect nodes directly through the door
3. Link to nearest nodes in same walkable cluster
4. Only retain doors separating distinct clusters

**Tile Structure:** Each tile = 4x4 pixels. Walker normalizes positions to [0,2] within tile grid.

### Chapter 2: Opening Doors

**Hard Solve Routine:**
1. Move to tile before the door
2. Rotate camera to face door
3. Locate tile behind door, position mouse at center
4. Check UpText for interaction prompts
5. Click to proceed

**General Routine:**
1. Position close enough for destination tile visibility
2. Verify camera angle compatibility
3. Hover near door edge
4. Check door state via UpText
5. Click to open or proceed

### Chapter 3: WebWalking Through Doors

**Door-Enhanced Process:**
- Calculate path within same walkable cluster
- Identify doors via `TRSWalkerV2.GetDoorsOnPath`
- Process doors sequentially with `TRSWalkerV2.WalkDoorway`
- Retry up to 3 times with general routine; fall back to hard solve

The `_DoorHandler` manages flags: FlagMoved, Handling, SettingUp, Skipped.

---

## 27. Minimap Dot Tiles

**Author:** bootje2000

### The Problem

Determining exact tile coordinates from minimap dots. Item dots appear between grid points. The green dot that the item belongs to is always the one to the bottom left.

### Solution

```simba
{$I Wasplib/osr.simba}

function GetMinimapGrid(angle: Single): Vector3Array;
var x, y: Integer;
begin
  for x := Minimap.Center().X - 20 * 4 to Minimap.Center().X + 20 * 4 with 4 do
    for y := Minimap.Center().Y - 20 * 4 to Minimap.Center().Y + 20 * 4 with 4 do
      Result += Vec3(x, y).RotateXY(angle, Minimap.Center().X, Minimap.Center.Y);
end;

function DotsToTile(dots: TPointArray; angle: Single): TPointArray;
var
  dotVecs, mmGrid: Vector3Array;
  i: Integer;
begin
  dotVecs.FromTPA(dots);
  dotVecs := dotVecs.Offset([2,1]);

  mmGrid := GetMinimapGrid(angle);
  for i := 0 to High(dotVecs) do
    dotVecs[i] := mmGrid.NearestVec(dotVecs[i]);

  Result := dotVecs.ToTPA();
end;

var
  mmGrid: Vector3Array;
  mmGridTPA, dots: TPointArray;
  dot: TPoint;
  rect: TRectangle;
  angle: Single;
  bmp: TMufasaBitmap;
begin
  RSClient.RemoteInput.EnableRealInput();
  Map.SetupChunks([[[53,149,55,147],[2]]]);
  while True do
  begin
    angle := Minimap.GetCompassAngle(False);
    mmGrid := GetMinimapGrid(angle);
    dots := Minimap.GetDots(ERSMinimapDot.ITEM);
    dots := dotsToTile(dots, angle);

    bmp.FromClient();
    bmp.DrawTPA(mmGrid.ToTPA, $FF00);
    bmp.DrawTPA(dots, $FF00FF);

    for dot in dots do
    begin
      dot := Map.MM2Map(dot, angle);
      dot := RSTranslator.NormalizeNearestTile(dot);
      rect := Map.GetTileMS(dot);
      bmp.DrawRect(rect, $FF);
    end;

    bmp.Debug();
    Wait(500);
  end;
end.
```

### Technical Notes

Using `Vector3` instead of `TPoint` allows decimal precision, reducing rounding errors. The offset [2,1] snaps dots to grid points reliably.

---

## 28. Simba Editor Keyboard Shortcuts

**Author:** TazE

### Basic Operations

| Shortcut | Function |
|----------|----------|
| CTRL+Q | Exit application |
| CTRL+W | Close current tab |
| CTRL+O | Open file |
| CTRL+S | Save current file |
| CTRL+A | Select all content |

### Text Editing

| Shortcut | Function |
|----------|----------|
| CTRL+Z | Undo |
| CTRL+SHIFT+Z | Redo |
| CTRL+X | Cut |
| CTRL+C | Copy |
| CTRL+V | Paste |
| CTRL+R | Find and Replace |
| CTRL+F | Find |
| CTRL+G | Go to line |

### Line Operations

| Shortcut | Function |
|----------|----------|
| CTRL+T | Delete line under cursor |
| CTRL+Y | Delete current line |
| CTRL+N | Insert new line under |
| CTRL+M | Insert new line and move cursor |
| CTRL+/ | Toggle line comment |
| CTRL+SHIFT+I | Indent line |
| CTRL+SHIFT+U | Deindent line |

### Code Navigation & Development

| Shortcut | Function |
|----------|----------|
| CTRL+SPACE | Inline function hints |
| CTRL+SHIFT+SPACE | Function matching dropdown |
| CTRL+MOUSE_1 | Go to declaration |
| CTRL+SHIFT+R | Run script |
| CTRL+SHIFT+S | Stop execution |
| CTRL+SHIFT+C | Compile code |

### Menu Access

| Shortcut | Function |
|----------|----------|
| ALT+F | File menu |
| ALT+E | Editor menu |
| ALT+T | Tools menu |
| ALT+S | Script menu |
| ALT+V | View menu |
| ALT+H | Help menu |

### Code Folding

| Shortcut | Function |
|----------|----------|
| ALT+SHIFT+1 | Fold all |
| ALT+SHIFT+2 | Fold all except current |
| ALT+SHIFT+3-5 | Fold nested levels |
| ALT+SHIFT+6 | Unfold all |

---

## 29. Bolt Launcher Setup (Debian)

**Author:** TazE | **Published:** 2025-02-21

### Installation

> **Note:** Simba must be installed separately.

```bash
wget https://raw.githubusercontent.com/Torwent/wasp-setup/master/linux/bolt-setup.sh
chmod +x bolt-setup.sh
./bolt-setup.sh
```

After completion, log out and back in.

### Uninstallation

```bash
wget https://raw.githubusercontent.com/Torwent/wasp-setup/master/linux/bolt-uninstall.sh
chmod +x bolt-uninstall.sh
./bolt-uninstall.sh
```

### Running

Launch from application menu or execute `bolt` in terminal. Requires Java 17.

---

## 30. Sending Discord Messages with Simba

**Author:** TazE | **Created:** 2025-04-28

### Setting Up the Client

```pascal
{$I WaspLib/osr.simba}
{$I Wasplib/optional/handlers/discord.simba}

var
  Discord: TDiscordClient;
  WebhookURL: String;
begin
  Discord.Setup();

  WebhookURL := 'https://discord.com/api/webhooks/your_webhook_id/your_webhook_token';

  if not Discord.SetWebhook(WebhookURL) then
  begin
    WriteLn('Failed to set webhook: ' + Discord.LastError);
    Exit;
  end;

  Discord.SetUsername('Simba Notifier');
  Discord.SetAvatar('https://raw.githubusercontent.com/Torwent/wasp-webapp/refs/heads/main/static/favicon.png');
  Discord.Free();
end.
```

### Sending Simple Messages

```pascal
Discord.Webhook.Content := 'Hello from Simba!';

if Discord.Send() then
  WriteLn('Simple message sent successfully!')
else
  WriteLn('Failed to send message: ' + Discord.LastError);
```

### Embeds

```pascal
var EmbedIdx: Int32;

Discord.Webhook.Content := 'Here is a status update:';
EmbedIdx := Discord.Webhook.AddEmbed();

with Discord.Webhook.Embeds[EmbedIdx] do
begin
  Title := 'Bot Status';
  Description := ':robot: Everything is running smoothly.';
  Color := clGreen;
  Footer := 'Checked at ' + FormatDateTime('hh:nn:ss', Now);
end;

Discord.Send();
```

### Mentioning Users

Enable Developer Mode in Discord settings, right-click user to copy ID, then:

```pascal
var AdminUserID: String;
AdminUserID := '123456789012345678';

Discord.Webhook.Content := 'Alert! ' + Discord.MentionUser(AdminUserID);
Discord.Send();
```

### Sending Files and Screenshots

**Files:**
```pascal
Discord.Webhook.Content := 'Here is the latest log file:';
Discord.SendFile(ScriptPath + 'script_log.txt');
```

**Screenshots:**
```pascal
Discord.Webhook.Content := 'Current game state:';
Discord.SendScreenshot(True); // True = anonymize sensitive details
```

### Configuration File (discord.json)

Settings auto-save to `discord.json`:

```json
{
  "webhook_url": "https://discord.com/api/webhooks/your_id/your_token",
  "webhook_username": "My Default Bot Name",
  "webhook_avatar": "https://example.com/avatar.png"
}
```

### Complete Example

```pascal
{$I WaspLib/osr.simba}
{$I Wasplib/optional/handlers/discord.simba}

var
  Discord: TDiscordClient;
  WebhookURL: String;
  EmbedIdx: Int32;
  AdminUserID: String;

begin
  Discord.Setup();
  WebhookURL := 'https://discord.com/api/webhooks/your_id/your_token';
  if not Discord.SetWebhook(WebhookURL) then Exit;
  Discord.SetUsername('Script Reporter');

  try
    // Startup message
    Discord.Webhook.Content := 'Script started!';
    Discord.Send();
    Wait(1000);

    // Progress embed
    Discord.Webhook.Content := 'Status Update';
    EmbedIdx := Discord.Webhook.AddEmbed();
    with Discord.Webhook.Embeds[EmbedIdx] do
    begin
      Title := 'Progress Report';
      Description := 'Task A completed successfully.';
      Color := clGreen;
      Footer := FormatDateTime('hh:nn:ss', Now);
    end;
    Discord.Send();
    Wait(1000);

    // Screenshot
    Discord.Webhook.Content := 'Current view:';
    Discord.SendScreenshot(True);
    Wait(1000);

    // Error with mention
    AdminUserID := '123456789012345678';
    Discord.Webhook.Content := 'Error! ' + Discord.MentionUser(AdminUserID);
    EmbedIdx := Discord.Webhook.AddEmbed();
    with Discord.Webhook.Embeds[EmbedIdx] do
    begin
      Title := ':warning: Alert';
      Description := 'Critical error: Target not found.';
      Color := clRed;
    end;
    Discord.Send();
    Wait(1000);

    // Final message
    Discord.Webhook.Content := 'Script finished.';
    Discord.Send();

  finally
    Discord.Free();
  end;
end.
```
