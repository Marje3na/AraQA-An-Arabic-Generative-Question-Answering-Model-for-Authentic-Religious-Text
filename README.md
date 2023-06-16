# Religious-Text-Analysis-and-ChatBot-Using-Transformer-Based-Models
[![078f0074fd7a58db4ea4a0e94efa3c5d.png](https://i.postimg.cc/1tysbx6S/078f0074fd7a58db4ea4a0e94efa3c5d.png)](https://postimg.cc/GBgWs5qg)
## Abstract
Nowadays, the internet is filled with misleading fatwas and the Muslim who really searching for the true information which is based on the Quran or on the Hadith of Prophet Mohamed is in a problem, he/she has to search about who gave the fatwa and to check the validity of the Hadith that the Sheikh relied on in his fatwa.<br>
<br>
In ‘مرجعنا’, we will make a GPT2 bot that can give a reliable and valid fatwa. We will use transformers (GPT2) for the bot to give fatwa because we need it to give
“human-like” responses. The model will be mainly and initially trained on islamweb.net fatwas, it is a famous and valid source where any fatwa is given by a knowledgeable and reliable Sheikh with the Quran and trusted Hadith. The bot is going to be initially in Arabic language only.

## Methodology
In this project, we used islamweb.net data that we scraped as we mentioned in the Abstract section.<br>
The Scraped Data: https://www.kaggle.com/datasets/abdallahelsaadany/fatawa <br>
<br>
Our Methodology Consist of 3 Main Sections:<br>
<br>
**Section 1: Data Cleaning & Prepocessing and Feature Engineering**<br>
<br>
1- Clean the data from NULL values, irrelevant text, and text that contains a reference that cannot be accessed.<br>
2- Concatenate the question/title with the answer in one single column.<br>
<br>
After all the data cleaning we end up with 40,859 data-points (pair of question and answer), for computational cost reasons, we only select the first 20,000 data-point, 90% for training and 10% for validation.<br>
<br>
**Section 2: Model Fine-Tuning and Testing**<br>
<br>
ARAGPT2-Base used in this project inherited the GPT2's architecture with 12 heads and 12 layers, as illustrated in the figure below.<br>

[![1-Ji79b-Z3-Kqp-MAj-Z9-Txv4q8-Q.png](https://i.postimg.cc/fWtB187t/1-Ji79b-Z3-Kqp-MAj-Z9-Txv4q8-Q.png)](https://postimg.cc/Z0m8dFM4)
<br>
<br>
<br>
1- Special token added for the pre-trained tokenizer (<question:>, <answer:>) to let the model understand which part is the question and which part is the answer.<br>
2- Fine-tune the pre-trained model ARAGPT-Base (by aubmindlab).
<br>
<br>
**Section 3: Results & Testing and Deployment**<br>
<br>

### *Results & Testing*
Training Loss before adding the special tokens: **4.9**<br>
<br>
Training Loss after adding the special tokens: **1.9**<br>
Validation Loss: **2.6**<br>
<br>
Perplexity Measure on the hold-out-test-set (15 unseen questions): **2.3**
<br>
<br>

![image](https://github.com/Marje3na/Religious-Text-Analysis-and-ChatBot-Using-Transformer-Based-Models/assets/67977986/f3dcfbff-521e-491a-8948-06c6569eb3f8)
<br>
<br>
<br>
### *Deployment*
Deploy the model using 'gradio' library. As shown in the figure below, the user asks a question, the answer then appears on the right side of the web-page in a text box. the maximum length of a text that the model can generate is set to 300.<br>
[![Screenshot-80.png](https://i.postimg.cc/bvQfpzfM/Screenshot-80.png)](https://postimg.cc/8FP0bg5B)<br>
<br>
<br>
## Citations
The model fine-tuned in this project: https://huggingface.co/aubmindlab/aragpt2-base<br>
<br>
***Disclaimer***: THE MODELS GENERATED ANSWERS ARE NOT RELIABLE AT ALL YET, AND THE MODEL IS NOT YET AVAILABLE FOR PUBLIC USE, USE FOR RESEARCH PURPOSES ONLY.
