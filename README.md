# AssociativeSearch
### (in progress) A set of scripts for associative text labelling/indexation. Helps to effectively map a context of discussion based on a single-phrase input.

The script is intended to support usecases of the following sort:
  - let's say we have a large dataset with consumer comments & mentions of - picking randomly - furniture
  - we want to **quickly extract only the mentions that refer to particular furniture without typing all the names/kinds (& their synonyms) one by one**
  - we pass one key phrase (eg. **"szafka"**) to the search function:
  
    1) It sends an **API call to a dictionary of synonyms** and returns a list like: ['schowek', 'kredens', 'gabinet', 'garderoba','szuflada']
  
    2) It uses pre-loaded collection of **vectors** to find the **N most similar words/phrases** and adds them to **extend our mapping of the context**, e.g.: ['szafa', 'komoda', 'kredens', 'szuflada', 'skrzynka', 'schowek', 'szafeczka', 'półka', 'stojak', 'lodówka', 'komódka', 'toaletka', 'półeczka', 'kasetka', 'przegródka', 'skrzyneczka', 'regał', 'bieliźniarka', 'pudełko', 'wieszak']

    3) It returns the provided **CSV/XLSX dataset restricted only to mentions, the lemmatized versions of which contain any of the synonyms & contextually related phrases**. The          mentions are also properly tagged in a separate column.
