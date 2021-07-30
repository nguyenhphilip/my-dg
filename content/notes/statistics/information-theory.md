---
title: information theory
---

*The* mathematical theory of communication developed by Claude Shannon

# What made it so impactful?

Idea of channel limits $C_t = W\log_{2}\frac{P+N}{N}$. Every communication channel has a speed limit, measured in binary digits per second. Above the limit it is mathemtically impossible to send an error-free message (i.e. loss of information when you go above the channel speed limit). 

But below the limit, it is always possible to transmit a message with zero error, regardless of noise or how weak the signal is.

The **noisy channel coding theorem** is what gave rise to channel coding theory: essentially it is concerned with how to encode messages (e.g. adding redundency) in a way that prevents corruption of information. (E.G. CDs that get scratched can still transmit perfectly, thanks to noisy channel coding).

Shannon also introduced a formal architecture for communication systems

![Pasted image 20210323083911.png](/notes/images/20210323083911.png)

In this architecture one can treat each component separately and independently.

Shannon also unified information transmission with the idea of a bit. He recognized that the content of the message was irrelevant to the channel: it was 1s and 0s to the channel. Once data was represented digitally, it could be reproduced and transmitted without error. This unified many fields concerned with the communication of some message, e.g. audio, telegraphy, images, film.