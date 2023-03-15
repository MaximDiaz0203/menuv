# MenuV | Standalone Menu for FiveM | NUI Menu
[![N|CoreV](https://i.imgur.com/iq1llQG.jpg)](https://github.com/MaximDiaz0203/menuv)

[![Issues](https://img.shields.io/github/issues/MaximDiaz0203/menuv.svg?style=for-the-badge)](https://github.com/MaximDiaz0203/menuv/issues)
[![License](https://img.shields.io/github/license/MaximDiaz0203/menuv.svg?style=for-the-badge)](https://github.com/MaximDiaz0203/menuv/blob/master/LICENSE)
[![Forks](https://img.shields.io/github/forks/MaximDiaz0203/menuv.svg?style=for-the-badge)](https://github.com/MaximDiaz0203/menuv)
[![Stars](https://img.shields.io/github/stars/MaximDiaz0203/menuv.svg?style=for-the-badge)](https://github.com/MaximDiaz0203/menuv)
[![Discord](https://img.shields.io/badge/discord-Maxim%20D%C3%ADaz%230203-7289da?style=for-the-badge&logo=discord)](https://discordapp.com/users/553607177432989696)

---

**[MenuV](https://github.com/MaximDiaz0203/menuv)** is a library written for **[FiveM](https://fivem.net/)** and only uses NUI functionalities. This library allows you to create menus in **[FiveM](https://fivem.net/)**. This project is open-source and you must respect the [license](https://github.com/MaximDiaz0203/menuv/blob/master/LICENSE) and the hard work.

## Features
- Support for simple buttons, sliders, checkboxes, lists and confirms
- Support for emojis on items
- Support for custom colors (RGB)
- Support for all screen resolutions.
- Item descriptions
- Rebindable keys
- Event-based callbacks
- Uses `2 msec` while menu open and idle.
- Themes: **[default](https://i.imgur.com/OLLLfpA.png)** or **[native](https://i.imgur.com/QBjm0Zn.png)**

## Compile files
**[MenuV](https://github.com/MaximDiaz0203/menuv)** uses **[VueJS](https://vuejs.org/v2/guide/installation.html#NPM)** and **[TypeScript](https://www.npmjs.com/package/typescript)** with **[NodeJS](https://nodejs.org/en/)**. If you want to use the **`master`** files, you need to build the hole project by doing:

```sh
npm install
```
After you have downloaded/loaded all dependencies, you can build **[MenuV](https://github.com/MaximDiaz0203/menuv)** files by executing the following command:
```sh
npm run build
```

After the command is executed you will see a `build` folder containing all the resource files.
Copy those files to a resource folder called `menuv` or create a symbolic link like that:

### Windows

```batch
mklink /J "repositoryPath\build" "fxResourcesPath\menuv"
```

### Linux

```sh
ln -s "repositoryPath\build" "fxResourcesPath\menuv"
```

You can also check this tutorial on how to make a link:
[https://www.howtogeek.com/howto/16226/complete-guide-to-symbolic-links-symlinks-on-windows-or-linux/](https://www.howtogeek.com/howto/16226/complete-guide-to-symbolic-links-symlinks-on-windows-or-linux/)

**When your downloading a [release](https://github.com/MaximDiaz0203/menuv/releases), you don't have to follow this step, because all [release](https://github.com/MaximDiaz0203/menuv/releases) version are build version.**

## How to use?
> ⚠️ **example.lua** can't be added in the **menuv** fxmanifest, you must make an seperate resource like: **[menuv_example](https://github.com/MaximDiaz0203/menuv/tree/master/example)**
1. Add `start menuv` to your **server.cfg** before the resources that's uses **menuv**
2. To use **[MenuV](https://github.com/MaximDiaz0203/menuv)** you must add **@menuv/menuv.lua** in your **fxmanifest.lua** file.

```lua
client_scripts {
    '@menuv/menuv.lua',
    'example.lua'
}
```

### Create a menu
Create a menu by calling the **MenuV:CreateMenu** function.
```ts
MenuV:CreateMenu(title: string, subtitle: string, position: string, red: number, green: number, blue: number, texture: string, disctionary: string, namespace: string, theme: string)
```
**Example:**
```lua
local menu = MenuV:CreateMenu('MenuV', 'Welcome to MenuV', 'topleft', 255, 0, 0, 'size-125', 'default', 'menuv', 'example_namespace', 'native')
```

### Create menu items
Create a item by calling **AddButton**, **AddConfirm**, **AddRange**, **AddCheckbox** or **AddSlider** in the created menu
```ts
/** CREATE A BUTTON */
menu:AddButton({ icon: string, label: string, description: string, value: any, disabled: boolean });

/** CREATE A CONFIRM */
menu:AddConfirm({ icon: string, label: string, description: string, value: boolean, disabled: boolean });

/** CREATE A RANGE */
menu:AddRange({ icon: string, label: string, description: string, value: number, min: number, max: number, disabled: boolean });

/** CREATE A CHECKBOX */
menu:AddCheckbox({ icon: string, label: string, description: string, value: boolean, disabled: boolean });

/** CREATE A SLIDER */
menu:AddSlider({ icon: string, label: string, description: string, value: number, values: [] { label: string, value: any, description: string }, disabled: boolean });
```
To see example in practice, see [example.lua](https://github.com/MaximDiaz0203/menuv/blob/master/example/example.lua)

### Events
In **[MenuV](https://github.com/MaximDiaz0203/menuv)** you can register event-based callbacks on menu and/or items.
```ts
/** REGISTER A EVENT ON MENU */
menu:On(event: string, callback: function);

/** REGISTER A EVENT ON ANY ITEM */
item:On(event: string, callback: function);
```

## License
Project is written by **[ThymonA](https://github.com/MaximDiaz0203/)** and published under
**GNU General Public License v3.0**
[Read License](https://github.com/MaximDiaz0203/menuv/blob/master/LICENSE)

## Screenshot
**How is this menu made?** see **[example.lua](https://github.com/MaximDiaz0203/menuv/blob/master/example/example.lua)**

## Original Code by
[ThymonA](https://github.com/ThymonA)


Default | Native
:-------|:--------
![MenuV Default](https://i.imgur.com/OLLLfpA.png) | ![MenuV Native](https://i.imgur.com/QBjm0Zn.png)
[Default Theme](https://i.imgur.com/OLLLfpA.png) | [Native Theme](https://i.imgur.com/QBjm0Zn.png)
