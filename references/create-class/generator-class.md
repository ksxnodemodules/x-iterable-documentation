
# create-class

## GeneratorClass

```
template <JSGenerator gen>
class GeneratorClassBase {
	public constructor(any ...);
	public ReturnValue<gen> [Symbol.iterator]();
}
template <class gen>
alias GeneratorClass = SubClass<XIterable<GeneratorClassBase<gen>>>;
```
