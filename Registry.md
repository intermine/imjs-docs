# REGISTRY

## INTRODUCTION

Registry is an abstraction of connection between the client and the intermine registry (http://registry.intermine.org/service/) RESTful API. It provides the required functionality to access public endpoints of the registry easily, along with providing required error handling.

## USAGE

### Create a new registry adapter
```javascript
const registry = new Registry();
```
### Fetch all 'dev' mines containing 'yeast'
```javascript
registry.fetchMines(["yeast"], ["dev"]).then(response => {
  console.log(response.instances);
  // Do something with the response
});
```
### Fetch information about an instance given its id, name or namespace
```javascript
registry.fetchInstance("flymine").then(instance => {
  console.log(instance);
  // Do something with the instance
});
```
### Fetch a namespace associated with a given url
```javascript
registry.fetchNamespace("www.flymine.org").then(namespace => {
  console.log(namespace);
  // Do something with the namespace obtained
});
```
