# irisCTF 2024 Write Up
My Write-Ups for challenges I solved in irisCTF 2024

# Miscellaneous Category:

### > Sir Scope challenge :

![App Screenshot](https://cdn.discordapp.com/attachments/1067452256686981161/1194017381782126764/Screen_Shot_2024-01-08_at_9.28.43_PM.png?ex=65aed257&is=659c5d57&hm=ee50aeaa38c5bd9dcb989de315ffb844e05eef3cfea245296d4f33156eab8efb&)

in this challenge, they gave us Screenshots of [oscilloscope](https://en.wikipedia.org/wiki/Oscilloscope).

![App Screenshot](https://cdn.discordapp.com/attachments/1067452256686981161/1194017381421432952/chal1.jpeg?ex=65aed257&is=659c5d57&hm=09243f110dcec1bccdb0b1d0805aafc90c0332b7a0d78382566285997813ed9e&)

in the challenge description, they told us they wrote the flag using an array of 8 LEDs, hmm... 8 LEDs so basically in binary.
I'm unfamiliar with oscilloscopes, but after examining the screenshot, I observed that in the blue line, every group of eight dots appears to be separated, indicating potentially eight LEDs. Each corresponding dot in the yellow line represents a single value, either 0 or 1.

![App Screenshot](https://cdn.discordapp.com/attachments/1067452256686981161/1194024623478677574/capture_0.jpeg?ex=65aed916&is=659c6416&hm=5dc86359aeb9ac97eb394b7ec987c2e3e174dd11267a934ea48d9ac59a72c4f5&)

Starting from right to left, in the first group, I have "01101001" which when transformed to ASCII gives me "i" the first letter in the flag format "irisctf".

Continuing this with all the remaining elements, I obtained:

"01101001 01110010 01101001 01110011 01100011 01110100 01100110 01111011 00110000 01110011 01100011 00110001 01101100 01101100 01101111 01110011 01100011 00110000 01110000 01100101 01110011 01011111 01110010 01011111 01100111 01110010 00111000 01011111 01110100 00110000 00110000 01101100 01110011 01011111 00110010 01011111 01101000 01100001 01110110 00110011 01111101"

To ASCII : 
> irisctf{0sc1llosc0pes_r_gr8_t00ls_2_hav3}

# Forensics Category:

### > Not Just Media challenge :

![App Screenshot](https://cdn.discordapp.com/attachments/1067452256686981161/1194028269813633124/Screen_Shot_2024-01-08_at_10.20.24_PM.png?ex=65aedc7b&is=659c677b&hm=366a0cda43e386b581263250a5ec24ceed1758564007fc00d0a7531c24d4ae55&)

In this challenge, they provided us with an MKV video containing Chinese subtitles.

![App Screenshot](https://cdn.discordapp.com/attachments/1067452256686981161/1194029217239797830/Screen_Shot_2024-01-08_at_10.25.35_PM.png?ex=65aedd5d&is=659c685d&hm=c6c3a66cc7422a3fb78c979fce318997bd6ffc16622c358f569ebb2ba1f34e5d&)

since its .mkv i used the MKVToolNix in linux

executing mkvinfo

> mkvinfo chal.mkv

I discovered three attachments accompanying the video: font files (.ttf). One of them is named 'Fake_Font'.

![App Screenshot](https://cdn.discordapp.com/attachments/1067452256686981161/1194031366225010818/Screen_Shot_2024-01-08_at_10.30.25_PM.png?ex=65aedf5d&is=659c6a5d&hm=2bb3d65af2273a3d6638e365ddd27f4a7b95c5332b831cc2c5cb0c7aaf5e48ef&)

I extracted the Fake_Font

> mkvextract attachments chal.mkv 1:FakeFont_0.ttf

Then i extracted the subtitles to get the Chinese text

> mkvextract "chal.mkv" tracks 2:subtitles.srt
> cat subtitles.srt

![App Screenshot](https://cdn.discordapp.com/attachments/1067452256686981161/1194036230275469362/Screen_Shot_2024-01-08_at_10.51.58_PM.png?ex=65aee3e5&is=659c6ee5&hm=74c3ec84bdd4cfed82522c28a906776a62f65152417137d9a8c669f5b41bc9db&)

> 我們歡迎您接受一生中最大的挑戰，即嘗試理解這段文字的含義

then we used photoshop to apply the Fake_Font to the Chinese text but you can use any text editor that has font tools:

![App Screenshot](https://cdn.discordapp.com/attachments/1067452256686981161/1194041135274922128/Screen_Shot_2024-01-08_at_11.13.00_PM.png?ex=65aee876&is=659c7376&hm=fbf8ffc04df76615420e0aa8f59e97bef4e103cd65c5a76dc72647fcf7728f41&)

FLAG : 
> irisctf{mkvm3rg3_my_b3l0v3d}

---------------------------------------------

### > What the Beep? challenge :

![App Screenshot](https://cdn.discordapp.com/attachments/1067452256686981161/1194042461362851986/Screen_Shot_2024-01-08_at_11.16.14_PM.png?ex=65aee9b3&is=659c74b3&hm=3cb96dc4ff933063e4569420f1d8803674d2ad3d7253e9b305fccb845066c3e9&)

In this challenge, we were provided with four HTML documents containing audio waves recorded from four different locations surrounding the area where the original sound was streamed.

Initially, I labeled the coordinates of the recordings on Google Maps.



![](https://cdn.discordapp.com/attachments/1067452256686981161/1194044410271367290/New_Project.png?ex=65aeeb83&is=659c7683&hm=5e15aee1a635fa55f1bcbcb7c4ad46ede37e2a1a9130ae1f8f92a16e80121ec6&)

![](https://cdn.discordapp.com/attachments/1067452256686981161/1194047603218853946/Screen_Shot_2024-01-08_at_11.32.17_PM_1.png?ex=65aeee7c&is=659c797c&hm=36ba1887bb0bd67f17e5fa49a746656aa0fa598604ed2d1edc7dc5e49ed4a4cb&)

As there were two positions with the same decibel level, I drew two circles from those points to determine the midpoint between them.

![](https://cdn.discordapp.com/attachments/1067452256686981161/1194051448061821060/Screen_Shot_2024-01-08_at_11.32.17_PM_2.png?ex=65aef211&is=659c7d11&hm=a418bb1b76181085d57bb0f144e48caf463f1c83ee2894691d269e2ccb778e68&)

Now, we have three defined areas, one of which is the source of the sound (either to the north of the meeting point, the south, or the meeting point itself). Upon analysis, we observed that the northern point exhibited approximately 57 dB, indicating its proximity to the source. This proximity led me to draw the white circle in the northern area.

Now, focusing on the white circle, I noticed a house positioned in the center of this area.

![](https://cdn.discordapp.com/attachments/1067452256686981161/1194052870211899472/Screen_Shot_2024-01-08_at_11.32.17_PM_3.png?ex=65aef364&is=659c7e64&hm=43b1e3ade00def6b90864e5f30b1233a12aa8465eb7e400ac63dbbef07f58878&)

Let's proceed by checking the checker for these coordinates.

![](https://cdn.discordapp.com/attachments/1067452256686981161/1194055383803777184/Screen_Shot_2024-01-09_at_12.09.01_AM.png?ex=65aef5bb&is=659c80bb&hm=75db27b50c111ccc632575b686ca4a3957ed6a20ce56ef0853465727a52c2de8&)

That's it 

> irisctf{ac0ust1c_pr0pagat10n_m0d3ls_c4n_b3_us3d_t0_appr0xim4te_d1st4nce5}
