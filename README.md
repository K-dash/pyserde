# `pyserde`

Yet another serialization library on top of [dataclasses](https://docs.python.org/3/library/dataclasses.html), inspired by [serde-rs](https://github.com/serde-rs/serde).

[![image](https://img.shields.io/pypi/v/pyserde.svg)](https://pypi.org/project/pyserde/)
[![image](https://img.shields.io/pypi/pyversions/pyserde.svg)](https://pypi.org/project/pyserde/)
![Tests](https://github.com/yukinarit/pyserde/workflows/Tests/badge.svg)
[![codecov](https://codecov.io/gh/yukinarit/pyserde/branch/master/graph/badge.svg)](https://codecov.io/gh/yukinarit/pyserde)

[Guide](https://yukinarit.github.io/pyserde/guide) | [API Docs](https://yukinarit.github.io/pyserde/api/serde.html) | [Examples](./examples)

## Overview

Declare a class with pyserde's `@serde` decorator.

```python
@serde
@dataclass
class Foo:
    i: int
    s: str
    f: float
    b: bool
```

You can serialize `Foo` object into JSON.

```python
>>> to_json(Foo(i=10, s='foo', f=100.0, b=True))
'{"i":10,"s":"foo","f":100.0,"b":true}'
```

You can deserialize JSON into `Foo` object.
```python
>>> from_json(Foo, '{"i": 10, "s": "foo", "f": 100.0, "b": true}')
Foo(i=10, s='foo', f=100.0, b=True)
```

## Features

- Supported data formats
    - dict
    - tuple
    - JSON
	- Yaml
	- Toml
	- MsgPack
- Supported types
    - Primitives (`int`, `float`, `str`, `bool`)
    - Containers (`List`, `Set`, `Tuple`, `Dict`)
    - [`typing.Optional`](https://docs.python.org/3/library/typing.html#typing.Optional)
    - [`typing.Union`](https://docs.python.org/3/library/typing.html#typing.Union)
    - User defined class with [`@dataclass`](https://docs.python.org/3/library/dataclasses.html)
    - [`typing.NewType`](https://docs.python.org/3/library/typing.html#newtype) for primitive types
    - [`typing.Any`](https://docs.python.org/3/library/typing.html#the-any-type)
    - [`typing.Generic`](https://docs.python.org/3/library/typing.html#user-defined-generic-types)
    - [`Enum`](https://docs.python.org/3/library/enum.html#enum.Enum) and [`IntEnum`](https://docs.python.org/3/library/enum.html#enum.IntEnum)
    - Standard library
        - [`pathlib.Path`](https://docs.python.org/3/library/pathlib.html)
        - [`decimal.Decimal`](https://docs.python.org/3/library/decimal.html)
        - [`uuid.UUID`](https://docs.python.org/3/library/uuid.html)
        - [`datetime.date`](https://docs.python.org/3/library/datetime.html#date-objects), [`datetime.time`](https://docs.python.org/3/library/datetime.html#time-objects), [`datetime.datetime`](https://docs.python.org/3/library/datetime.html#datetime-objects)
        - [`ipaddress`](https://docs.python.org/3/library/ipaddress.html)
    - PyPI library
        - [`numpy`](https://github.com/numpy/numpy) types
- [Attributes](docs/features/attributes.md)
- [Decorators](docs/features/decorators.md)
- [TypeCheck](docs/features/type-check.md)
- [Union Representation](docs/features/union.md)
- [Python 3.10 Union operator](docs/features/union-operator.md)
- [Python 3.9 type hinting](docs/features/python3.9-type-hinting.md)
- [Postponed evaluation of type annotation](docs/features/postponed-evaluation-of-type-annotation.md)
- [Forward reference](docs/features/forward-reference.md)
- [Case Conversion](docs/features/case-conversion.md)
- [Rename](docs/features/rename.md)
- [Skip](docs/features/skip.md)
- [Conditional Skip](docs/features/conditional-skip.md)
- [Custom field (de)serializer](docs/features/custom-field-serializer.md)
- [Custom class (de)serializer](docs/features/custom-class-serializer.md)
- [Flatten](docs/features/flatten.md)

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tbody>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/yukinarit"><img src="https://avatars.githubusercontent.com/u/2347533?v=4?s=100" width="100px;" alt="yukinarit"/><br /><sub><b>yukinarit</b></sub></a><br /><a href="https://github.com/yukinarit/pyserde/commits?author=yukinarit" title="Code">💻</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/alexmisk"><img src="https://avatars.githubusercontent.com/u/4103218?v=4?s=100" width="100px;" alt="Alexander Miskaryan"/><br /><sub><b>Alexander Miskaryan</b></sub></a><br /><a href="https://github.com/yukinarit/pyserde/commits?author=alexmisk" title="Code">💻</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/ydylla"><img src="https://avatars.githubusercontent.com/u/17772145?v=4?s=100" width="100px;" alt="ydylla"/><br /><sub><b>ydylla</b></sub></a><br /><a href="https://github.com/yukinarit/pyserde/commits?author=ydylla" title="Code">💻</a></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td align="center" size="13px" colspan="7">
        <img src="https://raw.githubusercontent.com/all-contributors/all-contributors-cli/1b8533af435da9854653492b1327a23a4dbd0a10/assets/logo-small.svg">
          <a href="https://all-contributors.js.org/docs/en/bot/usage">Add your contributions</a>
        </img>
      </td>
    </tr>
  </tfoot>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!

## LICENSE

This project is licensed under the [MIT license](https://github.com/yukinarit/pyserde/blob/master/LICENSE).
