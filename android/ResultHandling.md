### Result Handling

this could be a way for me to implement result handling better

```kotlin

sealed interface Error

typealias Errors = Error

sealed interface Result<out D, out E: Errors> {
    data class Success<out D, out E: Errors>(val data: D): Result<D, E>
    data class Error<out D, out E: Errors>(val error: E): Result<D, E>
}

```