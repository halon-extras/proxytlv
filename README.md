# PROXY Protocol v2 TLV Parser

This plugin parses a PROXY protoocol v2 TLV (type-length-value) list into a readable representation. This class is intended to be used to parse the connect hooks ``$arguments["proxytlv"]`` property.

## Installation

Follow the [instructions](https://docs.halon.io/manual/comp_install.html#installation) in our manual to add our package repository and then run the below command.

### Ubuntu

```
apt-get install halon-extras-proxytlv
```

### RHEL

```
yum install halon-extras-proxytlv
```

## Exported classes

These classes needs to be [imported](https://docs.halon.io/hsl/structures.html#import) from the `extras://proxytlv` module path.

### ProxyTLS(proxytlv)

Parse the proxytlv string.

**Params**

- proxytlv `string` - The TLV string

**Returns**: class object.

**On Error**

An Exception is thrown

#### value(type)

Return the value of a type. For known type, the ``type`` argument should on in the list.

| Type      | Return            |                                       |
|-----------|-------------------|---------------------------------------|
| ALPN      | `string`          |                                       |
| AUTHORITY | `string`          |                                       |
| CRC32C    | `number`          |                                       |
| UNIQUE_ID | `string`          |                                       |
| SSL       | `array of string` | VERSION, CN, CIPHER, SIG_ALG, KEY_ALG |
| NETNS     | `string`          |                                       |
| `number`  | `string`          |                                       |

**Returns**: the requested type if available

**Return type**: `any`, `none` on error

#### types()

Return all available types.

**Returns**: list of types

**Return type**: `array`