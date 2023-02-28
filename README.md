# Python-assesment
The formatINR function is a Python function that takes in a number as an argument and returns a string representing that number in Indian rupees format. The Indian rupee format separates the thousands, lakhs, and crores places by commas.

Here's a step-by-step explanation of what the code does:

s, *d = str(number).partition("."): This line converts the input number into a string, and then partitions it into two parts: the integer part (before the decimal point), and the decimal part (after the decimal point). The s variable will contain the integer part, and the d variable will contain the decimal part (if any).

r = ",".join([s[x-2:x] for x in range(-3, -len(s), -2)][::-1] + [s[-3:]]): This line takes the integer part s and splits it into chunks of two digits each, starting from the end of the string and working towards the beginning. For example, if s is "1234567", the list of chunks will be ['67', '45', '12']. This is accomplished using a list comprehension and the range() function. The [::-1] slice at the end of the list comprehension reverses the order of the chunks.

After the list of chunks is created, the last three digits of the integer part (if any) are added as a single chunk to the end of the list using the s[-3:] slice. In the example above, this would result in the list ['67', '45', '12', '345'].

Finally, the list of chunks is joined together into a single string using commas as the separator. This creates the formatted string in the Indian rupee format. In the example above, the formatted string would be "12,34,567".

return "".join([r] + d): This line concatenates the formatted integer part r with the decimal part d (if any), and returns the resulting string.

Overall, the formatINR function takes in a number, formats the integer part of the number in the Indian rupee format, and returns the formatted string with the decimal part (if any) appended.
