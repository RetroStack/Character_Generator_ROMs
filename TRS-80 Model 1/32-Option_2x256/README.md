# TRS-80 Model 1 Character Generator ROMs - 32 Options

*Suitable for 2x256 ROMs (and beyond)*

This character ROM is combining multiple other character generator ROMs in one binary to be able to select a specific ROM on-the-fly. 

There are four versions: (click to download)
- [Normal](character_set_32.bin) - Here, all ROMs are sequentially listed. This is the default option.
- [Reversed/Inverted](character_set_32_r.bin) - All address are inverted (effectively reversing the normal list). This is useful if your adapter uses active-low addressing. Use this when using solder jumpers or jumper caps to configure 
- [Bit-Flipped](character_set_32_f.bin) - All bits in an address are flipped from MSB to LSB. This is useful if you want to set the bit-address for selection from left-to-right (like using a DIP switch).
- [Reversed/Inverted & Bit-Flipped](character_set_32_rf.bin) - Combines the last two options in one: all addresses are inverted and the bits are flipped. Use this when using DIP switches to configure any RetroStack character generator adapters (like the [MCM776x character generator adapter](https://github.com/RetroStack/MCM776x_CharGen_Adapter)).

The following lists are also available as a [printable PDF version](Configuration.pdf).

## Combinations and Features

This mode is active when `bit 5` is off.

|Bit|Description|Example Image|
|-|-|-|
|`1`|Floating "a"|![Mask 1](../Images/Mask_1.jpg)|
|`2`|Special characters like arrows & pound sign|![Mask 2](../Images/Mask_2.jpg)|
|`3`|Descenders|![Mask 3](../Images/Mask_3.jpg)|
|`4`|Duplicate capital letters|![Mask 4](../Images/Mask_4.jpg)|

## Sequential Character Sets

This mode is active when `bit 5` is on. All other bits (`bit 1` to `bit 4`) selects each ROM sequentially.

It has multiple parts:
- Typical Model 1 Character Sets (e.g. Kana, GenDon 3)
- Debugging Character Sets (e.g. blank, cross, ...)
- Character set typed in from the datasheet of common character generators (e.g. LCD display, Teletext, ...)
- Custom & System specific character sets

|#|Bit Address (Normal)| Bit Address (Bit-Flipped)|Name|Source|Comment|Character Set|
|-|-|-|-|-|-|-|
|01|`0000`|`0000`|Kana||Japanese|![17](../Images/17.png)|
|02|`0001`|`1000`|GenDon 3 6A|[link](https://forum.vcfed.org/index.php?threads/gendon3-improved-character-generator-for-the-model-i-discussion.59498/)|No mod is needed! (modified to fit)|![18](../Images/18.png)|
|03|`0010`|`0100`|GenDon 3 9E|[link](https://forum.vcfed.org/index.php?threads/gendon3-improved-character-generator-for-the-model-i-discussion.59498/)|No mod is needed! (modified to fit)|![19](../Images/19.png)|
|04|`0011`|`1100`|GenDon 3 -61|[link](https://forum.vcfed.org/index.php?threads/gendon3-improved-character-generator-for-the-model-i-discussion.59498/)|No mod is needed! (modified to fit)|![20](../Images/20.png)|
|05|`0100`|`0010`|Set All|RetroStack|Noise check; Debugging Set|![21](../Images/21.png)|
|06|`0101`|`1010`|Blank|RetroStack|Noise check; Debugging Set|![22](../Images/22.png)|
|07|`0110`|`0110`|Cross|RetroStack|Alignment check; Debugging Set|![23](../Images/23.png)|
|08|`0111`|`1110`|Xs|RetroStack|Distortion check; Debugging Set|![24](../Images/24.png)|
|09|`1000`|`0001`|Hitachi HD44780U|Datasheet|LCD Display (modified to fit)|![25](../Images/25.png)|
|10|`1001`|`1001`|Mullard SAA5050|Datasheet|Teletext (modified to fit)|![26](../Images/26.png)|
|11|`1010`|`0101`|Signetics 2513|Datasheet|Used in Apple I (modified to fit)|![27](../Images/27.png)|
|12|`1011`|`1101`|Motorola MC4847|Datasheet|(modified to fit)|![28](../Images/28.png)|
|13|`1100`|`0011`|Cyber|[link](http://www.6502.org/users/sjgray/computer/cbmchr/cbmchr.html)|(modified to fit)|![29](../Images/29.png)|
|14|`1101`|`1011`|Sinclair Spectrum|?|(modified to fit)|![30](../Images/30.png)|
|15|`1110`|`0111`|Original First Inverted|RetroStack|Just a filler!||
|16|`1111`|`1111`|Original Final Inverted|RetroStack|Just a filler!||
