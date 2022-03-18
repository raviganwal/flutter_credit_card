# Flutter Credit Card

A Flutter package allows you to easily implement the Credit card's UI easily with the Card detection.

## Preview

![ezgif-5-f5ac97be7d](https://user-images.githubusercontent.com/22388017/159047691-b30e4fd9-f5a8-4180-b7db-eea093a904e1.gif)

## Installing

1.  Add dependency to `pubspec.yaml`

    *Get the latest version in the 'Installing' tab on pub.dartlang.org*
    
```dart
dependencies:
    flutter_credit_card: <latest_version>
```

2.  Import the package
```dart
import 'package:flutter_credit_card/flutter_credit_card.dart';
```

3.  Adding CreditCardWidget

*With required parameters*
```dart
    CreditCardWidget(
        cardNumber: cardNumber,
        expiryDate: expiryDate, 
        cardHolderName: cardHolderName,
        cvvCode: cvvCode,
        showBackView: isCvvFocused, //true when you want to show cvv(back) view
    ),
```    

*With optional parameters*
```dart   
    CreditCardWidget(
        cardNumber: cardNumber,
        expiryDate: expiryDate,
        cardHolderName: cardHolderName,
        cvvCode: cvvCode,
        showBackView: isCvvFocused,
        cardbgColor: Colors.black,
        glassmorphismConfig: Glassmorphism.defaultConfig(),
        backgroundImage: 'assets/card_bg.png',
        obscureCardNumber: true,
        obscureCardCvv: true,
        isHolderNameVisible: false,
        height: 175,
        textStyle: TextStyle(color: Colors.yellowAccent),
        width: MediaQuery.of(context).size.width,
        isChipVisible: true,
        isSwipeGestureEnabled: true,
        animationDuration: Duration(milliseconds: 1000),
        customCardIcons: <CustomCardTypeImage>[
                    CustomCardTypeImage(
                      cardType: CardType.mastercard,
                      cardImage: Image.asset(
                        'assets/mastercard.png',
                        height: 48,
                        width: 48,
                      ),
                    ),
                  ],
    ),
``` 

*Glassmorphism UI*

 + Default configuration
```dart
    CreditCardWidget(
        glassmorphismConfig: Glassmorphism.defaultConfig(),
    ),
```    

 + Custom configuration
```dart
    CreditCardWidget(
        glassmorphismConfig: Glassmorphism(
          blurX: 10.0,
          blurY: 10.0,
          gradient: LinearGradient(
            begin: Alignment.topLeft,
            end: Alignment.bottomRight,
            colors: <Color>[
              Colors.grey.withAlpha(20),
              Colors.white.withAlpha(20),
            ],
            stops: const <double>[
              0.3,
              0,
            ],
          ),
        ),
    ),
```    

4.  Adding CreditCardForm

```dart
    CreditCardForm(
      formKey: formKey, // Required 
      onCreditCardModelChange: (CreditCardModel data) {}, // Required
      themeColor: Colors.red,
      obscureCvv: true, 
      obscureNumber: true,
      isHolderNameVisible: false,
      isCardNumberVisible: false,
      isExpiryDateVisible: false,
      cardNumberDecoration: const InputDecoration(
        border: OutlineInputBorder(),
        labelText: 'Number',
        hintText: 'XXXX XXXX XXXX XXXX',
      ),
      expiryDateDecoration: const InputDecoration(
        border: OutlineInputBorder(),
        labelText: 'Expired Date',
        hintText: 'XX/XX',
      ),
      cvvCodeDecoration: const InputDecoration(
        border: OutlineInputBorder(),
        labelText: 'CVV',
        hintText: 'XXX',
      ),
      cardHolderDecoration: const InputDecoration(
        border: OutlineInputBorder(),
        labelText: 'Card Holder',
      ),
    ),
```


## How to use
Check out the **example** app in the [example](example) directory or the 'Example' tab on pub.dartlang.org for a more complete example.

## Credit

This package's animation is inspired from from this [Dribbble](https://dribbble.com/shots/2187649-Credit-card-Checkout-flow-AMEX) art.

<br/>