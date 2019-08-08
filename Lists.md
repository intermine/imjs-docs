# LISTS

Lists are representations of collections of objects stored on the server

## USAGE
```javascript
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

// Lists can be created through the a) Query saving mechanism and b) List upload mechanism

// Saving lists using Query saving mechanism
flymine.query({
    ...
}).then(q => {
    q.saveAsList({
        name: 'new_list',
        tags: ['test-list', 'other-tags', ...]
    })
})

// Saving lists using List upload mechanism
//'type' parameter denotes the type of objects these are identifiers of
flymine.createList(
    // Options array, providing information about the list
    {
        name: 'new_list_2',                                     //required
        type: 'Gene',                                           //required
        description: 'Demonstrating list upload mechanism',     //optional
        extraValue: 'To disambiguate between different lists'   //optional
    },
    // Provide identifiers to include in the list
    [
        ...
    ]
)
```
