+++
title = "About Me"
date = "2020-04-30"
[ author ]
  name = "Jakub Duchniewicz"
+++

## [Hello there!](https://www.youtube.com/watch?v=rEq1Z0bjdwc)
{{< image src="/me2_resized.jpg" alt="Picture of me!" position="center" style="border-radius: 8px" >}}

My name is **Jakub Duchniewicz** and this is my personal space :grin:

I am currently working as a programmer at **[Tietoevry]** doing 5G NR L1 development from the Modem UE side on a custom ASIC for an **Unspecified Client**. Also, I am a co-founder of **[Sticky Piston Studios]** - a jack-of-all-trades company where **we make any advanced tech tick**!

My skills include low-level programming in **C**, **C++** and **Rust**. Being proficient in hardware accelerators, such as **FPGA**s I happen to know some **VHDL** and **SystemVerilog**. Lastly, being a hardcore **gamejammer** I am familiar with the **Unity** engine and other popular tools of the trade.
In my free time I am doing a ton of **bouldering**, learning **hardware hacking**, some **reverse engineering** and taking care of my cute humongous German Shepherd **Bruno**

I have recently graduated with an MSc in **Embedded Systems** at **KTH Royal Institute of Technology**, Sweden and **University of Turku**, Finland as a part of EIT Digital Programme. Thesis titled: *"FPGA accelerated tcpdump using eBPF"* goes into the topic of hardware acceleration of packet capturing in embedded Linux system using an FPGA. It was a cooperative effort between KTH and [Tietoevry].

I have also graduated from **Warsaw University of Technology** with the highest degree for my thesis: *"FPGA based hardware accelerator for musical synthesis for Linux system"*.

You can see both theses under the *Achievements* section below.

**Social [links] 🗡️:** \
 - [CV] \
 - [GitHub] \
 - [LinkedIn] \
:coffee: - [Sponsor :)]

## What's in here?
---
On this website you can find some thoughts of mine on several topics ranging from:

* Zephyr, Linux and other OS's
* Microcontrollers and FPGA's
* Lifestyle and travelling :ocean:
* Hardware hacking and retro consoles
* Systems Programming
* Game Engines and Game Development
* Keeb stuff - HHKB2 Workman user here :muscle:
* Machine Learning

Please feel free to reach out to me, or leave a comment, I am always eager to have a chat or give a helping hand!
*Also, if you like what I do and you want more content, feel free to buy me a [coffee] :coffee:*

## Achievements
---
### FOSDEM 2024
{{< svg path="static/fosdem_logo.svg" width="30%" height="30%" >}}

At **[FOSDEM]** 2024, I [presented my] and **[Tietoevry]**'s role and experience in revolutionizing the **5G** networks via adoption of **ORAN** or projects that implement it, such as **Intel FlexRAN** that I had pleasure developing. The core message of my talk was the necessity for a *solid open-source foundation at the lowest layer of the telecom industry's processing chain*. I also discussed the importance of opening up the ecosystem in the context of **5G** and shed some light on the intricate structure of the network, especially how the **[L1]** works.
**Skills:** `C`, `5G`, `Radio Networks`, `L1`

### Hackaday Supercon
{{< image src="/Hackadaysupercon_logo.jpg" alt="Hackaday Supercon" position="center" style="border-radius: 8px;" >}}

This is the second time we spoke on the topic of *[Porting an AI Powered Wearable Health Monitor to Zephyr on Open Hardware]*. See below for details!

### Embedded Open Source Summit
{{< image src="/EOSS_logo.png" alt="Embedded Open Source Summit 2023" position="center" style="border-radius: 8px;" >}}

Me and **[Szymon Duchniewicz]** spoke at **Embedded Open Source Summit** on the topic of *[Porting an AI Powered Wearable Health Monitor to Zephyr on Open Hardware]*. You may refer to [the video] and [the blog post] for more details. In short we briefly explained the first iteration of our project on non-Zephyr OS (Arduino) and the presented the challenges and shortcomings of that approach. Then showed how we ported the solution to [QuickLogic EOS S3 platform] and ran it on **[Zephyr OS]**. We also commented on how we designed the entire system, including the **Machine Learning** model for Blood Pressure inference (whose breakdown you can see in [this blog post]). The entire presentation featured a plethora of tips regarding porting Zephyr to a new platform (as it turned out the EOS S3 had *really* basic Zephyr support.\
**Skills:** `C`, `Zephyr`, `Machine Learning`, `Hardware acceleration`, `3D printing`

### State of Open Con
{{< image src="/sooc23.png" alt="State of Open Con 23" position="center" style="border-radius: 8px;" >}}

During this presentation, the topic of **hardware acceleration** using **FPGA**s in an **embedded Linux** was covered. Presented was a solution based on a custom **Linux** distribution assembled using the **Buildroot** tool, specially configured and patched **Linux** kernel, **uboot bootloader**, and the **programmable logic** for packet acceleration.

The project was evaluated on a **De0-Nano System on Chip development board** through modifications to burst lengths, packet sizes, and programmable logic clock frequency.
Metrics include packet capturing time, time per packet, and consumed power.
Finally, the results were contrasted with baseline **embedded Linux** packet processing by inspection of a packet’s path through the kernel.

After the presentation, a lengthy discussion arose and interesting future ideas for the project were imagined. It can be viewed [online here].

**Skills:** `C`, `FPGA`, `Linux`, `Networking`, `Hardware acceleration`

### The Deluge
{{< image src="/deluge.png" alt="The Deluge" position="center" style="border-radius: 8px;" >}}

My name is Jakub Duchniewicz and welcome to the **[Sticky Piston Studios]**!

I have been game jamming since 2016 and when in 2019 me and **[Mateusz Szymoński]** have jammed for the first time - **[Eternal Feud]** (a game where you shoot at each other with bleating sheep) was born. Unfortunately in 2020 Covid struck and all on-site jams were canceled.

We came back to on-site jamming in 2022 and in force! After onboarding **[Szymon]** 1 jam earlier, **we were able to win the entire competition of HackYeah 2022!**

**[The Deluge]** was made in **only 24 hours** and is a combination of **FTL**-like map exploration, a deck builder and a real-time strategy battle fighting. We used **DALL-E** for generation of most of the graphics and made the rest on our own. Be sure to check it out on **itch.io**!

**Skills:** `Unity`, `Generative AI`, `C#`, `Game design`

### '21 GSoC beagleboard.org - GPGPU using OpenGL ES on BBBa
{{< image src="/beagle.png" alt="beagleboard.org" position="center" style="border-radius: 8px;" >}}

This project was part of the **Google Summer of Code** initiative under the **[beagleboard.org]** organization. With this library you can accelerate your computations using built-in **SGX GPU** onboard the **Beaglebone Black**.

Motivation for the project was scarcity of heteregenousity on the **BBB** platform which means that most computations were done either on the **CPU** or in the **PRU** or both of them. Meanwhile **GPU** on the **SoC** was laying mostly untouched apart from some rare occasions where rendering was required - **[this is unacceptable]** and [this project aims to change that]!

**Skills:** `C`, `OpenGL ES`, `Hardware acceleration`, `GPGPU`

## Projects
---
### Rustalizer
{{< image src="/playing_tui.gif" alt="Rustalizer" position="center" style="border-radius: 8px" >}}

A simple audio frequency visualizer written in **Rust**. Use it to accompany you in you daily job as a Winamp-style distractor :)
Delivered both as a **GTK** desktop application and as a **console app**.

**Skills:** `Rust`, `GTK`, `Signal processing`

### PolyEngine
{{< image src="/polyengine.png" alt="PolyEngine" position="center" style="border-radius: 8px" >}}

While I was a co-chair of **Student Society [KNTG Polygon]**, I heavily contributed to creation of the **[PolyEngine]** game engine. It was written in the **Entity Component System** programming architectural pattern, effectively realizing **data-oriented programming**. During various gamejams and meetings we created **extensible and professinal engine** that always lacked a functional editor :). If you are interested on picking it up, drop me a line!


**Skills:** `C`, `C++`, `Game Engines`, `CMake`, `Meson`, `Vulkan`

### BIBoP
{{< image src="/bibop/case.png" alt="BIBoP" position="center" style="border-radius: 8px" >}}
*Image courtesy of [Szymon Duchniewicz].*

Basis for the **[EOSS23 talk]** me and [Szymon] are doing in June. A **Machine Learning** model for **Blood Pressure inference** from **photopletysmography** sensor data was deployed by means of **AWS Lambda**. The device used Wi-Fi for communication with the model and obtaining BP prediction data that was displayed on the small LCD screen. It was also powered by a LiPo battery so that it could be worn tetherlessly.

**Skills:** `Embedded IoT`, `Analog electronics`, `Machine Learning`, `MQTT`, `SAMD microcontrollers`, `AWS`

### Envidrawer
{{< image src="/envidrawer.jpg" alt="Envidrawer" position="center" style="border-radius: 8px" >}}
*Image courtesy of [Anna Tatarzyńska].*

**Skills:** `Embedded IoT`, `Analog electronics`, `Woodworking`, `3D printing`
## Academia
---
## MSc Thesis:
### *"FPGA accelerated tcpdump using eBPF"*
