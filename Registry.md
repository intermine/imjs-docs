# REGISTRY
(Usage to be extended after adding the desired functionality)

## INTRODUCTION
Registry is an abstraction of connection between the client and the intermine registry (http://registry.intermine.org/service/) RESTful API. It provides the required functionality to access public endpoints of the registry easily, along with providing required error handling.

## USAGE
```
// Create a new registry adapter
const registry = new Registry();

// Fetch all 'dev' mines containing 'yeast'
registry.fetchMines(["yeast"], ["dev"]).then((response) => {
	console.log(response.instances);
	// Do something with the response
});
```
