# What is CoptLib?

CoptLib (shortened from "Coptic Library") is a .NET Standard library developed in C# designed to help developers handle scenarios specific to the Coptic language and culture.

## Using CoptLib
If your app supports .NET Standard 1.4, then you can [install the package from NuGet](https://www.nuget.org/packages/CoptLib) by pasting the command below into the Package Manager Console.
  PM> Install-Package CoptLib

| .NET Core | .NET Framework | Mono | Xamarin.iOS | Xamarin.Mac | Xamarin.Android | UWP    | Unity  | Windows 8/8.1/Phone |
|-----------|----------------|------|-------------|-------------|-----------------|--------|--------|---------------------|
| 1.0       | 4.6.1          | 4.6  | 10.0        | 3.0         | 7.0             | 10.0.0 | 2018.1 | Not Available       |

# Features
## Coptic Dates

The ```CopticDate``` class is a crude version of .NET's  ```DateTime``` class. The most important features provided by this class are the date calculation functions and the static properties for common Coptic events.

### DateTime to CopticDate
```csharp
DateTime gDate = DateTime.Today; // Any DateTime (using the Gregorian calendar) will work here
CopticDate cDate1 = new CopticDate(gDate);
CopticDate cDate2 = CopticDate.ToCopticDate(gDate);
```

### CopticDate to DateTime
```csharp
CopticDate cDate = CopticDate.Today; // Any CopticDate created from a DateTime object will work here
DateTime gDate = cDate.ToGregorianDate();
```

### More Date-related features
For more features available in the CopticDate class, see [Dates](https://www.github.com/yoshiask/CoptLib/master/Dates).

## Text Conversions (CopticInterpreter)

The ```CopticInterpreter``` is a static class that contains various functions for converting Coptic text to various formats. Along with functions to do the conversions automatically, there are also key mappings available via the "Alphabet" Dictionaries.

```csharp
// Coptic-Phonetic is a custom format written to be safely saved into text files (Including XML and JSON)
// Coptic1 is a common Coptic font. Used by Coptic Chanter.
string Coptic1 = CopticInterpreter.ConvertFromString(CopticPhonetic);
string CopticPhonetic = CopticInterpreter.ConvertToString(Coptic1);

// Tabeha.org is a popular online library containing many Coptic hymns and such. It uses the CS Avva Shenouda font.
string Coptic1 = CopticInterpreter.ConvertFromTasbeha(Tasbeha);

string Coptic1 = CopticInterprester.ConvertFromCopticUnicode(CopticUnicodeText);
```

## More information coming soon!
