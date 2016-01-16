
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

## Typedef: `Equal`
