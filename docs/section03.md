## How to use

Example:

```python
from smalldict import SmallDict

d = {
    "key_1": ["value_1", "value_2", "value_3"],
    "key_2": {"key_1": "value", "key_2": "value", "key_3": "value"},
    "key_3": "value",
}


def test_no_limit():
    assert SmallDict(d).get() == d


def test_limit():
    assert SmallDict(d).get(
        dict_limit=2, list_limit=1, str_limit=3, json_out=None, yaml_out=None
    ) == {
        "key_1": ["val"],
        "key_2": {"key_1": "val", "key_2": "val"},
    }
```

JSON/YAML file input/output is supported.
- Input: Specify the path, either JSON (`.json`) or YAML (`.yaml`, `.yml`), as `d` argument for `SmallDict`.
- Output: Specify the path as `json_out` or `yaml_out` argument for `SmallDict.get` method.
