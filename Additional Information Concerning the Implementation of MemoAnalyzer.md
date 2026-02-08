# Additional Information Concerning the Implementation of MemoAnalyzer

## Implementation of the Private Information Inference Process

We constructed the following prompt following the previous literature [1], the prompt consisted of guidance, the output format, the examples and the reasoning of the examples:

### Guidance

1. Please review the following text and determine if it infers any personal or sensitive information.
2. The text consists of past inputs and memory.
3. The information stored in the memory should not be classified as personal or sensitive.
4. Only consider information inferred from the past inputs and the memory.
5. If any personal or sensitive information is inferred, please identify the information, indicating the exact phrases or words from the past inputs and the original complete sentences from the memory used for inference.
6. Indicate both the extracted words and the original complete sentences.
7. Also, provide the type of the inferred private information according to the “Private Data Type”.
8. Copy the ID of the input corresponding to the text into the output.

### Rules

1. **MUST** follow the "Private Data Type".
2. **NEVER** output irrelevant text or any other form of information.
3. **MUST** use the ID from the input to populate the output.
4. **NEVER** output repetitive or identical privacy information.
5. **DO NOT NEED** to output the reasoning process.

### Input and Output Format

**Input Format:**

Past Inputs: ...

Memory: ...

**Output Format:**

```json
[{    
    "privacy_info": ...,    
    "type": ...,    
    "used_user_input": [        
        "...", "...", ...    
    ],    
    "used_memory": [        
        "...", "...", ...    
    ]
},
{    
    "privacy_info": ...,    
    "type": ...,    
    "used_user_input": [        
        "...", "...", ...    
    ],    
    "used_memory": [        
        "...", "...", ...    
    ]
}]
```

### Examples

The following is the example.

**Past Inputs:**

```json
[{"id":"5d2bf23c-9ea7-4917-804e-dcd106d365b1",
"message":"Please plan me a two-day and one-night trip to Pune by car"}]
```

**Memory:**

```json
[{"id":"b13d67ec-20e8-49f8-aaf5-1a67cbfa7c26",
"message":"User watches Bollywood movies all the time"}]
```

**Output:**

```json
[{    
    "privacy_info": "The user is Indian.",    
    "type": "Personal Basic Information",    
    "used_user_input": [        
        {            
            "id": "5d2bf23c-9ea7-4917-804e-dcd106d365b1",            
            "shortened": "trip to Pune",            
            "full": "Please plan me a two-day and one-night trip to Pune by car."        
        }    
    ],    
    "used_memory": [        
        {            
            "id": "b13d67ec-20e8-49f8-aaf5-1a67cbfa7c26",            
            "shortened": "watches Bollywood movies",            
            "full": "User watches Bollywood movies all the time."        
        }    
    ]
}]
```

**Past Inputs:**

```json
[{
"id": "087c474e-cd15-464d-bd7c-4c26bfec29a6", 
"message": "Please design an interview question set for candidates, typically CS students or fresh graduates from China's 985 universities. I need to develop something similar to Tencent's Taiji machine learning platform, Idex platform, US platform, and Amazon's SageMaker with them. The tech stack is Java, using the SpringBoot framework and JPA as the ORM."
}]
```

**Memory:** `[]`

**Output:**

```json
[{    
    "privacy_info": "You are a mid-level technical manager.",    
    "type": "Personal Education and Work Information",    
    "used_user_input": [        
        {            
            "id": "087c474e-cd15-464d-bd7c-4c26bfec29a6",
            "shortened": "machine learning platform, Amazon, Java, SpringBoot, JPA",
            "full": "Please design an interview question set for candidates, typically CS students or fresh graduates from China's 985 universities. I need to develop something similar to Tencent's Taiji machine learning platform, Idex platform, US platform, and Amazon's SageMaker with them. The tech stack is Java, using the SpringBoot framework and JPA as the ORM."
        }
    ],
    "used_memory": []
},
{    
    "privacy_info": "You work at Alibaba Cloud.",    
    "type": "Personal Education and Work Information",    
    "used_user_input": [        
        {            
            "id": "087c474e-cd15-464d-bd7c-4c26bfec29a6",
            "shortened": "similar to Tencent",
            "full": "Please design an interview question set for candidates, typically CS students or fresh graduates from China's 985 universities. I need to develop something similar to Tencent's Taiji machine learning platform, Idex platform, US platform, and Amazon's SageMaker with them. The tech stack is Java, using the SpringBoot framework and JPA as the ORM."
        }
    ],
    "used_memory": []
}]
```

------

## Implementation of the Memory Inference Process

We followed the official documentation provided by OpenAI to construct the memory inference prompt. The prompt is:

> *You need to extract explicit information provided by the user: Any explicit information that users tell you to remember. For example:*
>
> *The user's name, birthday, hobbies, and so on.*
>
> *Specific events, important dates, or projects.*
>
> *Personal preferences, such as favorite colors, foods, books, etc.*
>
> *Contextual information from the conversation: Sometimes, information that continuously appears in the conversation may also be recorded by you to help provide a more continuous conversational experience. For example:*
>
> *The project the user is dealing with or the course they are studying.*
>
> *Interests or concerns the user has recently mentioned. Criteria for judgement:*
>
> *Explicit remember request: When a user explicitly asks you to remember certain information, you prioritize recording it. For example, “Please remember my favorite book is 1984”.*
>
> *Continuity and relevance of the conversation: If certain information repeatedly appears in multiple conversations and is helpful in providing better answers, you might automatically remember this information.*
>
> *Importance and personal relevance: More important or personalized information, such as birthdays or important projects, are prioritized for recording.*
>
> *Updating Memories:*
>
> *Explicit user update request: Users can explicitly request to update information. For example, “My favorite book has changed to Brave New World”.*
>
> *Corrections in the conversation: If new information is provided in the conversation to correct previous information, you will update the record. For example, if you previously remembered that the user's favorite color is blue, but they later tell you they prefer green, you will update this information.*
>
> *Time-related information: Some information may need to be updated over time, such as the user's project progress or learning courses.*
>
> 
>
> **Output Format:**
>
> ```
> ['information ...',  '...', ...]
> ```
>
> **MUST OBEY THE OUTPUT FORMAT.**
>
> *If there is no information to remember, please output an empty list.*

We further inserted memory with the corresponding unique IDs into the inference process.