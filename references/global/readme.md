
# Global specs

## Struct: `JSIterable`

 * See also:
  - [iterable object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#Iterables)
  - [`for...of` loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)

An iterable object is an object which is able to use [`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of) to iterate

An iterable class is a class which is used to create iterable objects

```
template <class Target>
struct JSIterable {
	public JSIterator<Target> [Symbol.iterator]();
}
```

### Examples

`Array` is an iterable class
```javascript
for (let element of [0, 1, 2, 3, 4]) {
	console.log(element);
}
```

## Template Struct: `JSIterator`

 * Also known as [generator object](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Generator)
 * See also:
  - [Template Struct: `JSIteratorReturn`](./readme.md#template-struct-jsiteratorreturn)

An iterator is an object which is returned by a [generator function](./readme.md#template-function-generator)

```
template <class Target>
struct JSIterator {
	public JSIteratorReturn<Target> next();
	public JSIteratorReturn<Target> return(Target value);
	optional public void throw(Error exception);
}
```

## Template Struct: `JSIteratorReturn`

```
template <class Value>
struct JSIteratorReturn {
	public [[out]] bool done;
	public [[out]] Value value;
}
```

## Template Either: `Yieldable`

A `Yieldable` object is an object which is able to use [operator `yield *`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/yield*) to iterate within a [`function *`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*)

```
template <class Target>
either Yieldable {
	Iterable<Target>,
	JSIterator<Target>
}
```

## Set: `Falsy`

 * See also:
  - [Falsy](https://developer.mozilla.org/vi/docs/Glossary/Falsy)

```
set Falsy {
	undefined,
	null,
	false,
	'',
	0,
	NaN
}
```

## Set: `Truthy`

 * See also:
  - [Truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)

```
set Truthy {
	exclude<JSObject, null>,
	exclude<JSString, ''>,
	true,
	exclude<JSNumber, either {0, NaN}>,
	JSFunction<any ...>
}
```
