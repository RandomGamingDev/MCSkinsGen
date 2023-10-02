# MCSkinsGen
A repository for prototype 2 of a Minecraft skin generator based off of Stable Diffusion v1.5. It's trained off of Stable Diffusion and uses data scraped with https://github.com/RandomGamingDev/mcskins-net-scraper.

## This model generates actual skins that can be imported and used in Minecraft

 📊 **Skin Generator**:  [![Open in Colab](https://raw.githubusercontent.com/hollowstrawberry/kohya-colab/main/assets/colab-badge.svg)](https://colab.research.google.com/github/RandomGamingDev/MCSkinsGen/blob/main/MCSkinGen.ipynb) <br/>
 ⭐ **Model Trainer**: [![Open in Colab](https://raw.githubusercontent.com/hollowstrawberry/kohya-colab/main/assets/colab-badge.svg)](https://colab.research.google.com/github/RandomGamingDev/MCSkinsGen/blob/main/MCSkinGenTrainer.ipynb)

## Here are some example skins that I liked (Note: The model will try to follow the prompt, but currently does so very very loosely if at all in a lot of cases.): <br/>

This skin was generated with the name "Alchemist", the "movies" category, and with the "Alchemist with golden hair" description. <br/>
![alt text](https://github.com/RandomGamingDev/MCSkinsGen/blob/main/imgs/demoSkin3.png) <br/>
I forgot the prompt for these, but honestly I like em so they go on the front page :D <br/>
![alt text](https://github.com/RandomGamingDev/MCSkinsGen/blob/main/imgs/demoSkin1.png)
![alt text](https://github.com/RandomGamingDev/MCSkinsGen/blob/main/imgs/demoSkin2.png)

Note: Only the Skin Generator itself can be used on the Google Colab free tier

Why Stable Diffusion? While a smaller GAN may be more efficient, if we even got to a fraction of utilizing the abilities of Stable Diffusion, that means that we don't have to do nearly as much work with characters that are less well known if we can get the model to learn how to make pixel art of the characters its seen before.
However, I might try using a smaller custom model in the future for efficiency.

First, we scrape the data with https://github.com/RandomGamingDev/mcskins-net-scraper before using `to-imagefolder.py` and `to-1dir-dataset.py` to convert it into a form that can be used and with a 512x512 resolution for each skin before placing it into `Loras/mcskins/dataset` and train it with the default LoRA model. (This requires Google Colab Compute units since Google doesn't let you do it with the free tier)
With the finished models, we can then generate skins that we then proceed to resize back to 64x64 with Pillow before exporting. (This can be done on the free tier)

I've trained up to epoch 18, but I haven't had enough computing power to train past that (Google Colab does a funni and kicks me off and I don't have a GPU powerful enough to train the AI)
