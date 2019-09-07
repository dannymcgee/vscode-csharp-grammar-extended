# C# Grammar Extended

This extension aims to improve the default C# grammar that comes with VS Code by making it more accurate and granular.

**Features**
* In object creation expressions (e.g., `new Foo()`), the object name is tokenized as a class name (`entity.name.type.class.cs`)
* Enum access expressions (e.g., `Foo.Bar`) receive more accurate tokenization if they're cased according to standard conventions (PascalCase for the enum and its members) (`entity.name.type.enum.cs` for the enum, and `entity.name.variable.enum-member.cs` for the member)
* In object access expressions (e.g., `foo.bar.Baz()`), the object name will be tokenized as a static class if PascalCase (`entity.name.class.static.cs`)
* Numeric constants receive more granular tokenization:
	* Decimal points are tokenized as punctuation (`punctuation.separator.decimal.cs`)
	* Type suffixes (e.g., the `f` in `3.141f`) are tokenized as keywords (`keyword.numeric.type.cs`)
	* Exponent prefixes (e.g., the `e` in `3e10`) are tokenized as keywords (`keyword.numeric.exponent.cs`)