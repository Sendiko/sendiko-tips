### Useful Error States

this is states that can be used to mark different error type and messages.

#### ErrorTextField

```kotlin 
/**
 *
 * Error States for TextField.
 *
 * @param isError to pass to TextField's isError.
 * @param errorMessage can be passed to TextField's supportingText.
 * 
 * */
data class ErrorTextField(
    val isError: Boolean = false,
    val errorMessage: String = "",
)
```
<br>

#### RequestFailed

```kotlin
/**
 *
 * Used mainly with retrofit, to notify the UI that the request has failed.
 *
 * @param isFailed set to true when request failed.
 * @param failedMessage message to show about why the request has failed.
 * 
 * */
data class FailedRequest(
    val isFailed: Boolean = false,
    val failedMessage: String = "",
)
```