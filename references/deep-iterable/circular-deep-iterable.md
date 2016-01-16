
# deep-iterable

## Class: `CircularDeepIterable`

 * See also:
  - [`CircularDeepIterableBase`](./circular-deep-iterable.md#class-circulardeepiterablebase)

```
class CircularDeepIterable = XIterable<CircularDeepIterableBase>;
```

## Class: `CircularDeepIterableBase`

 * See also:
  - [`DeepIterableTarget`](./deep-iterable-base.md#template-either-deepiterabletarget)
  - [`Deeper`](./deep-iterable-base.md#typedef-deeper)
  - [`Equal`](./circular-deep-iterable.md#typedef-equal)
  - [`Circular`](./circular-deep-iterable.md#typedef-circular)

```
class CircularDeepIterableBase {
	public constructor(DeepIterableTarget<any> target, Deeper deeper = DeepIterableBase.DEFAULT_DEEPER, Equal equal = Object.is, Circular circular = CircularDeepIterableBase.DEFAULT_CIRCULAR_HANDLER);
	public static const Circular DEFAULT_CIRCULAR_HANDLER;
}
```

### Constructor

Constructor takes 1 up-to 4 parameters

#### Parameter `target`

Similar to [this](./deep-iterable-base.md#parameter-target)

#### Parameter `deeper`

Similar to [this](./deep-iterable-base.md#parameter-deeper)

#### Parameter `equal`

 * Type: [`Equal`](./circular-deep-iterable.md#typedef-equal)

 * This parameter is optional, constructor would use [`Object.is`](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Object/is) is this parameter is not specified

Determines if two parameters are the same to avoid circular iteration

#### Parameter `circular`

 * Type [`Circular`](./circular-deep-iterable.md#typedef-circular)

 * This parameter is optional, constructor would use [`CircularDeepIterableBase.DEFAULT_CIRCULAR_HANDLER`](./circular-deep-iterable.md#enum-function-circulardeepiterabledefault_circular_handle) is this parameter is not specified

Handles 'duplicated' values

Returns an iterable or `undefined`

## Typedef: `Equal`

```
typedef JSFunction<bool, void, DeepIterableTarget<any>, DeepIterableTarget<any>> Equal;
```

## Typedef: `Circular`

 * See also:
  - [`Falsy`](../global/readme.md#set-falsy)

```
typedef JSFunction<either {Iterable<any>, Falsy}, void, DeepIterableTarget<any>, CircularDeepIterable> Circular;
```
