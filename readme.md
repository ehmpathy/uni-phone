# uni-phone

![test](https://github.com/ehmpathy/uni-phone/workflows/test/badge.svg)
![publish](https://github.com/ehmpathy/uni-phone/workflows/publish/badge.svg)

A glossary of intuitive, universally unambiguous phone domain literals.

# purpose

declare a universally unambiguous serialization format for phones
- `UniPhoneNumber` = [E.164](https://en.wikipedia.org/wiki/E.164)
- `UniPhone` = `{ number: UniPhoneNumber }`

usecases
- clarify the format a string should be in (`const phoneNumber: UniPhoneNumber = '+13231110101'`)
- cast date to universal format (`const phoneNumber: UniPhoneNumber = toUniPhoneNumber('(323) 111-0101')`)
- narrow type of strings with runtime validation (`if (!isUniPhoneNumber(input)) throw new Error('wrong format')`)


# install

```sh
npm install uni-phone
```

# use

## Phone

### declare that a phone or phone.number must be in the universal format

```ts
const phone: UniPhone;
const phoneNumber: UniPhoneNumber;
```


### assure that a phone number is in the universal phormat

```ts
const phone: UniPhone = { number: isUniPhoneNumber.assure('+13231110101') }
```


### cast a phone number into the universal format

```ts
const phone: UniPhone = { number: asUniPhoneNumber('(323) 111-0101') }
```
