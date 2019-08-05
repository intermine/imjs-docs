# QUERYING THE INTERMINE

## SAMPLE QUERIES
(Fill this space using some queries with real use cases)

## TEMPLATE QUERIES
Template is a pre-defined query, that allows you to search the database without having to construct your own query or understanding underlying data structure. Templates generally represent some common use case scenario of the mine.

```
// Create a new Service adapter
const intermine = require('imjs');
const flymine = new intermine.Service({ root: 'www.flymine.org/query' })

// To fetch all the templates of a particular service available
flymine.fetchTemplates().then(templates => {
	// Print the names of the templates
	Objects.keys(templates).forEach(k => console.log(k))
})

// To query according to a particular template
flymine.templateQuery('GO_Gene').then(query => {
	// Do something with the template
	console.log(query.model.name);
})
```