<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">Table of Contents</h2></summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
    </li>
    <li>
      <a href="#dataset-components">Dataset components</a>
    </li>
       <li>
      <a href="#data-collection-and-annotation">Data collection and annotation</a>
      <ul>
        <li><a href="#data-collection">Data collection</a></li>
      </ul>
      <ul>
        <li><a href="#data-annotation">Data annotation</a></li>
      </ul>
    </li>
    <li><a href="#license">License</a></li>
  </ol>
</details>

## About The Project
This repository contains a dataset is colected from [UTEHY website](http://www.utehy.edu.vn/) and it's fan page in two year (2018 - 2020) and built for [Rasa platform](https://rasa.com/docs/rasa/).

## Dataset components
* nlu data: *160 intents* with *4127 data samples* were manual annotated.
* core data: *211 stories*.

## Data collection and annotation
### Data collection
* To build the chatbot system, we collected data from two main sources including the university’s website and its fan page, in the last two years. We do this manually since there are not any available tools. Collected data contains documents and conversations relating to admission. After removing questions that are not answered yet, we acquired 400 conversations including *8,500 questions* and *6,500 answers*. To refine the data, unclear and ambiguous questionswere first removed, and then regular expressions were appliedto cleaning the data (e.g. removing teen codes or icons).

### Data annotation
* For Rasa-based chatbot systems, data annotation of intents and entities plays an important role in building the Natural Language Understanding (NLU) component where the system needs to understand a given user's intent before predicting the next action. As recommended by Rasa, it is necessary to provide at least 10 examples for each intent to train NLU efficiently. This would be time-consuming when doing manually. We added more examples for intents that have few instances to avoiding data imbalance. It satisfies the requirement of intent examples for training NLU. Finally, we obtain a final dataset with 160 intents, in which each of them has over 10 examples.

* Apart from intent identification, Rasa NLU also requires named entity recognition (NER). This is because the policies learn to predict the next action based on a combination of both intent and entities. We, therefore, annotated entities for input data. In this task, we consider five entity types including location, majors, organization, person, and time. The statistics of entity annotation is presented in the following table:


NER | train | test | total |
| --- | --- | --- | --- |
| Location | 193 | 41 | 234 |
| Majors | 510 | 139 | 649 |
| Organization | 903 | 226 | 1,129 |
| Person | 9 | 2 | 11 |
| Time | 102 | 39 | 141 |

## License
Distributed under the MIT License. See `LICENSE` for more information.
