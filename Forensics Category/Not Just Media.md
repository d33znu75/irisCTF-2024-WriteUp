### > Not Just Media challenge :

![](https://media.discordapp.net/attachments/1067452256686981161/1194028269813633124/Screen_Shot_2024-01-08_at_10.20.24_PM.png?ex=65ef75fb&is=65dd00fb&hm=42b1eff44a876ed14c16cbf0c9abce09386ccdbb69fa8a35282598607104c62b&=&format=webp&quality=lossless&width=2588&height=390)

In this challenge, they provided us with an MKV video containing Chinese subtitles.

![](https://media.discordapp.net/attachments/1067452256686981161/1194029217239797830/Screen_Shot_2024-01-08_at_10.25.35_PM.png?ex=6601ebdd&is=65ef76dd&hm=40b744a3ce4ee458e3ba7a5d7ea79376f8227f367eb59c39df0825c57ac18ee8&=&format=webp&quality=lossless&width=1100&height=668)

since its .mkv i used the MKVToolNix in linux

executing mkvinfo

> mkvinfo chal.mkv

I discovered three attachments accompanying the video: font files (.ttf). One of them is named 'Fake_Font'.

![](https://media.discordapp.net/attachments/1067452256686981161/1194031366225010818/Screen_Shot_2024-01-08_at_10.30.25_PM.png?ex=6601eddd&is=65ef78dd&hm=f482aca8dac9dce429ac9dfc5324526641644b5608142786b2ab3f8166327f57&=&format=webp&quality=lossless&width=2016&height=1396)

I extracted the Fake_Font

> mkvextract attachments chal.mkv 1:FakeFont_0.ttf

Then i extracted the subtitles to get the Chinese text

> mkvextract "chal.mkv" tracks 2:subtitles.srt
> cat subtitles.srt

![](https://media.discordapp.net/attachments/1067452256686981161/1194036230275469362/Screen_Shot_2024-01-08_at_10.51.58_PM.png?ex=6601f265&is=65ef7d65&hm=ff3847b99e08c2874cfb7cf803f6ce01e811987c50571b0da420c88d05be5408&=&format=webp&quality=lossless&width=2588&height=1244)

> 我們歡迎您接受一生中最大的挑戰，即嘗試理解這段文字的含義

then we used photoshop to apply the Fake_Font to the Chinese text but you can use any text editor that has font tools:

![](https://cdn.discordapp.com/attachments/1067452256686981161/1194041135274922128/Screen_Shot_2024-01-08_at_11.13.00_PM.png?ex=65ef81f6&is=65dd0cf6&hm=f2a6824cd372afbb3989b6ee588ec8bd80f8f8f9b3b42a8dea110893f577b82e&)

FLAG : 
> irisctf{mkvm3rg3_my_b3l0v3d}
