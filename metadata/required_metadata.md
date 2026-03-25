## Required model metadata

The following questionnaire is to collect model metadata that is critical to enable AI Foundry support such as Playground and code samples. **Please fill in the info and share with Microsoft contact at the earliest opportunity to ensure the model release is not delayed.**

1. Model name as used in marketing (ex. Phi 3.5 Vision Instruct, please do not include model provider name as part of the model name): Mistral Small 4 (26.03)
2. Model name without a blank space (ex. Phi-35-vision-instruct, please do not include model provider name as part of the model name): mistral-small-2603
3. Short description of the model (1-2 sentences) or an existing documentation of the model: Mistral Small 4 is the first Mistral model to unify the capabilities of our flagship models, Magistral for reasoning, Pixtral for multimodal, and Devstral for agentic coding, into a single, versatile model. With Small 4, users no longer need to choose between a fast instruct model, a powerful reasoning engine, or a multimodal assistant: one model now delivers all three, with configurable reasoning effort and best-in-class efficiency.

4. Does this model support finetuning?: Y
5. Target release date: 03/16/2026
6. Inference task types (ex. chat completion - see the attached `reference_for_task_and_keyword_types.md`):
- Chat completion
- Conversational
- Completions
- Image classification
- Object detection
- Question answering
- Summarization
- Text classification
- Text generation
- Text summarization
7. Keyword to describe the model (only choose up to 3 from the keyword list in `reference_for_task_and_keyword_types.md`):
- Multimodal
- Reasoning
- Coding
8. Modality Input (ex. text, image, etc): text, image
9. Modality Output (ex. text, image, etc): text
10. Sample prompt: 
```json
{
  "model": "mistral-small-2603",
  "messages": [
    {
      "role": "user",
      "content": [
        {
          "type": "text",
          "text": "John is one of 4 children. The first sister is 4 years old. Next year, the second sister will be twice as old as the first sister. The third sister is two years older than the second sister. The third sister is half the age of her older brother. How old is John?"
        },
          },
    ],
    reasoning_effort="high"
}

```
11. Sample API response:
```json
{
  "id": "a1b9a0a492b943289419d37ce95eeb0f",
  "object": "chat.completion",
  "created": 1741598392,
  "model": "mistral-small-2603",
  "choices": [
    {
      "index": 0,
      "message": {
        "role": "assistant",
        "tool_calls": null,
        "content": "Okay, let's try to figure out John's age. So, John is one of 4 children. There are three sisters and one brother (John). Wait, the problem says \"the first sister,\" \"the second sister,\" \"the third sister,\" so that means there are three sisters and John is the brother. So total four children: three sisters and John.\n\nFirst, the first sister is 4 years old. Let's note that down. Let's call the sisters S1, S2, S3, and John is J.\n\nGiven:\n- S1 = 4 years old (current age)\n- Next year, the second sister (S2) will be twice as old as the first sister (S1). Wait, \"next year\" meaning one year from now. So next year, S1 will be 5, and S2 will be twice that, so 10? Wait, but let's check.\n\nWait, the problem says: \"Next year, the second sister will be twice as old as the first sister.\" So next year, S2's age = 2 * S1's age next year.\n\nS1 is currently 4, so next year S1 will be 5. Therefore, next year S2 will be 2*5=10. Therefore, S2's current age is 10 - 1 = 9 years old.\n\nWait, let's confirm that. If S2 is currently X years old, then next year S2 will be X+1. At that time, S1 will be 4+1=5. So X+1 = 2*5 => X+1=10 => X=9. So S2 is currently 9.\n\nNext, \"The third sister is two years older than the second sister.\" So S3 = S2 + 2. Since S2 is 9, S3 is 11.\n\nThen, \"The third sister is half the age of her older brother.\" The older brother is John, since John is a brother (assuming he's older than the sisters; but wait, could John be younger? Wait, the problem says \"her older brother,\" so the brother is older than the third sister. So John is older than S3.\n\nSo S3 = (1/2) * J => J = 2 * S3.\n\nSince S3 is 11, then J = 22.\n\nWait, let's check all steps again.\n\nCurrent ages:\n\nS1 = 4\n\nNext year, S1 will be 5. At that time, S2 will be twice S1's age next year, so 10. Therefore, S2's current age is 10 - 1 = 9.\n\nS3 = S2 + 2 = 9 + 2 = 11.\n\nS3 is half the age of her older brother (John), so John's age is 2 * 11 = 22.\n\nSo John is 22 years old.\n\nWait, but let's make sure there's no mistake here. Let's verify each statement with these ages.\n\nFirst sister is 4: correct.\n\nNext year, first sister will be 5. Second sister next year will be 9 + 1 = 10, which is twice 5: correct.\n\nThird sister is two years older than second sister: 9 + 2 = 11, correct.\n\nThird sister (11) is half the age of her older brother: so brother is 22, which is older than 11: correct.\n\nSo all conditions are satisfied. Therefore, John is 22. ... "
      },
      "finish_reason": "stop"
    }
  ],
  "usage": {
    "prompt_tokens": 77,
    "total_tokens": 1191,
    "completion_tokens": 1114
  }
}
```
12. Any additional headers needed to query the /completions API? No
13. Mark X on the parameters your model supports and provide the corresponding values for each. If none of them is marked, we will assume the model doesn't support parameters. The following values are required for code sample generation: `max_tokens` (for some models is called: `max_completion_tokens`, `max_new_tokens`), `temperature`, `top_p`

*Example:*
*[X] max_tokens (type: number | default value: 2048 | min value: 100 | max value: 4096 )*

- [X] max_tokens (type: number| default value: null |min value: 0 | max value: 128000)
- [ ] max_completion_tokens (type: number | default value: | min value: | max value:)
- [X] temperature (type: number | default value:0.3 |min value: 0| max value: 1.5)
- [X] top_p (type number | default value: 1 | min value: 0 | max value: 1)
- [ ] top_k (type number | default value: | min value: | max value: )
- [X] presence_penalty (type number | default value: 0 | min value: -2| max value: 2)
- [X] frequence_penalty (type number | default value: 0| min value: -2| max value: 2)
- [ ] repetition_penalty (type number | default value: | min value: | max value: )
- [ ] reasoning_effort (type multiple_choice | default value: | options: [] )
- [X] stop (type string | default value: )
- [ ] rows (type number | default value: | min value: | max value: )
- [ ] do_sample (type boolean | default value: )
- [ ] return_full_text (type: boolean | default value: )

14. Mark X on capabilities your model supports and the corresponding values

- [X] bring your own data support
- [X] system prompt support
- [X] is it a chat completion model? Yes
- [X] images per turn support. How many images does the model supports per turn? 8
- [X] assistant support (streaming, function calling supported)
- [X] agent support (streaming, function calling supported)

*If your model needs to support any other parameter/capability that is not in the above list, please list them below with their default value and a brief description of it.*

15. Model announcement title (max 25 characters): Mistral Small 4 (26.03)
16. Model description (max 80 characters): Mistral Small 4 delivers state-of-the-art performance at lower cost

*For model announcement, it must meet the character limits. You can see the current model announcement examples under "What's New" on <https://ai.azure.com/explore/models>*

17. [Optional] If this is the first time you are onboarding a model with Microsoft, add a your logo image file to the metadata folder . The image file must be in SVG format and 42x42 dimensions. Preferably 1kb max size. Azure AI Foundry model catalog cannot use any other format. This is for the model catalog only, and you can use other sizes for marketing/etc.
