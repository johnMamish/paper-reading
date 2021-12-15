The authors construct a system consisting of an RF transmitter, a RF reciever, and some RFID tags on somone's body (Figure 9). By feeding the RSSI and phase information from these 2 tags into an LSTM network, the authors are able to discriminate between 8 different gestures (Figure 7). In order to overcome user-to-user variation in terms of motion and tag placement as well as RSSI and phase information variation due to environment variation, they include a reverse LSTM network and they train their network adversarially (although I have no idea what this means, and they don't exactly make it clear).

Hot takes:
personal interest: 4/10
Tangentially related to batteryless. Good to have it in my mental rolodex.

paper quality / novelty: 4/10
Feels like throwing deep learning spaghetti at the wall and hoping it will stick. Also, their user study seems restricted.