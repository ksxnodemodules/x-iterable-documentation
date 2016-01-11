
# parallel-iterable

 * See also:
  - [`Stop`](./parallel-iterable-base.md#typedef-stop)
  - [`JSIterable`](../global/readme.md#struct-jsiterable)

```
class ParallelIterableBase {
	public constructor(Stop stop, JSIterable<any> ...iterables);
	public JSIterator<JSArray<any>> [Symbol.iterator]();
	public static const Stop END_OF_FIRST;
	public static const Stop END_OF_ALL;
	public static const Stop END_OF_SOME;
	public static Stop FOR_COUNT(unsigned int count);
}
```

### Constructor

#### Parameter `stop`

 * Type: `Stop`

 * This parameter is required

If `stop([...elements], iterable)` returns `true`, the iteration would stop

#### Rest parameter `iterables`

 * Type: `JSIterable<any>`

 * Contains at least 1 element

### Enum function `ParallelIterableBase.END_OF_FIRST`

 * Type: `Stop`

Returns `true` when the first iterable of `iterables` has finished

### Enum function `ParallelIterableBase.END_OF_ALL`

 * Type: `Stop`

Returns `true` when all iterables of `iterables` have finished

### Enum function `ParallelIterableBase.END_OF_SOME`

 * Type: `Stop`

Returns `true` when any iterables of `iterables` have finished

### Function `ParallelIterableBase.FOR_COUNT`

```
Stop ParallelIterableBase.FOR_COUNT(unsigned int count);
```

Returns a `Stop` which determines how many times does iterating

## Typedef `Stop`

```
typedef JSFunction<bool, ParallelIterable, JSArray<any>, ParallelIterable> Stop;
```
