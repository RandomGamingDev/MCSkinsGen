# MCSkinsGen
A repository for a Minecraft skin generator based off of Stable Diffusion v1.5. It's trained off of Stable Diffusion and uses data scraped with https://github.com/RandomGamingDev/mcskins-net-scraper

 📊 **Skin Generator**:  [![Open in Colab](https://raw.githubusercontent.com/hollowstrawberry/kohya-colab/main/assets/colab-badge.svg)](https://colab.research.google.com/github/RandomGamingDev/MCSkinsGen/blob/main/MCSkinGen.ipynb) <br/>
 ⭐ **Model Trainer**: [![Open in Colab](https://raw.githubusercontent.com/hollowstrawberry/kohya-colab/main/assets/colab-badge.svg)](https://colab.research.google.com/github/RandomGamingDev/MCSkinsGen/blob/main/MCSkinGenTrainer.ipynb)

This is prototype 2 and is based off of Stable Diffusion.

Why Stable Diffusion? While a smaller GAN may be more efficient, if we even got to a fraction of utilizing the abilities of Stable Diffusion, that means that we don't have to do nearly as much work with characters that are less well known if we can get the model to learn how to make pixel art of the characters its seen before.
However, I might try using a smaller custom model in the future for efficiency.

First, we scrape the data with https://github.com/RandomGamingDev/mcskins-net-scraper before using `to-imagefolder.py` and `to-1dir-dataset.py` to convert it into a form that can be used and with a 512x512 resolution for each skin and train it with the default LoRA model.
With the finished models, we can then generate skins that we then proceed to resize back to 64x64 with Pillow before exporting.

I've trained up to epoch 18, but I haven't had enough computing power to train past that (Google Colab does a funni and kicks me off and I don't have a GPU powerful enough to train the AI)

The model will try to follow the prompt, but currently does so very very loosely if at all in a lot of cases.
