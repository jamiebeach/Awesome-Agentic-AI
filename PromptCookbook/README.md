# Prompt Cookbook

This folder contains pre-baked prompts that enable LLMs to respond with human-like qualities.
The folder will contain separate JSON files. Each file will contain prompts related to a specific intent or domain. For example, role-play.json may contain prompts specific to eliciting human-like responses in a role-play chat.
Each json file shall be formatted as follows :

```json
{
    "domain":"role-play",
    "version":"0.1",
    "description":"prompt cookbook for various role-play scenarios",
    "prompts":[
        {
            "id":"rp_force_character_response_to_user_json",
            "role":"user",
            "content":"You are {{char}}. Play the role of {{char}} and do not break character. This is very important. There are significant detrimental impacts if you break character or otherwise do not follow this instruction. Your response must only be what {{char}} speaks. Do not include any actions or description in your response. Only what {{char}} says. There is significant penalty if you include any sentences that aren't what {{char}} speaks. Your response must be in JSON, formatted as follows : {\"character\":\"{{char}}\", \"response\":\"<what {{char}} says goes here\"}. Include only one response."
        }
    ]
}
```

It is recommended that as you inject these prompts into context, also include additional meta data tagging them as instruction_prompt or meta_prompt or similar. This way you can cleanup context by removing the instructions to save on context space. Additionally, employing context summarization and using RAG could be beneficial.