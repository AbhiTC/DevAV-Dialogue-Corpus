
# A Dynamic Goal Adapted Task Oriented Dialogue Agent

The primary task of any goal-oriented dialogue agent is to accomplish a user's task with utmost user satisfaction. Existing virtual agents assume that the end-user will always have a predefined task goal, which will be served after filling the corresponding intent and slots. However, in real-life, users do not always have a generic pre-known task goal, i.e., they determine their precise task goal dynamically based on their utility value and the agent's serving capability. They may upgrade/downgrade/update their goal components in real-time to maximize their utility value. This assumption emphasizes the gap between real human assistance and virtual agent assistance, where users have a flexible goal to maximize their utility. This work attempts to develop a dialogue agent that can deal with dynamically changing user goals; Goal driven module (GDM) has been incorporated with the dialog manager (DM) to track user goals and update them accordingly. A Dynamic Goal Driven Dialogue Agent (DGDVA) has been developed by incorporating a Dynamic Goal Driven Module (GDM) on top of a deep reinforcement learning based dialogue manager. In the course of a conversation, the user sentiment provides grounded feedback about agent behavior, including goal serving action. Please see the ReadeMe for more details.

Data:  Deviation adapted Virtual Agent (DevAV) Dialogue-Corpus
    
      Conversational Dialogue Corpus featured with Dynamic Task Goal.  
      Domain : Sales Domain, Annotated Tag : Intent Slot and User Sentiment 



The proposed system contains three sub-modules namely : \
					**1) Natural Language Understanding (NLU)** \
					**2) Dynamic Goal adapted Dialogue Manager (DM)** \
					**3) Natural Langauage Generator (NLG)** 

The pipline structure is as follows : (User Response) NLU --> DM --> NLG (Agent Response)



The dialogue corpus (DevVA) contains a total of 1000 dialogues (25 sample conversations + 975 grounded dialogue conversations). It includes a total of 8335 utterances, seven categories, and 18 slots. We have utilized a subset of GSMAreana [2] as the knowledge base for the corpus creation, which contains 2697 unique phone samples and 18 attributes (slots).


**1)** In NLU, there are two sub-modules named a) Intent and Slot tagger and b )Sentiment classifier for predicting users response schematic.
    - Intent and Slot tagger: We have utilized the joint BERT Model [1] as our IC/STM module, which achieves the accuracy of 93.11% and 87.39% for intent and slot, respectively. \
    - We experimented with different models such as LSTM, BiLSTM, pre-trained BERT, and pre-trained XLNet, and found that the XLNet is performing best (accuracy - 96.68%) among these models. So, we integrated the pre-trained XLNet fine-tuned on the corpus (DevVA) as the Sentiment Classieir (SC) module.

**2)** Dynamic Goal adapted Dialogue Manager (DM): DM consists of mainly two layers: i) Goal Manager and ii) Dialogue Policy Learner. Goal Manager (GM) tracks discrepancy (goal deviation) for the current dialogue state and formulates a new goal as the observed discrepancy and dialogue state. The dialogue policy with architecture as Fig 4 is optimized using a Reinforcement learning algorithm (DQN). Also, the training loop has been shown in Fig 7. For more details, please see the paper and the GDM Incorporated DPL algorithm.

**3)** For NLG, the proposed system utilizes a template-based NLG system with an average of 4 response templates per action.


### Citation 

      Details will be provided soon.

### For more deatails, please contact: 

    abhisektiwari2014@gmail.com
    
### References :

1. Bert for joint intent classification and slot filling 2019 https://arxiv.org/abs/1902.10909
2. Baichoo A. Kaggle GSMArean; 2017 https://www.kaggle.com/arwinneil/gsmarena-phone-dataset

