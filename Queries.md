# QUERYING THE INTERMINE

## SAMPLE QUERY
Following query shows the genes located on a particular chromosome of D. melanogaster
### Create a new Service adapter
```javascript
const intermine = require('imjs');
const flymine = new intermine.Service({ root: 'www.flymine.org/query' })
flymine.rows({
	from: 'Gene',
	select: [
		'Gene.chromosome.primaryIdentifer',
		'Gene.organism.name'
	]
	where: [
		['Gene.chromosome.primaryIdentifier', '=', '2L'],
		['Gene.organism.name', '=', 'Drosophila melanogaster']
	]
}).then(result => {
	// Do something with the result
}).catch(err => {
	// Error handling goes here
})
```

## TEMPLATE QUERIES
Template is a pre-defined query, that allows you to search the database without having to construct your own query or understanding underlying data structure. Templates generally represent some common use case scenario of the mine.

### Create a new Service adapter
```javascript
const intermine = require('imjs');
const flymine = new intermine.Service({ root: 'www.flymine.org/query' })
```

### To fetch all the templates of a particular service available
```javascript
flymine.fetchTemplates().then(templates => {
	// Print the names of the templates
	Objects.keys(templates).forEach(k => console.log(k))
})
```

### To query according to a particular template
```javascript
flymine.templateQuery('GO_Gene').then(query => {
	// Do something with the template
	console.log(query.model.name);
})
```
