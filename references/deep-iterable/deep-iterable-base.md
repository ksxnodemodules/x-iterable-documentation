
# deep-iterable

## Class: `DeepIterableBase`

 * See also:
  - [`Deeper`](./deep-iterable-base.md#typedef-deeper)
  - [`DeepIterableTarget`](./deep-iterable-base.md#template-either-deepiterabletarget)

```
class DeepIterableBase {
	public constructor(DeepIterableTarget<any> target, Deeper deeper = DeepIterableBase.DEFAULT_DEEPER);
	public JSIterator<any> [Symbol.iterator]();
}
```

### Constructor

Constructor takes 1 or 2 parameters: an iterable object called `target` and a function called `deeper`

#### Parameter `target`

 * Type: `DeepIterableTarget<any>`

 * This parameter is required

#### Parameter `deeper`

 * Type: `Deeper`

 * This parameter is optional, constructor would use `DeepIterable.DEFAULT_DEEPER` if this parameter is not specified

`deeper` is a function which would take 2 parameters (See 'Type' above).

If `deeper(...)` returns `true`, iteration process would go deeper

### Enum function `DeepIterableBase.OBJECT_DEEPER`

 * Type: `bool (DeepIterableTarget<any> target, DeepIterable)`
  - a.k.a. `Deeper`

Returns `true` if `target` is both an object and an iterable

### Enum function `DeepIterableBase.CIRCULAR_DEEPER`

 * Type: `bool (DeepIterableTarget<any> target, DeepIterable)`
  - a.k.a. `Deeper`

Returns `true` if `target` is an iterable value which is passed to this function for the first time

It's good to use to iterate *circular* object/value (e.g. strings, circular arrays ...)

### Enum function `DeepIterableBase.DEFAULT_DEEPER`

```
Deeper DeepIterableBase.DEFAULT_DEEPER = OBJECT_DEEPER;
```

## Typedef: `Deeper`

```
typedef JSFunction<bool, void, DeepIterableTarget<any>, DeepIterable> Deeper;
```

## Template Either `DeepIterableTarget`

 * See also:
  - [`JSIterable`](../global/readme.md#struct-jsiterable)

```
template <class Element>
either {
	JSIterable<Element>,
	JSIterable<DeepIterableTarget<Element>>
}
```
