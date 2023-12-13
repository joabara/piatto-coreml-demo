# Piatto - Language ML on iOS

## Recipe + Allergies From Natural Language
The CoreML model used in Piatto is capable of taking natural language input and effortlessly converting it into a structured recipe object. While CreateML made the process of training the model straightforward, building the training dataset for the CoreML model required extensive work with PyTorch and Python. This was necessary to ensure that the model could accurately extract ingredient names and their corresponding quantities from the given text.

That data is not publically available in this repo, and so we provide a visual demo below instead!

However, I did open-source the Allergy CoreML models in this repo. If anything, I would like for developers to take my AllergyML and use it to improve their Allergy detection! 

![RecipeFromNaturalLanguage.gif](media/RecipeFromNaturalLanguage.gif)

## Cocktail Flavors
The ML solution implemented in Piatto has the capability to identify alcohol ingredients and determine the flavors of the ingredients in a recipe. To achieve this, open-source zero-shot classification embeddings were utilized to label the data, allowing CoreML to transform this into a powerful ML feature within the app.

![RecipeFlavorTagging.gif](media/RecipeFlavorTagging.gif)


## Federated QR Codes
Piatto utilizes federated QR codes, which offer two fantastic advantages. Firstly, these QR codes embed all the underlying recipe data into a single code, eliminating the need for internet or cloud storage to share a recipe. It provides a convenient and offline method of sharing recipes. Secondly, the on-device encryption ensures that the QR code can only be decoded by other users of the Piatto app. If you try scanning the QR code with any other QR code reader, you will only find gibberish instead of the actual recipe. Give it a try!

![FederatedQRCode](media/FederatedQRCode.gif)


## Recipe Generation AI
Piatto offers a powerful Generate Recipe feature that leverages OpenAI for recipe generation. However, to ensure seamless functionality even without internet access and without the need for storing user data in a cloud, a local recipe generation AI model has been deployed within the app. This allows users to enjoy all the app's features offline, while maintaining privacy and data security.

At this time, the model works very well in a PyTorch environment, but I am still learning to optimize text generation models iOS.

### OpenAI Version
![RecipeGeneration](media/RecipeGeneration(Online).gif)

### PiattoAI (my Version)
Below is the model output from the iOS CoreML adaptation of the RecipeGeneration model built in PyTorch (named `recipegen_distilgpt2_48_256_6). This model is designed to be effective and ultra-light (only weighs ~300MB) and can cover all the needs of the OpenAI version (albeit much slower). Based on the results, this looks like a working recipe!
```
Recipe Name: Blueberry Pancakes

Name: Blueberry Pancakes
Ingredients: ['1 cup all-purpose flour;', 
'3/4 teaspoon baking powder;', 
'Dash salt;', 
'2 eggs, lightly beaten;', 
'1 cup 2% milk;', 
'2 tablespoons canola oil;', 
'2 cups fresh or frozen blueberries;']
```
