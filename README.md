# HOW TO SUBMIT A MODEL CARD AND METADATA TO AZURE AI FOUNDRY

### Instruction

1. Inside the metadata folder, you will find a md file (`required_metadata.md`). **Complete this md file as soon as possible and share with your Microsoft contact. Failure to do so can risk a delay to the model release schedule.**
2. Add a your logo image file to the metadata folder if this is the first time you are onboarding a model with Microsoft. **The image file must be in SVG format and 42x42 dimensions. Preferably 1kb max size. Azure AI Foundry model catalog cannot use any other format.** This is for the model catalog only, and you can use other sizes for marketing/etc.
3. Inside the modelname folder, you will find three md files (`description.md` `evaluation.md` `notes.md`). Fill in the content as instructed in the file. DO NOT CHANGE THE FORMAT AS IT COULD RISK A REJECTION DURING THE MODEL CARD CONTENT REVIEW.

### Required

- `metadata/required_metadata.md`: This captures model metadata needed to make the model work with AI Foundry features such as playground and code samples, which may require a long development time.
- `modelname/description.md`: this is what you see on AI Foundry model catalog model details page.

### Highly recommended for best user experience

- `evaluation.md`: this captures model provider's evaluation data.
- `notes.md`: this captures disclosure/responsible ai/license information.
