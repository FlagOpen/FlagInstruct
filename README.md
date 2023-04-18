# This is the Chinese Open Instruction Generalist project

We propose the Chinese Open Instruction Generalist (**COIG**) project to maintain a harmless, helpful, and diverse set of Chinese instruction corpora. We welcome all researchers in the community to contribute to the corpus set and collaborate with us. We only release the first chip of COIG to help the Chinese LLMs' development in the exploration stage and appeal to more researchers joining us in building COIG. We introduce a manually verified translated general instruction corpus, a manually annotated exam instruction corpus, a human value alignment instruction corpus, a multi-round counterfactual correction chat corpus, and a leetcode instruction corpus. We provide these new instruction corpora to assist the community with instruction tuning on Chinese LLMs. These instruction corpora are also template workflows for how new Chinese instruction corpora can be built and expanded effectively.

It is best to download the individual data files directly that you wish to use instead of using HF load_datasets. https://huggingface.co/datasets/BAAI/COIG/tree/main

This model card is modified from [OIG](https://huggingface.co/datasets/laion/OIG).

### Translated Instructions (67,798)
There are 67,798 instructions in total, which are composed of 1,616 task descriptions in [Super-NaturalInstructions](https://arxiv.org/abs/2204.07705) along with a single instance for each of them, 175 seed tasks in [Self-Instruct](https://arxiv.org/abs/2212.10560), and 66,007 instructions from [Unnatural Instructions](https://arxiv.org/abs/2212.09689). To reduce the cost and further improve the quality of the instruction corpus, we separate the translation procedure into three phases: automatic translation, manual verification, and manual correction. These strict quality verification procedures assure the reliability of the translated corpus.
### Exam Instructions (63,532)
The Chinese National College Entrance Examination, Middle School Entrance Examinations, and Civil Servant Examination are the main Chinese commonsense tests. These exams contain various question formats and detailed analysis that can be used as the Chain-of-Thought (**CoT**) corpus. We extract six informative elements from original exam questions, including instruction, question context, question, answer, answer analysis, and coarse-grained subject. There are six main coarse-grained subjects: Chinese, English, Politics, Biology, History, and Geology. There are very few Math, Physics, and Chemistry questions in the corpus because these questions are often with complex symbols which are hard to annotate. For many choice questions, we recommend that the researchers utilize this corpus to further post-process it using prompts or post-process it to blank-filling questions to increase the instructions' diversity further.
### Human Value Alignment Instructions (34,471)
To respect and reflect the major difference caused by different cultural backgrounds, different from other tasks in COIG that leverage one unified collection of instruction-following samples, we categorize the value alignment data into two separate series:
- A set of samples that present shared human values in the Chinese-speaking world. In total, we choose 50 instructions as the augmentation seeds, and produce 3k resulting instructions following samples for general-purpose value alignment in the Chinese-speaking world.
- Some additional sets of samples that present regional-culture or country-specific human values.
### Counterfactural Correction Multi-round Chat (13,653)
The Counterfactual Correction Multi-round Chat dataset (CCMC) is constructed based on the [CN-DBpedia knowledge graph dataset](https://link.springer.com/chapter/10.1007/978-3-319-60045-1_44) with the aim of alleviating and resolving the pain points of hallucination and factual inconsistency in current LLMs. The CCMC dataset includes 5 rounds of role-playing chat between a student and a teacher, and the corresponding knowledge they refer to. The dataset contains ~13,000 dialogues with an average of 5 rounds per dialogue, resulting in ~65,000 rounds of chat.
### Leetcode Instructions (11,737)
Given that the code-related tasks potentially contribute to the ability emergence of LLMs, we argue that code-related tasks aligned with the Chinese natural language should be considered in our datasets. Therefore, we build the Leetcode instructions from a **CC-BY-SA-4.0** license [collection](https://github.com/doocs/leetcode) of 2,589 programming questions. The questions contain problem descriptions, multiple programming languages, and explanations (834 questions do not have explanations).

## Support this project
Your contributions and feedback support the open source ecosystem, improve the bot and provide datasets for future AI research. To participate you can:

Submit Github issues, track issues and help create datasets that need improvement. https://github.com/FlagOpen/FlagInstruct

## Update: April 16, 2023
- Release the five datasets of COIG.

## Disclaimer
These datasets contain synthetic data and in some cases data that includes humans trying to get the language model to say toxic/offensive/trolling things. If you are concerned about the presence of this type of material in the dataset please make sure you carefully inspect each of the entries and filter appropriately. Our goal is for the model to be as helpful and non-toxic as possible and we are actively evaluating ways to reduce or eliminate undesirable content from the instruction tuning datasets.

## License
The COIG dataset that is authored by BAAI is released under an Apache 2.0 license. However, the data also includes content licensed under other permissive licenses such as unnatural instructions data which is licensed under MIT License, or web-crawled data which is used under fair use principles.

## BibTeX & Citation
```
@misc{zhang2023chinese,
      title={Chinese Open Instruction Generalist: A Preliminary Release}, 
      author={Ge Zhang and Yemin Shi and Ruibo Liu and Ruibin Yuan and Yizhi Li and Siwei Dong and Yu Shu and Zhaoqun Li and Zekun Wang and Chenghua Lin and Wenhao Huang and Jie Fu},
      year={2023},
      eprint={2304.07987},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```
