#### Monday, December 18, 2023

Today, I am going to uninstall Haystack 1.0. and install Haystack 2.0. ... I want to try running  [Guide to Using Zephyr Models to Generate Answers on Your Data](https://haystack.deepset.ai/blog/guide-to-using-zephyr-with-haystack2)

#### Saturday, December 16, 2023

Definitely some confusion about which version of Haystack to install.

I began with running 'pip install farm-haystack[inference]' which immediately did not work in the 'haystack2_zephyr_beta.ipynb' notebook, which, when I looked, requested I install 'pip install haystack-ai' which is tagged with 'You are currently looking at the readme of Haystack 2.0-Beta, an unstable version of what will eventually become Haystack 2.0.' This notebook worked, but looking at https://haystack.deepset.ai/tutorials these request a different install. Some request 'pip install farm-haystack[colab]', others request 'pip install farm-haystack[inference]', others 'pip install farm-haystack[colab,inference]'

So rather than expecting 'one install to fit them all' I think I will just install 'pip install farm-haystack' and see what happens. But first, I will uninstall what I have using 'pip uninstall haystack-ai'

And now I will attempt to go through the Beginner tutorials that do NOT use OpenaI. 

[Tutorial: Build Your First Question Answering System](https://haystack.deepset.ai/tutorials/01_basic_qa_pipeline)



