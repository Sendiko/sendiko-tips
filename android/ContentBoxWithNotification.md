### ContentBoxWithNotificaition

this is the snippet of the composable code that i made very beautifully. In addition to this snippet, also recommended to use ```LaunchedEffect``` to set and clear the state of ```ContentBoxWithNotificaition```.

#### Main Composables


```kotlin
/**
 * Sendiko's custom notification composables!.
 *
 * @param message for the message that will be shown in the notification.
 * @param isErrorNotification error notification will show with red color.
 * @param isLoading show loading indicator notification.
 * @param content for the screen content inside.
 *
 * */
@Composable
fun ContentBoxWithNotification(
    message: String,
    isErrorNotification: Boolean = false,
    isLoading: Boolean = false,
    content: @Composable (() -> Unit),
) {
    Box {
        content()
        Notification(
            message = message,
            isVisible = message.isNotBlank() && !isLoading,
            isErrorNotification = isErrorNotification
        )
        LoadingIndicator(isLoading = isLoading)
    }
}
```

<br>

#### Notification Composables

```kotlin
/**
 *
 * The notification that will be shown.
 *
 * @param message the message that will be shown.
 * @param isVisible when the notification comes up.
 * @param isErrorNotification shown red notification.
 *
 * */
@Composable
fun Notification(
    message: String,
    isVisible: Boolean,
    isErrorNotification: Boolean = false,
) {
    AnimatedVisibility(
        visible = isVisible,
        enter = expandVertically(),
        exit = shrinkVertically()
    ) {
        Box(
            modifier = Modifier
                .fillMaxWidth()
                .background(if (isErrorNotification) MaterialTheme.colorScheme.error else MaterialTheme.colorScheme.surfaceVariant),
            content = {
                Text(
                    text = message,
                    modifier = Modifier.padding(top = 28.dp + 8.dp, end = 8.dp, start = 8.dp, bottom = 16.dp),
                    color = if (isErrorNotification) MaterialTheme.colorScheme.onError else MaterialTheme.colorScheme.onSurfaceVariant,
                    fontFamily = nunitoFont
                )
            }
        )
    }
}
```

<br>

#### Loading indicator
```kotlin
/**
 * 
 * The loading indicator
 * 
 * @param isLoading to determine if loading indicator should show.
 * 
 * */
@Composable
fun LoadingIndicator(
    isLoading: Boolean,
) {
    AnimatedVisibility(
        visible = isLoading,
        enter = expandVertically(),
        exit = shrinkVertically()
    ) {
        Box(
            modifier = Modifier
                .fillMaxWidth()
                .background(MaterialTheme.colorScheme.tertiaryContainer),
            content = {
                Row(
                    modifier = Modifier.padding(top = 28.dp + 8.dp, end = 8.dp, start = 8.dp, bottom = 16.dp),
                    verticalAlignment = Alignment.CenterVertically
                ) {
                    Text(
                        text = "Loading",
                        color = MaterialTheme.colorScheme.onTertiaryContainer,
                        fontFamily = nunitoFont
                    )
                    Spacer(modifier = Modifier.width(8.dp))
                    CircularProgressIndicator(modifier = Modifier.size(24.dp), strokeWidth = 1.dp)
                }
            }
        )
    }
}
```