# LLaMa2_PlayGround

This will be my playground for all things using LLaMa2. 

Everything here will be run locally on an RTX 4090 Founders Edition card. (IKR!!)

docker container start hfpt_Oct28

## Saturday, November 4, 2023

Moved the docker images and containers folder from /home/rob/Data3/docker-data to /home/rob/Data2/docker-data ... and now disk io is just as fast as it was before. Nice! ... on /home/rob/Data3/docker-data it was much slower ... 

9:41am Pulling down 'mistralai/Mistral-7B-v0.1' because they claim to be more accurate than llama2 13b ...

[MISTRALAI_](https://mistral.ai/)

3:56pm ran a few simple tests of Mistral ...

4:31pm The QuickStart.ipynb notebook from the [FaceBook LLama Recipies](https://github.com/facebookresearch/llama-recipes/tree/main) repo cannot run by itself, it has to be run from the repo. So I am going to run this notebook from the downloaded repo, then will provide some updates to what happened here, mkay? ... ;)

## Friday, November 3, 2023

6:33am CodeHammer.ipynb Ensuring all 4 LLaMa2 huggingface models are downloaded and able to load from this container.

6:51am 'Llama 2 on a Budget.ipynb'

Damn! The above article points to a Llama 2 recipies from FaceBook Research repo found [here](https://github.com/facebookresearch/llama-recipes/tree/main). This repo contains a series of demo apps that 'show how to run Llama 2 locally and in the cloud to chat about data (PDF, DB, or live) and generate video summary.'

And for sure, I will be pulling resources from this repo into this repo to keep things in one location.

7:25am gonna bail on that 'Llama 2 on a Budget.ipynb' cuz it's paywalled and pivot to the Llama 2 recipies.

9:24am OK ... I have backed up all 4 working llama2 hf models into /home/rob/Data3/huggingface/transformers. To free up some space on that hfpt_Oct28 container, I am going to whack the 2 smaller 7b models plus the 14b non-chat model, and also kill the hfpt_Oct30 container. Then I will dry to duplicate the hfpt_Oct28 container into the hfpt_llama2 container ... brb ...

10:21am ... copied everything from /var/lib/docker to /home/rob/Data3/docker-data ...

    sudo rsync -avP /var/lib/docker /home/rob/Data3/docker-data

	sent 228,688,547,337 bytes  received 19,776,929 bytes  378,342,968.18 bytes/sec
	total size is 228,559,781,351  speedup is 1.00

Damn that was a lot of data! Spun docker back up WITHOUT changing the default location, and at the least, the hfpt_Oct28 container still works! Nice! So now will change the docker default location to /home/rob/Data3/docker-data and see if it works.

11:03am Nope! New location does not work ... sigh ... gonna whack everything currently in /home/rob/Data3/docker-data ... this drive is currently at 119gb free ... gonna run ...

sudo rm -rf /home/rob/Data3/docker-data 

Wow ... now its at 350gb free! Damn!

And once again docker spins up just fine, which is good, but yeah, I want to get this to work! Primary drive is still at 86gb free.

11:48am Gonna try [these](https://docs.docker.com/config/daemon/) directions ... they are similar to what [chatgpt](https://chat.openai.com/c/28f160f1-f1a0-4e5d-ae16-54225479b6e1) suggests and different from [this](https://linuxconfig.org/how-to-move-docker-s-default-var-lib-docker-to-another-directory-on-ubuntu-debian-linux) article which did not work for me.

///////////////////////

5:31pm So tried everything again but using the instructions found at [Docker daemon configuration overview](https://docs.docker.com/config/daemon/) and this DOES work! Great!



