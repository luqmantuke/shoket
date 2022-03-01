# Shoket Flutter Wrapper

A simple Flutter wrapper for the shoket payment API, for more information on the API visit [Shoket Official website](https://developers.shoket.co/).

## Getting Started

### Prerequisites

- Ensure you have your API keys.

### Installation

- Add the dependency

In your pubspec.yaml file add:

```shell

shoket: 0.0.1
run flutter pub get


```

### Usage

1. Create a Shocket instance by calling the constructor Shoket() The constructor accepts an API KEY as parameter
   It returns an instance of Shoket which we then call the async method .charge() or .verify() on.

```js
final shoket = Shoket(apiKey: "apiKey");

```

2. create a payment object with the payment details

```js
var paymentDetails = Payment(
                      amount: "1000",
                      customerName: "John DOe",
                      email: "johndoe@gmail.com",
                      numberUsed: "0717000000",
                      channel: "halotel");

```

3. Get the response by calling .charge() method passing paymentDetails oject as paramenter. NOTE chargeresponse can be null

```js
final ChargeResponse? response = await shoket.charge();

```

4. Handle the response

```js
if (response == null) {
  // the transaction failed
} else {
  var status = response.status;
  if (status == "success") {
    // provide value to customer
  } else {
    // check message
    print(response.message);
  }
}
```

## Contributing

Please see [CONTRIBUTING](CODE_OF_CONDUCT.md) for details.

## Credits

- [Alex Rossi](https://github.com/burnwood1911)

## License

This project is licensed under the [MIT](LICENSE.md) License.
