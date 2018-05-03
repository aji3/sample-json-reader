# sample-json-reader

Parse json string and convet to list of values in the following way:

## JSON string

```
{
  "aaa": "aaaa",
  "bbb": 100,
  "ccc": 99.99,
  "obj": {
    "ccc": "cccc",
    "ddd": {
      "dd1": "dd11"
    },
    "eee": {
        "fff1": true,
        "fff2": false,
        "fff3": null,
        "ggg": ["a1", "a2"],
        "hhh": [
            {"ii": "11"}, {"ii": "22"}, {"ii": "33", "jj": "j3"}
        ]
    }
  },
  "list": [
    "aa", "bb", "cc"
  ],
  "list2": [
      {"aa":"aaa", "bb":"bbb"},{"aa":"aaa2", "bb":"bbb2"}
  ]
}
```

## Converted table

key|type|value
---|---|---
aaa|VALUE_STRING|aaaa
bbb|VALUE_NUMBER_INT|100
ccc|VALUE_NUMBER_FLOAT|99.99
obj.ccc|VALUE_STRING|cccc
obj.ddd.dd1|VALUE_STRING|dd11
obj.eee.fff1|VALUE_TRUE|true
obj.eee.fff2|VALUE_FALSE|false
obj.eee.fff3|VALUE_NULL|null
obj.eee.ggg[0]|VALUE_STRING|a1
obj.eee.ggg[1]|VALUE_STRING|a2
obj.eee.hhh[0].ii|VALUE_STRING|11
obj.eee.hhh[1].ii|VALUE_STRING|22
obj.eee.hhh[2].ii|VALUE_STRING|33
obj.eee.hhh[2].jj|VALUE_STRING|j3
list[0]|VALUE_STRING|aa
list[1]|VALUE_STRING|bb
list[2]|VALUE_STRING|cc
list2[0].aa|VALUE_STRING|aaa
list2[0].bb|VALUE_STRING|bbb
list2[1].aa|VALUE_STRING|aaa2
list2[1].bb|VALUE_STRING|bbb2

