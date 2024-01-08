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
