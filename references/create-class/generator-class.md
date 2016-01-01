
# create-class

## GeneratorClass

```
template <JSGenerator gen>
class GeneratorClassBase {
	public constructor(any ...);
	public JSIterator<any> [Symbol.iterator]();
}
template <class gen>
class GeneratorClass = XIterable<GeneratorClassBase<gen>>;
```
