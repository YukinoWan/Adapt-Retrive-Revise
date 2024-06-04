This repository is for the paper "[Reformulating Domain Adaptation of Large Language Models as Adapt-Retrieve-Revise
](https://arxiv.org/abs/2310.03328)".



## Pretraining Data Format Example

{"text": "为一本关于被红眼生物诅咒的家族的恐怖小说生成一个引人入胜且独特的标题。"}
{"text": "这个算法的工作原理是循环遍历数组中的每个元素，找到它后面所有未排序元素中的最小值"}

During the pretraining, we collect the training data from the following two open Chinese legal sources:

- [Chinese Law Clauses](https://flk.npc.gov.cn/): the foundation of the judicial system, containing a wealth of legal terms, provisions, and judicial practices. They are essential for the model to understand and generate relevant content.
- [Chinese Judgments Online](https://wenshu.court.gov.cn/): the largest online publication platform for legal documents in China. The platform contains judicial documents from courts at all levels, covering various legal fields such as civil, criminal, administrative, and enforcement. Such documents contain knowledge for LLMs to understand the usage of laws in various scenarios.

We utilize the general domain [Baichuan 7B model](https://huggingface.co/baichuan-inc/Baichuan-7B) for continual learning Chinese legal corpora. In total, we trained 50B tokens of Chinese Law Clauses and Chinese Judgments Online corpora with the input length limit of 16K and the batch size of 256 on 32 A100 GPUs, and the time-consuming is 167 hours.

## SFT Data Format Example

{"text": "\n\nHuman: 为一本关于被红眼生物诅咒的家族的恐怖小说生成一个引人入胜且独特的标题。\n\nAssistant: 《鬼怪之眼：被诅咒的血脉》"}
{"text": "\n\nHuman: 用“勇气”、“诱惑”和“命运”这三个词写一首诗。\n\nAssistant: 雄心壮志，奋发有为，\n勇气汇聚心间，\n勇往直前。。。"}




