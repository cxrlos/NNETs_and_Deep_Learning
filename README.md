<p align="center">
    <img src="https://miro.medium.com/max/700/1*0FlvitTZnPKh8qkJ7UPLeQ.png" height="64" alt="NNET Logo">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f8/Python_logo_and_wordmark.svg/1280px-Python_logo_and_wordmark.svg.png" height="64" alt="Python Logo">
</p>
<h1 align="center">Context-free Name Entity Recognition</h1>
<h2 align="center">NLP via Deep Neural Networks</h2>
<p align="center"> Codes developed during a research fellowship at <a href="https://www.tec.mx" target="_blank">Tec de Monterrey</a> under <a href="https://research.tec.mx/vivo-tec/display/PID_321664" target="_blank">Leonardo Chang's</a>  supervision.</p>

## Description

In a common NER (Name Entity Recognition) environment, context is crucial to understand and tokenize the input data. During this semester, alongside my mentor, I will attempt to find a solution for accurate context-free implementation.

Using OCR technologies and documents such as invoices, the text obtained is labeled and will be recognized as a label (e.g. "*Date:*") or value (e.g. "*01/01/1970*").

## Dependencies

As of today, the packages used for the development are the following:

- [Numpy](https://github.com/numpy/numpy)

- [spaCy](https://github.com/explosion/spaCy)

## NER Labels Used

The [en_core_web_lg][https://spacy.io/models/en#en_core_web_lg] will be used, there is an equivalent type of classification in the package for almost every desired value type.

|    **Data Type**     |                 **SpaCy Default Value**                 |                          **Notes**                           |
| :------------------: | :-----------------------------------------------------: | :----------------------------------------------------------: |
|         Date         |                        ``DATE``                         |            Different formats should be recognized            |
|       Numbers        |                ``CARDINAL``,``QUANTITY``                |                                                              |
|       Currency       |                        ``MONEY``                        |                   It's a subset of numbers                   |
|     * Addresses      | Not included, but ``FAC``, ``LOC`` types can be helpful | Can be separated by different OCR readings due to break lines |
|         Name         |        ``PERSON``, ``ORG``,``NORP``,``PRODUCT``         |          Representing a person, company, or product          |
|     * Identifier     |                      Not included                       |        Alphanumerical code unique to a specific item         |
| * Miscellaneous text |                      Not included                       | Text representing all the other possible strings such as annotations |

> We might divide Name into subclasses.

