# Homework Submission for Session 7:

## Sambanova:
I ran the hands-on excercise with the origional flag values, saved the output log and pushed it to my GitHub here:
https://github.com/SVeldman/ai-science-training-series/blob/main/07_AITestbeds/Sambanova/bert/BertLarge_HW_compile_log_base.out

I then changed the --ntasks flag to 8 and the --ntasks-per-node to 8, saved the output log and pushed it to my GitHub here:
https://github.com/SVeldman/ai-science-training-series/blob/main/07_AITestbeds/Sambanova/bert/BertLarge_HW_compile_log_changed.out

These changes resulted in a dramatic reduction in Duration, and a model that trained much faster. I suspect that these changes did not result in a more useful model (most likely the opposite).


## Graphcore:
I first ran mnist_poptorch.py as-written. Here is a screenshot of my results:
![(Screenshot%202024-04-05%20004356%20-%20Original%20Run.jpg)](https://github.com/SVeldman/ai-science-training-series/blob/main/07_AITestbeds/Graphcore/Screenshot%202024-04-05%20004356%20-%20Original%20Run.jpg)

Next, I changed the number of epochs from 10 to 20, which produced the following results:
![(Screenshot%202024-04-05%20010744%20-%20Increased%20Epochs%20to%2020.jpg)](https://github.com/SVeldman/ai-science-training-series/blob/main/07_AITestbeds/Graphcore/Screenshot%202024-04-05%20010744%20-%20Increased%20Epochs%20to%2020.jpg)

Finally, I kept the number of epochs at 20 and decreased the learning rate from 0.03 to 0.02:
![(Screenshot%202024-04-05%20011206%20-%20Decreased%20Learning%20Rate.jpg)](https://github.com/SVeldman/ai-science-training-series/blob/main/07_AITestbeds/Graphcore/Screenshot%202024-04-05%20011206%20-%20Decreased%20Learning%20Rate.jpg)

Doubling the number of epochs increased the test set accuracy slightly (about 0.7%) by allowing the model to continue to learn. However this model was more computationally expensive and it took significantly longer to run. Reducing the learning rate also resulted in a slight improvement (0.05%), but again this came at the expense of a model that did take longer to run.


## Cerebras:
I first ran the hands-on exercise unchanged:
![(Screenshot%202024-04-07%20021234%20-%20Original%20Run.jpg)](https://github.com/SVeldman/ai-science-training-series/blob/main/07_AITestbeds/Cerebras/Screenshot%202024-04-07%20021234%20-%20Original%20Run.jpg)

I then re-ran the example with a batch size of 512:
![(Screenshot%202024-04-057%20024916%20-%20Batch%20Size%20512.jpg)](https://github.com/SVeldman/ai-science-training-series/blob/main/07_AITestbeds/Cerebras/Screenshot%202024-04-07%20024916%20-%20Batch%20Size%20512.jpg)

And re-ran it again with a batch size of 2048:
![(Screenshot%202024-04-07%20021234%20-%20Batch%20Size%202048.jpg)](https://github.com/SVeldman/ai-science-training-series/blob/main/07_AITestbeds/Cerebras/Screenshot%202024-04-07%20004356%20-%20Batch%20Size%202048.jpg)

The first run took 25 minutes (it began at 05:47:29 and finished at 06:12:26). The second run took about 24 mins (began at 06:24:42 and finished at 06:48:53). The third run took (began at 06:54:08 and finished at ).

## Groq:
I first ran the hands-on exercise with the default/dummy inputs:
![(Screenshot%202024-04-07%20002840%20-%20Original%20Run.jpg)](https://github.com/SVeldman/ai-science-training-series/blob/main/07_AITestbeds/Groq/Screenshot%202024-04-07%20002840%20-%20Original%20Run.jpg)

I then set up my own custom inputs, changing the max sequence length to 256:
![(Screenshot%202024-04-07%20004015%20-%20Custom%20Input.jpg)](https://github.com/SVeldman/ai-science-training-series/blob/main/07_AITestbeds/Groq/Screenshot%202024-04-07%20004015%20-%20Custom%20Input.jpg)

I re-ran the model and got the following results:
![(Screenshot%202024-04-07%20011349%20-%20Custom%20Input%20Results.jpg)](https://github.com/SVeldman/ai-science-training-series/blob/main/07_AITestbeds/Groq/Screenshot%202024-04-07%20011349%20-%20Custom%20Input%20Results.jpg)

The changes I made to the inputs did not have an impact on the model's accuracy, but did alter the latency and IPS metrics.