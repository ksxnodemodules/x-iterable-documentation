
# deep-iterable

## Class: `DeepIterableBase`

 * See also:
  - [`Deeper`](./deep-iterable-base.md#typedef-deeper)
  - [`DeepIterableTarget`](./deep-iterable-base.md#template-either-deepiterabletarget)

```
class DeepIterableBase {
	public constructor(DeepIterableTarget<any> target, Deeper deeper = DeepIterableBase.DEFAULT_DEEPER);
	public JSIterator<any> [Symbol.iterator]();
	public static Deeper ANY_DEEPER;
	public static Deeper OBJECT_DEEPER;
	public static Deeper LENGTHINESS_DEEPER;
	public static Deeper DEFAULT_DEEPER = OBJECT_DEEPER;
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

If `element` is an iterable and `deeper(element, ...)` returns `true`, iteration process would go deeper: iterate `element` as a `DeepIterable` using the same `deeper`

### Enum function `DeepIterableBase.ANY_DEEPER`

 * Type: `bool (DeepIterableTarget<any>, DeepIterable)`
  - a.k.a. `Deeper`

Always returns `true`

### Enum function `DeepIterableBase.OBJECT_DEEPER`

 * Type: `bool (DeepIterableTarget<any> target, DeepIterable)`
  - a.k.a. `Deeper`

Returns `true` if `target` is an object

### Enum function `DeepIterableBase.LENGTHINESS_DEEPER`

 * Type: `bool (DeepIterableTarget<any> target, DeepIterable)`
  - a.k.a. `Deeper`

Returns `true` if `target` has property `length` greater than 1

It means that the iteration process would not go deeper if the iterable has no elements or has only one element

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
