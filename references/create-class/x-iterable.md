
# create-class

## Template Class: XIterable

```
template <class Super>
class XIterable : Super {
	public void forEach(JSFunction<void, void, any element, XIterable<Super> self> callback);
	public JSArray<any> map(JSFunction<any response, void, any element, XIterable<Super> self> callback);
	public bool some(JSFunction<bool stop, void, any element, XIterable<Super> self> callback);
	public bool every(JSFunction<bool next, void, any element, XIterable<Super> self> callback);
	public filter(JSFunction<bool keep, void, any element, XIterable<Super> self> callback);
	public any most(JSFunction<bool closer, void, any element, XIterable<Super> self> callback);
	public get JSNumber min, max;
}
```
