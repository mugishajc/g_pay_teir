# Google Pay Test App

A small Kotlin Android app for trying out the Google Pay API end to end: it checks whether Google Pay is available on the device, builds a payment request and runs a checkout in the test environment.

## Stack

- Kotlin, AndroidX, ViewModel + LiveData
- Google Play Services Wallet (Google Pay API)

## How it works

- `util/PaymentsUtil.kt` builds the `IsReadyToPayRequest` and `PaymentDataRequest` JSON (allowed card networks, auth methods, tokenization spec, transaction info).
- `viewmodel/CheckoutViewModel.kt` checks whether the user can pay and starts the payment.
- `CheckoutActivity.kt` shows the Google Pay button and handles the result.
- `Constants.kt` holds the environment (`ENVIRONMENT_TEST`), country, currency and gateway settings.

## Running

1. Open in Android Studio.
2. In `Constants.kt`, set your gateway name and merchant ID, or a direct tokenization public key.
3. Run on a device signed in to a Google account. Test mode needs no real card.
