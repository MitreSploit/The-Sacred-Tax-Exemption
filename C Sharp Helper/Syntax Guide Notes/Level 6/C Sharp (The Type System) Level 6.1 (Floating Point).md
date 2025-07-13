### Char
Single characters can be saved as a variable using `char`. 
`char` is very closely related to integer types and is even lumped into the integer banner. 
Char uses over 65 thousand distinct characters and follows a widely used standard called Unicode. Even an emoji could be used here. 
A Char literal is made by placing the character in single quotes like this:
```C#
// As cool as this is, a console window often won't know how to display an emoji. 
// You can also use the hexadecimal unicode number for a symbol.
char icon = '😁';
```

### String Literals
A String Literal is created by placing the desired text inside of `" "` brackets and using the `string` datatype. 
```C#
string name = "Matthew";
```

# Floating-Point Types
C# has three types of floating-point data types. These are numbers that contain a decimal.
We call them floating-point because the decimal can float between any number, unlike fixes-point types. 
The three flavours of Floating-Point are `float`, `double` and `decimal`.

1. **`float`** - Float uses 4 bytes.
2. **`double`** - double uses 8 bytes (hence the name double).
3. **`decimal`** - decimal uses 16 bytes.  

Decimal is the most precise of the three, but it is also the slowest. Float and Double use conventions across all of the computing world including in circuitry boards. If you are doing something that requires extreme precision, then it would be best to choose `decimal`.
Floating-Point types can store numbers that are insanely big and insanely small. 

- A **`float`** has 6 to 7 digits of precision, depending on the number. It can represent the number `10000` and the number `0.0001`, but it cannot quite differentiate between `10000` and `10000.0001`
- A **`double`** has up to 15 to 16 digits of precision. 
- A **`decimal`** has up to 28 to 29 digits of precision. The decimal ranges is the smallest of the three though. 

Generally speaking, a `float` will be good for the vast majority of occasions and it uses the fewest bytes. 
Making variables with these data types is the same as any other:
```C#
double myDouble = 2.14159221;

// When a number liteal contains a decimal it becomes a double literal (instead of an integer litera), so you should append it with an 'f' to make it a float. 
float newFloat = 3.14159f;

// 'm' is for monetary or money (financial). Financial calculations often need incredible precision. This makes a decimal. 
decimal myDecimal = 3.1415922093m;
```

If you use an integer literal, the compiler will convert it. 