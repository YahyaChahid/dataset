# Darija Open Dataset

<p>
  <img width="150" align='right' src="./images/doda_logo.png">
  <!--- credits to [https://www.freeflagicons.com/country/morocco/sphere_icon/download/] --->
</p>

Welcome to the Darija Open Dataset (DODa), an ambitious open-source project dedicated to the Moroccan dialect. With about 150,000 entries, DODa is arguably the largest open-source collaborative project for Darija <=> English translation built for Natural Language Processing purposes.

In fact, besides semantic categorization, DODa also adopts a syntactic one, presents words under different spellings, offers verb-to-noun and masculine-to-feminine correspondences, contains the conjugation of hundreds of verbs in different tenses, as well as more that 86,000 translated sentences.

Additionally, DODa takes into account the diversity of Darija spellings used in various contexts, making it a versatile resource for language enthusiasts and NLP practitioners. The dataset includes entries written in both Latin and Arabic alphabets, reflecting the linguistic variations and preferences found in different sources and applications.

Our primary goal is to establish DODa as the go-to reference for NLP in Darija. By providing a robust and diverse dataset, we aim to facilitate the development of NLP applications that can cater to the specific linguistic needs of the Moroccan community. We encourage contributions from the Moroccan IT community to collectively build a powerful foundation for future NLP innovations tailored to Moroccan culture and language.

---
<p align="center">
  <img src="./images/wordcloud.png" alt="wordcloud of DODa."  width="100%" />
</p>

[Check out this introductory video about DODa.](https://www.youtube.com/watch?v=IZWuEy7yLB0)

---

## How to contribute

[We've made a tutorial for you in DODa's website](https://darija-open-dataset.github.io/examples/tutorial.html)

---

## Guidelines / Recommendations
1. 3ndk ح dir ح xD (shout-out to [this guy](https://www.facebook.com/watch/?v=238961807618014) 😆), often try to use:

darija | 3 | 7 | 9 | 8 | 2 - 'a' - 'i' | 5 - 'kh'
--- | --- | --- | --- |--- |--- |---
arabic | ع | ح | ق | ه | همزة |  خ  


2. Try to use capitalization to differentiate between the following letters:

| t | T | s | S | d | D |
| :---: | :---: | :---: | :---: | :---: | :---: |
| ت | ط | س | ص | د | ض |


3. Arabic characters with two-letters Latin equivalent:

Arabic alphabet | ش | غ | خ
--- | --- | --- | ---
Latin alphabet | ch | gh | kh


4. Double characters to refer to the emphasis or "الشدة":

darija | 7mam | 7mmam
--- | --- | ---
english | pigeons | bathroom



5. We usually don't add "e" in the end of darija words : `louz` instead of `louze`

6. We usually don't use "Z" or "th" for ظ ، ذ ، ث ,
because we generally don't use these letters in darija (except in northern Morocco, but for the sake of simplicity, we are focusing primarily on standard darija)

7. When using commas, don't forget to surround the expression by quotation marks (as we are using `csv` files)

8. We use spaces as word delimiters, not _ nor - : `thank you` instead of `thank_you`

9. Respect the number of columns in every row you add, you can use empty quotation marks "", or just empty placeholder, in case you don't have extra variations

> "sou9","souk","","سوق","market"

> sou9,souk,,مارشي,market

10. In each row, always start with the most used form (in your opinion of course) of the word in question

11. For future use of this dataset, try to reserve each row to similar variations of the same word. For instance, "sou9" and "marchi" both translate to "market", yet it's better to separate them into two different rows:

> sou9,souk,souq,سوق,market

> marchi,,,مارشي,market

12. `verbs.csv`: The darija translation is reserved to the past tense of the third pronoun "he", whereas the other pronouns and tenses are handled in separate files. The English translation present the basic form (or root) of the English verb.

> ghnna,ghenna,ghanna,,,,غنّا,sing

13. `masculine_feminine_plural.csv`: If it does exist, feminine-plural translation column is for nouns. Regarding adjectives feminine-plural = feminine.

## PyDODa - Python wrapper for the DODa
![Python Badge](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)

Pydoda is a comprehensive Python library that simplifies access and analysis of the DODa dataset. It enables effortless exploration of linguistic content for researchers, developers, and language enthusiasts by providing an intuitive interface for accessing various dataset categories, retrieving spellings and translations.

Integrating Pydoda into your Python workflow grants access to a wide range of functionalities, facilitating insights extraction from the DODa dataset, including semantic and syntactic analysis, translation retrieval, spelling variations exploration, and more.

### Usage example
Pydoda could easily be installed using `pip`:
```
pip install pydoda
```
Here is a small code snippet:
```
from pydoda import Category

# Create an instance of Category
my_category = Category('semantic', 'animals')

# Get the Darija translation of a word
darija_translation = my_category.get_darija_translation('dog')
print(darija_translation)
# Output: klb

# Get the English translation of a word
english_translation = my_category.get_english_translation('mch')
print(english_translation)
# Output: 'cat'
```

For further details, visit the [official Pydoda GitHub repository](https://github.com/saad-out/pydoda) & [official Pydoda documentation](https://saad-out.github.io/pydoda/).

# Usage Terms

- **Research and Personal Use**: You are welcome to use DODa for research, personal projects, and educational purposes, free of charge.

- **Commercial Use**: For commercial purposes or any other usage not covered by the open-source license, please contact the copyright holders aissam or hamza to discuss licensing options and permissions.

## Citation
```
@misc{outchakoucht2021moroccan,
      title={Moroccan Dialect -Darija- Open Dataset},
      author={Aissam Outchakoucht and Hamza Es-Samaali},
      year={2021},
      eprint={2103.09687},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```
