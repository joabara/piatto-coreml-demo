# Piatto - Language ML on iOS

## Recipe + Allergies From Natural Language
The CoreML model used in Piatto is capable of taking natural language input and effortlessly converting it into a structured recipe object. While CreateML made the process of training the model straightforward, building the training dataset for the CoreML model required extensive work with PyTorch and Python. This was necessary to ensure that the model could accurately extract ingredient names and their corresponding quantities from the given text.

That data is not publically available in this repo, and so we provide a visual demo below instead!

![RecipeFromNaturalLanguage.gif](media/RecipeFromNaturalLanguage.gif)

## Cocktail Flavors
The ML solution implemented in Piatto has the capability to identify alcohol ingredients and determine the flavors of the ingredients in a recipe. To achieve this, open-source zero-shot classification embeddings were utilized to label the data, allowing CoreML to transform this into a powerful ML feature within the app.

![RecipeFlavorTagging.gif](media/RecipeFlavorTagging.gif)


## Federated QR Codes
Piatto utilizes federated QR codes, which offer two fantastic advantages. Firstly, these QR codes embed all the underlying recipe data into a single code, eliminating the need for internet or cloud storage to share a recipe. It provides a convenient and offline method of sharing recipes. Secondly, the on-device encryption ensures that the QR code can only be decoded by other users of the Piatto app. If you try scanning the QR code with any other QR code reader, you will only find gibberish instead of the actual recipe. Give it a try!

![FederatedQRCode](media/FederatedQRCode.gif)