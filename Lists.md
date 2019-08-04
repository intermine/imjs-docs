# LISTS

Lists are representations of collections of objects stored on the server

## USAGE
```
// Create a new Service adapter
const intermine = require('imjs');
const flymine = new intermine.Service({ root: 'www.flymine.org/query' })

// Fetch all lists and print their name
flymine.fetchLists().then(listArr => {
    listArr
        .map(listObj => listObj.name)
        .forEach(console.log)
})

// Find a particular list by its name
flymine.findLists('UseCase5_backgroundGeneList').then(list => {
    console.log(`TITLE: ${list.title}`)
    console.log(`NAME: ${list.name}`)
    console.log(`TYPE: ${list.type}`)
    console.log(`CREATED AT: ${list.dateCreated}`)
})

// Fetch a list by its name and display its contents
flymine.fetchList('UseCase5_backgroundGeneList').then(list => {
    // Call the content function on the list object
    return list.content();
}).then(contentArr => {
    // An array of contents present in the list is displayed
    contentArr.forEach(console.log)
})
```