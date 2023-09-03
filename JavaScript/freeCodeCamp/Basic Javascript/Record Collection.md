#Record Collection

You are creating a function that aids in the maintenance of a musical album collection. The collection is organized as an object that contains multiple albums which are also objects. Each album is represented in the collection with a unique `id` as the property name. Within each album object, there are various properties describing information about the album. Not all albums have complete information.

The `updateRecords` function takes 4 arguments represented by the following function parameters:

`records` - an object containing several individual albums
`id` - a number representing a specific album in the `records` object
`prop` - a string representing the name of the album’s property to update
`value` - a string containing the information used to update the album’s property
`Complete` the function using the rules below to modify the object passed to the function.

Your function must always return the entire `records` object.
If `value` is an empty string, delete the given `prop` property from the album.
If `prop` isn't `tracks` and `value` isn't an empty string, assign the `value` to that album's `prop`.
If `prop` is `tracks` and `value` isn't an empty string, you need to update the album's `tracks` array. First, if the album does not have a `tracks` property, assign it an empty array. Then add the `value` as the last item in the album's `tracks` array.
Note: A copy of the `recordCollection` object is used for the tests. You should not directly modify the `recordCollection` object.

## Hints
 - Use `bracket notation` when accessing object properties with variables.

`Push` is an array method you can read about on Mozilla Developer Network.

You may refer back to Manipulating Complex ObjectsIntroducing JavaScript Object Notation (JSON) for a refresher.

### Before

```javascript
// Setup
// Setup
const recordCollection = {
  2548: {
    albumTitle: 'Slippery When Wet',
    artist: 'Bon Jovi',
    tracks: ['Let It Rock', 'You Give Love a Bad Name']
  },
  2468: {
    albumTitle: '1999',
    artist: 'Prince',
    tracks: ['1999', 'Little Red Corvette']
  },
  1245: {
    artist: 'Robert Palmer',
    tracks: []
  },
  5439: {
    albumTitle: 'ABBA Gold'
  }
};

// Only change code below this line
function updateRecords(records, id, prop, value) {
  return records;
}

updateRecords(recordCollection, 5439, 'artist', 'ABBA');

```

### Answers

```javascript
// Setup
var collection = {
    "2548": {
      "album": "Slippery When Wet",
      "artist": "Bon Jovi",
      "tracks": [
        "Let It Rock",
        "You Give Love a Bad Name"
      ]
    },
    "2468": {
      "album": "1999",
      "artist": "Prince",
      "tracks": [
        "1999",
        "Little Red Corvette"
      ]
    },
    "1245": {
      "artist": "Robert Palmer",
      "tracks": [ ]
    },
    "5439": {
      "album": "ABBA Gold"
    }
};
// Keep a copy of the collection for tests
var collectionCopy = JSON.parse(JSON.stringify(collection));


// Only change code below this line
let records =recordCollection;

function updateRecords(records, id, prop, value) {
  if(value===""){
    delete records[id][prop];
  }else if(prop !== "tracks" && value !==""){
    records[id][prop] = value;
  }else if(prop ==="tracks" && value !==""){
    if(!records[id].hasOwnProperty(prop)){
      records[id].tracks=[];
      records[id].tracks.push(value);
    }else{
      records[id][prop].push(value);
    }
  }
  return records;
}
// Alter values below to test your code
updateRecords(recordCollection, 5439, 'artist', 'ABBA');
```
### Caution
1. Don't forget[id] in this code !records[id].hasOwnProperty(prop)

### Thinking

1. The more easy is to delete the prop if no value
2. If the prop is not tracks it's easy to add the value to this prop
3. Here we need to find if the object have a property tracks if not we create
this prop with a empty array and we push it the value. I use `.hasOwnProperty` for
doing this.
