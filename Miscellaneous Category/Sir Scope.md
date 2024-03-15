# Miscellaneous Category:

### > Sir Scope challenge :

![](https://media.discordapp.net/attachments/1067452256686981161/1194017381782126764/Screen_Shot_2024-01-08_at_9.28.43_PM.png?ex=65ef6bd7&is=65dcf6d7&hm=69eeac9f0875940276f99aaeb6b3350330f8abaea7661fb865a1c717bfccce70&=&format=webp&quality=lossless&width=2588&height=324)

in this challenge, they gave us Screenshots of [oscilloscope](https://en.wikipedia.org/wiki/Oscilloscope).

![](https://media.discordapp.net/attachments/1067452256686981161/1194017381421432952/chal1.jpeg?ex=6601e0d7&is=65ef6bd7&hm=b771ebbf141a85f1d2ddc046dd2d10fc3faf8bbd241fe28dc0322729a93236df&=&format=webp&width=2588&height=1146)

in the challenge description, they told us they wrote the flag using an array of 8 LEDs, hmm... 8 LEDs so basically in binary.
I'm unfamiliar with oscilloscopes, but after examining the screenshot, I observed that in the blue line, every group of eight dots appears to be separated, indicating potentially eight LEDs. Each corresponding dot in the yellow line represents a single value, either 0 or 1.

![](https://media.discordapp.net/attachments/1067452256686981161/1194024623478677574/capture_0.jpeg?ex=6601e796&is=65ef7296&hm=26bbfc7155f0110dfe67ca30bcee4cf6ce2887b9b1fa5f5a113f0f23f5f05e52&=&format=webp&width=950&height=660)

Starting from right to left, in the first group, I have "01101001" which when transformed to ASCII gives me "i" the first letter in the flag format "irisctf".

Continuing this with all the remaining elements, I obtained:

"01101001 01110010 01101001 01110011 01100011 01110100 01100110 01111011 00110000 01110011 01100011 00110001 01101100 01101100 01101111 01110011 01100011 00110000 01110000 01100101 01110011 01011111 01110010 01011111 01100111 01110010 00111000 01011111 01110100 00110000 00110000 01101100 01110011 01011111 00110010 01011111 01101000 01100001 01110110 00110011 01111101"

To ASCII : 
> irisctf{0sc1llosc0pes_r_gr8_t00ls_2_hav3}
