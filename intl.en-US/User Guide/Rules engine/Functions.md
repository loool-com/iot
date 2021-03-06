# Functions {#concept_mdn_mss_vdb .concept}

The rules engine provides functions that allow you to handle data when writing a SQL script.

## Call functions {#section_mml_cbt_vdb .section}

In SQL statement, you can use functions to get or handle data.

For example, in the following codes, the functions: deviceName\(\), abs\(number\), and topic\(number\) are used.

```
SELECT case flag when 1 then 'Light On' when 2 then 'Light Off' else '' end flag，deviceName(),abs(temperature) tmr FROM "/topic/#" WHERE temperature>10 and topic(2)='123'
```

**Note:** Exercise caution when you use functions. Constants are enclosed with apostrophes \('\). Variables are not enclosed or are enclosed with quotation marks \("\). For example, in `select “a” a1, ‘a’ a2, a a3`, `a1` is equivalent to `a3`, and `a2`represents a constant `a`.

|**Function**|**Description**|
|abs\(number\)|Returns the absolute value of a number.|
|asin\(number\)|Returns the asin of the value of number.|
|attribute\(key\)|Returns the device tag that corresponds with the key. If a tag with the specified key is not found, the returned value is null. When you debug your SQL statements, because there is no real device or tag, the returned value is null.|
|concat\(string1, string2\)| Concatenates two strings.

 Example: concat\(field,’a’\).

 |
|cos\(number\)|Returns the cosine of the value of number.|
|cosh\(number\)|Returns the hyperbolic cosine of a number.|
|crypto\(field,String\)| Encrypts the value of a field.

 The String parameter represents an algorithm. Available algorithms include MD2, MD5, SHA1, SHA-256, SHA-384, and SHA-512.

 |
|deviceName\(\)|Returns the name of the current device. When you debug your SQL statements, because there is no real device, the returned value is null.|
|endswith\(input, suffix\)|Validates whether the input value string ends with the suffix string.|
|exp\(number\)|Returns a specific value raised to the power of a number.|
|floor\(number\)|Rounds a number down, toward zero, to the nearest multiple of significance. Returns an integer that is equal|
|log\(n, m\)| Returns the logarithm of a number to the base that you have specified.

 If you do not specify m, log\(n\) is returned.

 |
|lower\(string\)|Returns a lower-case string.|
|mod\(n, m\)|Returns the remainder after a number has been divided by a divisor.|
|nanvl\(value, default\)| Returns the value of a property.

 If the value of the property is null, the function returns default.

 |
|newuuid\(\)|Returns a random UUID.|
|payload\(textEncoding\)| Returns the payload of encoding the text in the message sent by a device.

 The default encoding is UTF-8, which means that payload\(\) and payload\(‘utf-8’\) will return the same result.

 |
|power\(n,m\)|Raises number n to power m.|
|rand\(\)|Returns a random number greater than or equal to 0 and less than 1.|
|replace\(source, substring, replacement\)| Replaces a specific column.

 Example: replace\(field,’a’,’1’\).

 |
|sin\(n\)|Returns the sine of n.|
|sinh\(n\)|Returns the hyperbolic sine of n.|
|tan\(n\)|Returns the tangent of n.|
|tanh\(n\)|Returns the hyperbolic tangent of n.|
|timestamp\(format\)| Returns the current system time.

 The format parameter is optional. If you do not specify the timestamp format, the real-time timestamp in milliseconds will be returned. For example, timestamp\(\) = 1540483200000，timestamp\('yyyy-MM-dd HH:mm:ss.SSS'\)=2018-10-26 00:00:00.000.

 |
|topic\(number\)| Returns a segment of a topic.

 For example, for topic /abcdef/ghi, if you use the function topic\(\), “ /abcdef/ghi” will be returned; If you use the function topic\(1\), “ abcdef” will be returned; If you use the function topic\(2\), “ghi” will be returned.

 |
|upper\(string\)|Returns an upper-case string.|
|to\_base64\(\*\)|If the original payload data is binary data, you can call this function to convert the binary data to a base64 string.|

