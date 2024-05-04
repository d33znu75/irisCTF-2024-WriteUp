### > Not Just Media challenge :

![](https://cdn.discordapp.xyz/attachments/1067452256686981161/1194028269813633124/Screen_Shot_2024-01-08_at_10.20.24_PM.png)

In this challenge, they provided us with an MKV video containing Chinese subtitles.

![](https://cdn.discordapp.xyz/attachments/1067452256686981161/1194029217239797830/Screen_Shot_2024-01-08_at_10.25.35_PM.png)

since its .mkv i used the MKVToolNix in linux

executing mkvinfo

> mkvinfo chal.mkv

I discovered three attachments accompanying the video: font files (.ttf). One of them is named 'Fake_Font'.

![](https://cdn.discordapp.xyz/attachments/1067452256686981161/1194031366225010818/Screen_Shot_2024-01-08_at_10.30.25_PM.png)

I extracted the Fake_Font

> mkvextract attachments chal.mkv 1:FakeFont_0.ttf

Then i extracted the subtitles to get the Chinese text

> mkvextract "chal.mkv" tracks 2:subtitles.srt
> cat subtitles.srt

![](https://cdn.discordapp.xyz/attachments/1067452256686981161/1194036230275469362/Screen_Shot_2024-01-08_at_10.51.58_PM.png)

> 我們歡迎您接受一生中最大的挑戰，即嘗試理解這段文字的含義

then we used photoshop to apply the Fake_Font to the Chinese text but you can use any text editor that has font tools:

![](https://cdn.discordapp.xyz/attachments/1067452256686981161/1194041135274922128/Screen_Shot_2024-01-08_at_11.13.00_PM.png)

FLAG : 
> irisctf{mkvm3rg3_my_b3l0v3d}
