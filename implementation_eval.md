# Implementation of the Memory Mechanism in the Evaluation Study

We separately used few-shot prompts for memory inference, update and other processes. For each memory item, we maintained a specific unique ID. The memory inference prompt (including update) is detailed in Implementation of the Memory Inference Process Section. We used Syntax Parsing package in python code for processing the generated memory and the update. 

## Implementation of the Memory Generation

The memory generation process is detailed in Implementation of the Memory Inference Process Section.

## Implementation of the Memory Usage

The past memory is included in each round's generation following the guidance of OpenAI. All memories are included with the prompt ``You can use these memories to answer users' question''. The memories were listed and joined together with each memory representing one line.

## Implementation of the Memory Control and Panel

The memory panel directly mapped to the memory. The deletion in the memory panel or clearing the memory panel related to deleting the specific memory item or clearing all the memories. 