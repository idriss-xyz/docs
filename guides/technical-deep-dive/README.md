---
description: How does IDriss work?
---

# Technical Deep Dive

IDriss registry lives on [Polygon](https://polygonscan.com/address/0x2eccb53ca2d4ef91a79213fddf3f8c2332c2a814). Our contract is verified, and anyone can view the source code [here](https://polygonscan.com/address/0x2eccb53ca2d4ef91a79213fddf3f8c2332c2a814#code). At its core, IDriss is made up of three mappings.

First, we generate a hash called _IDrissHash._ It is a hash of the identifier, an optional (and encouraged) password (secretWord) , and an additional hash identifying the chosen wallet tag. The identifier is either an email, phone number, or Twitter user ID (which does not change when changing your Twitter username).&#x20;

&#x20;$$\begin{align} &IDrissHash = sha256(identifier+password_{optional}+walletTag_{hash})  \\ \\ &IDrissHash_{verify}= sha256(IDrissHash+verifier_{key}) \\ \\ &IDrissHash \rightarrow IDrissHash_{verify}\end{align}$$​

To normalize the input variables, we provide a number of methods to follow before generating the hashes:

```python
def convertNumber(number):
    conv = re.sub(r'[^\d]+', '', number)
    return "+" + conv

def convertSecretWord(input_):
    input_ = re.sub(r'[^a-zA-Z]', '', input_)
    return input_

# Some input fields automatically start with capitalized inputs
# Use this for every input
func = lambda s: s[:1].lower() + s[1:] if s else ''

# regular expressions to identify the type of input
if re.match(r"^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$", input_):
    return "email"
elif re.match(r"^(\+\(?\d{1,4}\s?)\)?\-?\.?\s?\(?\d{3}\)?[\s.-]?\d{3}[\s.-]?\d{4}$", input_):
    return "phone"
elif re.match(r"^@[a-zA-Z0-9_]{1,15}$", input_):
    return "twitter"
```

After transforming the inputs,  $$IDrissHash$$ and $$IDrissHash_{verify}$$ are generated using&#x20;

```python
def hashHex(s):
    return hashlib.sha256(s.encode()).hexdigest()
```

In an example, let's consider the IDriss identifier to be "hello@idriss.xyz", the wallet tag hash "ETH\_MM" for MetaMask Eth, and "gm" as the verifier key. No password is chosen. The resulting mapping looks as follows:

$$
4133dbf2e0b2af2b9b006e71dc23fa804df49ce85409b77bebef1395d5953153 \\ \downarrow \\ 3c7b23062dd8a4e09f35da8fe4f1418f614b63942c0aff1d86a3b370807fe29d
$$

Second, the mapping that saves the resolving address to a given IDriss is mapped to from $$IDrissHash_{verify}$$.​ In this example, the IDriss "hello@idriss.xyz" resolves to the address 0x000...0000 with wallet tag "Metamask ETH".

$$
3c7b23062dd8a4e09f35da8fe4f1418f614b63942c0aff1d86a3b370807fe29d \\ \downarrow \\ 0x0000000000000000000000000000000000000000
$$

Lastly, you can find IDriss ownerships in a mapping that stores your  $$IDrissHash$$ together with the address that has paid during sign-up. You are free to change the owner's address at any time. As this is an option, there might be a different means of payment in the future and therefore a different way of determining the original owner address. Head over to your [Management Dashboard](https://www.idriss.xyz/dashboard) for any changes you would like to perform.&#x20;

{% hint style="danger" %}
Beware: only the owner address is verified to change ownership of your IDriss. Make sure you do not lose access to this address. The owner address can also delete an IDriss from the registry.
{% endhint %}

$$
4133dbf2e0b2af2b9b006e71dc23fa804df49ce85409b77bebef1395d5953153\\ \downarrow \\ 0x0000000000000000000000000000000000000000
$$

In this example, the address 0x000..0000 owns the IDriss "hello@idriss.xyz", meaning the owner address is the same as the address saved in the registry.
