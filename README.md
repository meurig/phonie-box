# phonie-box
My implementation of the PhonieBox project on raspberry pi nano

## Hardware
### Components
#### Raspberry Pi
I started with a raspberry pi zero w, but I'm planning to upgrade to a raspberry pi zero 2 as it's faster and should give a better experience. The zero 1 w is working though.
[Raspberry Pi Zero 2 W](https://cpc.farnell.com/raspberry-pi/rpi-zero-w-v2/raspberry-pi-zero-w-v2/dp/SC19061)

#### Audio Amp
As the zero doesn't have a sound card, you need some hardware to get sounds out. I settled on a combined DAC and Amp that could drive speakers directly:
[HiFiBerry MiniAmp](https://cpc.farnell.com/hifiberry/4260439550415/miniamp-phat-format-amplifier/dp/SC14717)

#### Speakers
These [3W speakers](https://www.aliexpress.com/item/32589319707.html) are awful, don't use them.
I've ordered some [Kenwood JVC CS J420X\*](https://www.amazon.co.uk/dp/B00JHERC8I?psc=1&linkCode=ll1&tag=localleaves-21&linkId=562f84e8cc8c27d8721a36e34d902123&language=en_GB&ref_=as_li_ss_tl) instead as the case I'm planning to use was designed around them.

#### RFid Reader
RFID-RC522 (as I had one in my parts drawer)

#### RFID Tags
I'm going to try [these stickers\*](https://www.amazon.co.uk/dp/B0CN9CW9CK?psc=1&linkCode=ll1&tag=localleaves-21&linkId=cd778b395062dee679f12e4bf6c2fea6&language=en_GB&ref_=as_li_ss_tl) as they're cheap and cheerful, but are as yet untested.
#### Buttons
These [12mm momentary push button switches\*](https://www.amazon.co.uk/gp/product/B0B3QYVMVF?ie=UTF8&psc=1&linkCode=ll1&tag=localleaves-21&linkId=d32da4ed488852a598f6d1f40f094362&language=en_GB&ref_=as_li_ss_tl) are again what the case I'm planning to print is based on. I think I'll only need 5.

#### Screen
[1.3" I2C OLED 128x64\*](https://www.amazon.co.uk/gp/product/B09Z29QDQL?ie=UTF8&psc=1&linkCode=ll1&tag=localleaves-21&linkId=fd5c2566f4397acb63ac6d779fdc8010&language=en_GB&ref_=as_li_ss_tl) not necessary, but I'm going to give it a go.

#### Case
 have a 3D printer so I'll start with [this one by Doblist](https://www.printables.com/model/461626-phoniebox-jukebox-for-the-raspberry-pi-playing-aud/comments) as it looks reminiscient of the TonieBox.

#### Power Supply
I'm currently using an official 2.5A 5V raspberry pi power supply, but this may change.

#### Power Bank
TBD.

#### On Off Switch
[Pimoroni OnOff SHIM for Raspberry Pi](https://coolcomponents.co.uk/products/onoff-shim-for-raspberry-pi-all-models)
I'm currently powering down by running `sudo shutdown now` over ssh and powering back up by unplugging the replugging the power cable. I'm hoping this shim will make it more convenient.

#### SD Card
I'm using a [Sandisk Ultra micro SD Card\*](https://www.amazon.co.uk/SanDisk-Ultra-microSDHC-Adapter-120MB/dp/B08HYF3M3L?crid=267S01HCRG5O4&keywords=sd+card+sandisk+ultra+32GB+micro&qid=1704373684&sprefix=sd+card+sandisk+ultra+32gb+micro%2Caps%2C93&sr=8-10&linkCode=ll1&tag=localleaves-21&linkId=a77c289809a27cfb38eb3a4323560762&language=en_GB&ref_=as_li_ss_tl) but any fast card with decent space should work. I've yet to test one larger than 32GB, but it should be fine.

#### Misc others
- jumper cables
- screws
- SD Card adapter
- USB cables

### How to Assemble
ToDo: currently it's a mass of wires on my desk, but I have a working prototype.
If you're not going to mount your miniamp directly onto the pi, this page is useful to know which pins are needed using jumper cables: [https://sites.google.com/site/cartwrightraspberrypiprojects/home/steps/hifiberry-miniamp]
[pi zero pinout](https://i.stack.imgur.com/yHddo.png)

## Software
### Operating System


### Phonie Box Project
ihttps://github.com/MiczFlor/RPi-Jukebox-RFID
### How to Configure
#### RFID Reader
#### MiniAmp audio out
[https://www.hifiberry.com/docs/hardware/gpio-usage-of-hifiberry-boards/#:~:text=HiFiBerry%20MiniAmp,shuts%20down%20the%20power%20stage.]
[https://www.hifiberry.com/docs/software/configuring-linux-3-18-x/]
[https://github.com/MiczFlor/RPi-Jukebox-RFID/discussions/1073#discussioncomment-211533]

## Getting hold of Content

### Music
#### YouTube to MP3
I've used [4K YouTube to MP3](https://www.4kdownload.com/products/youtubetomp3-72) to pull down some non copyrighted music from YouTube on windows. The starter plan is free and allows 15 downloads per day.

#### Streaming YouTube Music
This is currently not supported afaik, but this project and it's recent MRs suggest it could be:


### Audio Books
#### Audible
Audible was the cheapest for the book I was trying to get, but they would not give me an MP3, only a DRM enabled AAC file.
[Pippi Longstockings \*](https://www.amazon.co.uk/hz/audible/mlp/mfpdp/ASIN?actionCode=AMN30DFT1Bk06604291990WX&tag=AssociateTrackingID) was £2.62 when I bought it. You can also get it for free if you start a free trial.

You can download the AAC from audible.co.uk.

Do not use OpenAudible to download the AAC as it corrupts the file's metadata making it unable to work with InAudible. They also played dirty by [taking open source code and making a closed source for porfit tool using it](https://github.com/inAudible-NG/audible-activator?tab=readme-ov-file#audible-activator). I don't like their tactics, including not making it obvious that you can't actually get mp3s without paying for the product, so I don't use it, but I believe it does work.

#### InAudible
To get around the audible DRM I use [InAudible](https://github.com/rmcrackan/inAudible). It can take an audible AAC and, depending on your settings, can spit out and mp3 per chapter - nice.

## How to Use
[http://192.168.86.29/index.php]

## Useful Links
These are mostly other people's implementations, but I leaned heavily on them to build mine!
[https://splittscheid.de/phoniebox-bauanleitung-toniebox-alternative/#5_3]
[https://gt-blog.de/toniebox-hacking-how-to-get-started/]

