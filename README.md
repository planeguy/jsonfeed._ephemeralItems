# jsonfeed._ephemeral_items

a micro add-on for ephemeral items management.

instead of infinitely expanding archives of old items, ephemeral items encourage living in the moment as older content disappears forever.

this extension is inspired by my sad attempt at redemocratization of social media, [clusterfriend](https://github.com/planeguy/clusterfriend)

# use
_ephemeral_items is a root-level property that is referenced only when editing the feed. Systems that do not reference the feed when editing or adding items but generate a new feed from a seperate source will not take advantage of _ephemeral_items.

```
{
    "_ephemeral_items":{
        "about":"https://github.com/planeguy/jsonfeed._ephemeral_items",
        "max_items":25,
        "ttl":"P3W"
    }
}
```

_ephemeral_items has 2 main properties. both are optional, but at least 1 of the two is required.

## max_items
When updating, if the number of items > max_items, the oldest (by date_published) should be deleted.

## ttl
When updating, items whose date_published+ttl are deleted. ttl is expressed as a ISO 8601 duration.

## when both max_items and ttl are present
When both properties are present, it is recommended to trim items by ttl before checking for max_items.
