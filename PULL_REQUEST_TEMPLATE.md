### <a name="summarize-the-change-in-the-pull-request-title"></a>Résumer la modification dans le titre de la demande de tirage (Pull request)

Décrivez votre modification, en particulier *pourquoi* vous pensez qu’elle est nécessaire.

Corrige #Issue_Number (si nécessaire)


Thank you for providing suggestions to the localized article! 

## Localization Reference

- [Microsoft Language Style Guide](https://www.microsoft.com/Language/StyleGuides) provides the full version of the Mirosoft Language Style Guide for all the available languages that Microsoft is localizing. You may also refer a short version [Quick Start Localization Style Guide](https://docs.microsoft.com/globalization/localization/styleguides) for some popular languages.

- All the technical term definition and translation are listed on [Term Studio](https://termstudio.azurewebsites.net/Default.aspx) for all teh available languages that Microsoft is localizing.

## Contribution Tips

We recommend you to avoid the temptation of translation English updates as soon as you see them. There is a time lag needed for us to process the translation work. And please don't keep committing new suggests to the same PR.

- **Small** edits: To make a small change like a copyedit to an article, use the Edit button on the article. 
- **Medium** edits: To make a bigger change like adding or deleting a sentence or two, we suggest you to submit the pull request to **English** repo. If the writer accept your edits, your name will be listed on English article besides receive the contribution points.
- **Large** edits: To make a substantive change OR to create an article, create a **GITHUB ISSUE** instead of Pull Request.  

## Common FAQ
 
### My PR was merged, but i never see my suggestion on DOCS. Why?

We agree with you that the translation is not perfect or not correct. Our linguistic moderator (LM) lightly edits your suggestion to follow the language style guide. We merge your PR, you get credit. 

### My PR was merged, and i saw all my suggestions published on DOCS. But then my suggestions disappeared. Why? 
 
It may happen when the same string in English is updated after we accepted your suggestion. The updated localized string overwrote your suggestion.

### My merged PR contains 5 suggestions, but I only can see 2 of them published to DOCS. Why?

We accepted two suggestions and declined the other three. We merged your PR, then we submitted another PR reverting the three declined ones to the original string. You still get credit.

### I see a lot of API names or setting values being translated. The translation is not professional. Can you change the translator?

We are sorry about this bad experience! It is because the string is not formatted with code fence in the English source file.   Without code fence, it is difficult for our translators to know which string is not translatable.  This problem especially happens on machine translated content.

### I always get same responses on GitHub, am I speaking with an Azure bot? 

No, you are talking with our Community Contribution team. We created response templates for the most common scenarios, so our team can respond easily and quickly in all languages.
