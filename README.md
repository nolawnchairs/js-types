
# Types Package

This package contains type definitions for various function signatures. When imported, these types are added to the global scope.

## Installation

```bash
npm install @nolawnchairs/types

# Or.... (see caveats below)
npm install -D @nolawnchairs/types
```

## Usage

Import the package in your code once, preferably in your main entry point:

```typescript
import '@nolawnchairs/types'
```

## Caveats

If installing as a development dependency, be aware that when installing as a production build via `npm install --production` or `npm ci --only=production`, any dev dependencies will not be installed. This will cause imports of this package to fail. To avoid this, install this package as a production dependency.

## API

The API is simple the contents of the `index.d.ts` file:

```typescript

/**
 * Represents a value that may be null or undefined.
 * @template T the type of the value
 */
type Nullable<T> = T | null | undefined

/**
 * Represents a function that accepts one argument and produces a result.
 * @template T the parameter type
 * @template U the return type
 */
interface UnaryFunction<T, U> {
  (value: T): U
}

/**
 * Represents a function that accepts one argument and produces a result
 * that may be null or undefined.
 * @template T the parameter type
 * @template U the return type
 */
interface NullableUnaryFunction<T, U> {
  (value: T): Nullable<U>
}

/**
 * Represents a function that accepts one argument and produces a result asynchronously.
 * @template T the parameter type
 * @template U the return type
 */
interface AsyncUnaryFunction<T, U> {
  (value: T): Promise<U>
}

/**
 * Represents a function that accepts one argument and produces a result
 * that may be null or undefined asynchronously.
 * @template T the parameter type
 * @template U the return type
 */
interface NullableAsyncUnaryFunction<T, U> {
  (value: T): Promise<Nullable<U>>
}

/**
 * Represents a function that accepts one optional argument and produces a result.
 * @template T the parameter type
 * @template U the return type
 */
interface OptionalUnaryFunction<T, U> {
  (value?: T): U
}

/**
 * Represents a function that accepts one optional argument and produces a result
 * that may be null or undefined asynchronously.
 * @template T the parameter type
 * @template U the return type
 */
interface OptionalAsyncUnaryFunction<T, U> {
  (value?: T): Promise<U>
}

/**
 * Represents a function that accepts two arguments and produces a result.
 * @template T the first argument type
 * @template U the second argument type
 * @template R the return type
 */
interface BiFunction<T, U, R> {
  (value1: T, value2: U): R
}
/**
 * Represents a function that accepts two arguments and produces a result
 * that may be null or undefined.
 * @template T the first argument type
 * @template U the second argument type
 * @template R the return type
 */
interface NullableBiFunction<T, U, R> {
  (value1: T, value2: U): Nullable<R>
}

/**
 * Represents a function that accepts two arguments and produces a result asynchronously.
 * @template T the first argument type
 * @template U the second argument type
 */
interface AsyncBiFunction<T, U, R> {
  (value1: T, value2: U): Promise<R>
}

/**
 * Represents a function that accepts two arguments and produces a result
 * that may be null or undefined asynchronously.
 * @template T the first argument type
 * @template U the second argument type
 * @template R the return type
 */
interface NullableAsyncBiFunction<T, U, R> {
  (value1: T, value2: U): Promise<Nullable<R>>
}

/**
 * Represents a function that accepts two optional arguments and produces a result asynchronously.
 * @template T the first argument type
 * @template U the second argument type
 * @template R the return type
 */
interface OptionalBiFunction<T, U, R> {
  (value1?: T, value2?: U): R
}

/**
 * Represents a function that accepts two optional arguments and produces a result
 * that may be null or undefined asynchronously.
 * @template T the first argument type
 * @template U the second argument type
 * @template R the return type
 */
interface OptionalAsyncBiFunction<T, U, R> {
  (value1?: T, value2?: U): Promise<R>
}

/**
 * Represents a supplier of a result.
 * @template T the return type
 */
interface Supplier<T> {
  (): T
}

/**
 * Represents a supplier of a result that may be null or undefined.
 * @template T the return type
 */
interface NullableSupplier<T> {
  (): Nullable<T>
}

/**
 * Represents a supplier of a promise.
 * @template T the return type
 */
interface AsyncSupplier<T> {
  (): Promise<T>
}

/**
 * Represents a supplier of a promise whose resolved value may be
 * null or undefinded.
 * @template T the return type
 */
interface NullableAsyncSupplier<T> {
  (): Promise<Nullable<T>>
}

/**
 * Represents an operation that accepts a single input argument
 * and returns no result.
 * @template T the argument type
 */
interface Consumer<T> {
  (value: T): void
}

/**
 * Represents an operation that accepts a single input argument
 * and returns no result asynchronously.
 * @template T the argument type
 */
interface AsyncConsumer<T> {
  (value: T): Promise<void>
}

/**
 * Represents an operation that accepts a single optional input argument
 * and returns no result.
 * @template T the argument type
 */
interface OptionalConsumer<T> {
  (value?: T): void
}

/**
 * Represents an operation that accepts a single optional input argument
 * and returns no result asynchronously.
 * @template T the argument type
 */
interface OptionalAsyncConsumer<T> {
  (value?: T): Promise<void>
}

/**
 * Represents an operation that accepts two input arguments and returns no result.
 * @template T the first argument type
 * @template U the second argument type
 */
interface BiConsumer<T, U> {
  (value1: T, value2: U): void
}

/**
 * Represents an operation that accepts a optional arguments and returns no result.
 * @template T the first argument type
 * @template U the second argument type
 */
interface OptionalBiConsumer<T, U> {
  (value1?: T, value2?: U): void
}

/**
 * Represents an operation that accepts two input arguments and returns no result asynchronously.
 * @template T the first argument type
 * @template U the second argument type
 */
interface OptionalAsyncBiConsumer<T, U> {
  (value1?: T, value2?: U): Promise<void>
}

/**
 * Represents an operation on a single operand that produces a
 * result of the same type as its operand.
 * @template T the type of the operand and return type
 */
interface UnaryOperator<T> {
  (value: T): T
}

/**
 * Represents an operation on a single operand that produces an optional
 * result of the same type as its operand.
 * @template T the type of the operand and return type
 */
interface NullableUnaryOperator<T> {
  (value: T): Nullable<T>
}

/**
 * Represents an asynchronous operation on a single operand that produces a
 * result of the same type as its operand.
 * @template T the type of the operand and return type
 */
interface AsyncUnaryOperator<T> {
  (value: T): Promise<T>
}

/**
 * Represents an asynchronous operation on a single operand that produces an optional
 * result of the same type as its operand.
 * @template T the type of the operand and return type
 */
interface NullableAsyncUnaryOperator<T> {
  (value: T): Promise<Nullable<T>>
}

/**
 * Represents an operation upon two operands of the same type,
 * producing a result of the same type as the operands.
 * @template T the type of the operands and return type
 */
interface BinaryOperator<T> {
  (value1: T, value2: T): T
}

/**
 * Represents an asynchronous operation upon two operands of the same type,
 * producing a result of the same type as the operands.
 * @template T the type of the operands and return type
 */
interface AsyncBinaryOperator<T> {
  (value1: T, value2: T): Promise<T>
}

/**
 * Represents an operation upon two operands of the same type,
 * producing an optional result of the same type as the operands.
 * @template T the type of the operands and return type
 */
interface OptionalBinaryOperator<T> {
  (value1?: T, value2?: T): T
}

/**
 * Represents an operation upon two operands of the same type,
 * producing an optional result of the same type as the operands.
 * @template T the type of the operands and return type
 */
interface NullableBinaryOperator<T> {
  (value1: T, value2: T): Nullable<T>
}

/**
 * Represents an asynchronous operation upon two operands of the same type,
 * producing an optional result of the same type as the operands.
 * @template T the type of the operands and return type
 */
interface NullableAsyncBinaryOperator<T> {
  (value1: T, value2: T): Promise<Nullable<T>>
}

/**
 * Represents a predicate operation that takes a single argument.
 * @template T the argument type
 */
interface Predicate<T> {
  (value: T): boolean
}

/**
 * Represents an asynchronous predicate operation that takes a single argument.
 * @template T the argument type
 */
interface AsyncPredicate<T> {
  (value: T): Promise<boolean>
}

/**
 * Represents a predicate operation that takes a single optional argument.
 * @template T the argument type
 */
interface OptionalPredicate<T> {
  (value?: T): boolean
}

/**
 * Represents a predicate operation that takes two arguments.
 * @template T the first argument type
 * @template U the second argument type
 */
interface BiPredicate<T, U> {
  (value1: T, value2: U): boolean
}

/**
 * Represents an asynchronous predicate operation that takes two arguments.
 * @template T the first argument type
 * @template U the second argument type
 */
interface AsyncBiPredicate<T, U> {
  (value1: T, value2: U): Promise<boolean>
}

/**
 * Represents a predicate operation that takes two optional arguments.
 * @template T the first argument type
 * @template U the second argument type
 */
interface OptionalBiPredicate<T, U> {
  (value1?: T, value2?: U): boolean
}

/**
 * Represents an asynchronous predicate operation that takes two optional arguments.
 * @template T the first argument type
 * @template U the second argument type
 */
interface AsyncOptionalBiPredicate<T, U> {
  (value1?: T, value2?: U): Promise<boolean>
}

/**
 * Represents an operation that compares two operands of the same type
 * and produces a number (integer) for comparison purposes
 * @template T the argument type
 */
type Comparator<T> = BiFunction<T, T, number>

/**
 * Represents an operation that compares two operands of the same type
 * and produces a boolean result for comparison purposes
 * @template T the argument type
 */
type EqualityOperator<T> = BiFunction<T, T, boolean>
```