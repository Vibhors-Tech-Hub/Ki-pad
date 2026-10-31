# Ki-pad

Alright, so while working in KiCad, I need to use a lot of shortcuts. And not only are there many, but they're also a bit easy to mess up. So, while Hack Club recommends Macropads specifically to beginners, I decided to give it a go, without making things much complex, so I could have a easier, and more power workflow! And that also explains it's *unique* name!

# Features

So, with the number of shortcuts in KiCad that I use almost daily, I decided that a Macropad with **12 MX2A-H1NA keys** would be great. And I also added **two PEC11R-4220F-S0024 rotary encoders**; one for zooming in and zooming out (not only for KiCad), and one for scrolling (through massive datasheets).

So, I had two options for the switches then, either route each of them separately to my controller, or use a **matrix-based configuration** with rows and columns. I chose the later as it not only uses way less GPIOs, but most open-source projects and firmwares use it.

So, for the controller, I realised most projects on one way or the other use the RP2040. So, I too went with it. To keep things simple I decided to use a dev-board instead of using the raw QFN-56. Requiring **12 GPIOs**, the widely used Seed Studio RP2040 XIAO fell short by just one GPIO. So, I went with the **Waveshare RP2040 Zero** board.

I said that I didn't want to make this much complex, but what's a Macropad without lights? So, I also used **12 SK6812MINI-E RGB LEDs**, all daisy-chained underneath the switches. The SK6812MINI-E operate on 5V, and the min voltage to control them, according to the datasheet is 5 * 0.7 = 3.5V. As the RP2040's GPIO pins are only 3.3V tolerant, I had to go with a **74AHCT1G125 logic-level shifter**

As I said, to keep things simple, I didn't add a OLED, though it could be used for *something*?

# Enclosure

For this revision, I didn't design an enclosure. I didn't think it was absolutely required, as I was just making it to make my daily workflow easier, and while I've designed a LOT of PCBs, I'm a newbie to 3D CAD designing. But I could aways sesign one with MDF if I need it when I get the PCB in hand; whihcb is exactly why I added 4 M2.5 mounting holes.

# Firmware

Now, to actually map keys and rotary encoders to their functions, I had two options. Either to write my own firmware, or use Vial. Now, I could write my own firmware, but considering I just wanted it to help me with KiCad, and I wanted to keep it highly customizable, I decided to go with Vial. Vial uses an interactive GUI to assign shortcuts to switches instantly, and in the end generates a .uf2 file I can flash onto my RP2040. But it has a catch; I must physically plug-in my device to program it. Hence, I don't have any firmware inside it currently. But as soon as I get the PCB, I'll commit a .uf2 file in a firmware directory.

# Schematic
<img width="1229" height="866" alt="image" src="https://github.com/user-attachments/assets/da421ef9-3ef2-4333-9495-6b820b8788f4" />
<img width="1226" height="867" alt="image" src="https://github.com/user-attachments/assets/6ab49814-51e4-41fa-a1c0-dacd26204d7d" />
<img width="1226" height="869" alt="image" src="https://github.com/user-attachments/assets/b8117f6a-6d98-4a1d-93fc-d6994308a1f7" />

# PCB

<img width="317" height="545" alt="image" src="https://github.com/user-attachments/assets/33b15164-ac6a-474d-9754-893231a17d83" />
<img width="312" height="543" alt="image" src="https://github.com/user-attachments/assets/d90faa66-1545-4008-b635-af31a7404300" />

# 3D view

<img width="525" height="911" alt="image" src="https://github.com/user-attachments/assets/971ea8c2-34bf-4d88-81af-631e2cb8a79c" />
<img width="526" height="909" alt="image" src="https://github.com/user-attachments/assets/bab62da1-a6e1-4fef-a383-e8491eaf323c" />
