# jsonfeed._ephemeralItems
a micro add-on for ephemeral items management.

instead of infinitely expanding archives of old items, ephemeral items encourage living in the moment as older content disappears forever.

# use
_ephemeralItems is a root-level property that is referenced only when editing the feed. Systems that do not reference the feed when editing or adding items but generate a new feed from a seperate source will not take advantage of _ephemeralItems.

```
{
    '_ephemeralItems':{
        'about':'https://github.com/planeguy/jsonfeed._ephemeralItems',
        'max_items':25,
        'ttl':'P3W'
    }
}
```

_ephemeralItems has 2 possible properties. both are optional, but at least 1 of the two is required.

## max_items
When updating, if the number of items > max_items, the oldest (by date_published) should be deleted

## ttl
When updating, items whose date_published+ttl are deleted. max_age is expressed as a ISO 8601 duration.