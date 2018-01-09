# Budget Classification

## Background

Mexico is implementing the Open Fiscal Data Package (OFDP) which allows countries to express expenditures according to their different Budget Classification. Thus, we propose an extension that allows users to express monetary figures in different types of budget classifications. 
Even thou the classifications we are currently using are: Economic, Administrative and the Funding Source, the OFDP standard is comprehensive enough to include more classifications depending on the country.
Besides, this extension would also allow users to express amounts through their different accruing moments.  

## Extension fields

This extension adds an array named budgetClassifications like a property to the BudgetBreakdown object and consist of the following fields:

	•Origin- allows you to choose an origin of the monetary funding. al mismo nivel que classifications y que sea open codelist (federal, estatal, municipal)
	•Classifications - allows you to choose a budget classification.
	•Level - ID to identify the hierarchy level for the concept inside a classification.
	•levelLabel - Name of the concept.
	•Id - ID to identify a specific value of the concept.
	•Description - Description of the specific value of the concept.
	
Also this array has an array named measures consisting of an id and an object budgetClassification.value is a value reference:

	•Id - ID to identify the specific accruing moment in which the budget's value will be expressed.
	•Value - Value per accruing moment.
		•amount - Amount as a number.
		•currency - The currency for each amount should always be specified using the uppercase 3-letter currency code from ISO4217.

## Example

```json
"budgetclassifications": [{
  "origin": "federal",
  "classifications": "financialSource",
  "level": 1,
  "levelLabel": "Fuente de Financiamiento",
  "id": "1",
  "description": "Recursos fiscales",
  "Measures": [{
    "id": "Aprobado",
    "value": {
    	"amount": 0.0,
    	"currency": "MXN"
	}
  }]
}]
```
