# MCSkinsGen
A repository for prototype 2 of a Minecraft skin generator based off of Stable Diffusion v1.5. It's trained off of Stable Diffusion and uses data scraped with https://github.com/RandomGamingDev/mcskins-net-scraper. <br/>
This is the current most permissive model (in terms of license) and is one of the most powerful (I can't be sure whether or not it's the most powerful since I don't have access to some of the competitors or simply can't run them)

## Our Discord :D &nbsp;&nbsp;&nbsp; ![Discord Stats](https://img.shields.io/discord/1158518768067166338.svg?style=for-the-badge) <br/>
https://discord.gg/APdcNPMvR3

## Youtube (basically a vid explaining the AI and how to use it) (preferable to the text tutorial if you don't have experience with this sorta stuff)
https://www.youtube.com/watch?v=Zhug5-smQ8g

## Here are the Colab Notebooks for the models (Skin Generator is for generating the skins):
### Just follow the instructions in the Google Colab for Skin Generator and this model will create skins that can be used in game!
#### (btw I recommend generating more than 2 images once you know what you want)

 📊 **Skin Generator**:  [![Open in Colab](https://raw.githubusercontent.com/hollowstrawberry/kohya-colab/main/assets/colab-badge.svg)](https://colab.research.google.com/github/RandomGamingDev/MCSkinsGen/blob/main/MCSkinGen.ipynb) (Click on the icon left of me!) <br/>
 ⭐ **Model Trainer**: [![Open in Colab](https://raw.githubusercontent.com/hollowstrawberry/kohya-colab/main/assets/colab-badge.svg)](https://colab.research.google.com/github/RandomGamingDev/MCSkinsGen/blob/main/MCSkinGenTrainer.ipynb)

## Instructions for generating a skin: (Note: You should choose the T4 GPU runtime instance especially on the free tier)
1. Click on the **Skin Generator** Google Colab link to open the notebook
2. Sign up for a Hugging Face account and then create a read key here: https://huggingface.co/settings/tokens (making the key type read is all that's needed, but write works too)
3. Press play for the first code block (it won't appear until you hover over it so that it appears between the 2 square brackets), which will install some dependencies and then present a login screen in which you'll enter the key and then enter `y` for whether or not to add it as a git credential To enter text simply press the empty space next to the `:` which will reveal an input bar that you can type in. <br/> The login screen you find at the end of the fancy install bars: <br/> ![The login screen](https://github.com/RandomGamingDev/MCSkinsGen/blob/main/imgs/login_screen.png)
5. Run the second code block
6. Run the final code block with the prompt that you want

Step 5 can be repeated for each skin you try to generate without repeating the previous steps <br/>
However, you'll need to repeat the steps when Google Colab restarts 

## Here are some example skins that I liked (Note: The model will try to follow the prompt, but currently does so very very loosely if at all in a lot of cases.): <br/>

This skin was generated with the name "Alchemist", the "movies" category, and with the "Alchemist with golden hair" description. <br/>
![alt text](https://github.com/RandomGamingDev/MCSkinsGen/blob/main/imgs/demoSkin3.png) <br/>
I forgot the prompt for these, but honestly I like em so they go on the front page :D <br/>
![alt text](https://github.com/RandomGamingDev/MCSkinsGen/blob/main/imgs/demoSkin1.png)
![alt text](https://github.com/RandomGamingDev/MCSkinsGen/blob/main/imgs/demoSkin2.png)

Note: Only the Skin Generator itself can be used on the Google Colab free tier

## Why Stable Diffusion?
While a smaller GAN may be more efficient, if we even got to a fraction of utilizing the abilities of Stable Diffusion, that means that we don't have to do nearly as much work with characters that are less well known if we can get the model to learn how to make pixel art of the characters its seen before.
However, I might try using a smaller custom model in the future for efficiency.

## How does this work?

First, we scrape the data with https://github.com/RandomGamingDev/mcskins-net-scraper before using `to-imagefolder.py` and `to-1dir-dataset.py` to convert it into a form that can be used and with a 512x512 resolution for each skin before placing it into `Loras/mcskins/dataset` and train it with the default LoRA model. (This requires Google Colab Compute units since Google doesn't let you do it with the free tier) (If you want to train based off of another LoRA or based off of the LoRAs generated from what you previously trained just place it somewhere downloadable (perhaps in a github pull request) and then place the url to it in the optional_custom_training_model_url)
With the finished models, we can then generate skins that we then proceed to resize back to 64x64 with Pillow before exporting. (This can be done on the free tier)

## Why is the model not was powerful as it could be?

I've trained up to epoch 18, but I haven't had enough computing power to train past that (Google Colab does a funni and kicks me off and I don't have a GPU powerful enough to train the AI)
