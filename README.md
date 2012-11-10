TransformerKit
==============

**Transforming Ordinary Code into Awesomesauce**

[`NSValueTransformer`](https://developer.apple.com/library/mac/#documentation/Cocoa/Reference/Foundation/Classes/NSValueTransformer_Class/Reference/Reference.html), while somewhat obscure to most iOS programmers, remains a mainstay of OS X development. Before Objective-C APIs got in the habit of flinging block parameters hither and thither with reckless abandon, `NSValueTransformer` was the go-to way to encapsulate mutation functionality--especially when it came to Bindings.

`NSValueTransformer` is convenient to use, but a pain to set up. Creating even a trivial value transformer required creating of its own subclass, implementing the handful of required methods, and registering a singleton instance by name.

TransformerKit breathes new life into `NSValueTransformer`, by making them dead-simple to define and register:

```objective-c
NSString * const TKCapitalizedStringTransformerName = @"TKCapitalizedStringTransformerName";

[NSValueTransformer registerValueTransformerWithName:TKCapitalizedStringTransformerName 
                               transformedValueClass:[NSString class] 
                  returningTransformedValueWithBlock:^id(id value) {
  return [value capitalizedString];
}];
```

TransformerKit also contains a _growing_ number of convenient transformers that your apps will love and cherish:

### String Transformers

- Capitalized
- UPPERCASE
- lowercase
- CamelCase
- llamaCase
- snake_case
- train-case
- desreveR _(Reverse)_
- Rémövê Dîaçritics _(Remove accents and combining marks)
- ट्रांस्लितेराते स्ट्रिंग _(Transliterate to Latin)_

## Contact

Mattt Thompson

- http://github.com/mattt
- http://twitter.com/mattt
- m@mattt.me

## License

TransformerKit is available under the MIT license. See the LICENSE file for more info.