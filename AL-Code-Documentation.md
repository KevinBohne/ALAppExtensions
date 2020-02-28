### Disclaimer: These guidelines are in development and might change over time.

For documentation hints, have a look at [XML Documentation Comments](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments).

---

# Overview

Code documentation in AL is generated according to the XML-based code comments (`///`) preceding an object or a procedure.

### Example
```
/// <summary>
/// My awesome codeunit
/// </summary>
Codeunit 42 "My awesome codeunit"
{
    /// <summary>
    /// Hello AL Documentation!
    /// </summary>
    procedure HelloALDocumentation()
    begin
    ...    
    end;
}
```
----
The AL documentation guidelines are similar to the C# documentation. However, there are some minor differences so keep reading.


# Supported tags

- [\<error>](#error_tag)<sup><span style="color:red">**_only in AL_**</span></sup>
- [\<example>](#example_tag)
- [\<param>](#param_tag)
- [\<paramref>](#paramref_tag)
- [\<raises>](#raises_tag)<sup><span style="color:red">**_only in AL_**</span></sup>
- [\<remarks>](#remarks_tag)
- [\<returns>](#returns_tag)
- [\<see>](#see_tag)
- [\<seealso>](#seealso_tag)
- [\<summary>](#summary_tag)

## <a id="error_tag"></a><error>
#### Syntax
```AL
<error>description</error>
```

#### Parameters
`description` - a summary of the error

#### Remarks
Use this tag to provide a description of the error that a procedure might throw.

#### Example
```AL
/// <summary>
/// My awesome name setter
/// </summary>
/// <param name=NewName>The name to set as my name</param>
/// <error>When the provided name is empty</error>
procedure SetMyName(NewName: Text)
begin
    if NewName = '' then
      Error('Oops! Cannot set an empty name.');
    
    MyName := NewName;
end;
```

---

## <a id="example_tag"></a><example>
See the [\<example>](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/xmldoc/example) documentation.

---

## <a id="param_tag"></a><param>
See the [\<param>](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/xmldoc/param) documentation.

---

## <a id="paramref_tag"></a><paramref>
See the [\<paramref>](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/xmldoc/paramref) documentation.

---

## <a id="raises_tag"></a><raises>

#### Syntax
```AL
<raises>description</raises>
```

#### Parameters
`description` - a summary of the raised event

#### Remarks
Use this tag to provide a description of the event that a procedure might raise.

#### Example
```AL
/// <summary>
/// My awesome name getter
/// </summary
/// <raises>OnAfterGeMyName</raises>
/// <returns>My name</returns>
procedure GetMyName() Name: Text
begin
    Name:= MyName;

    OnAfterGeMytName(Name);
end;

/// <summary>
/// Integration event, raised from <see cref="GetMyName"/>.
/// Subscribe to this event to modify the returned name.
/// </summary>
[IntegrationEvent(false, false)]
local procedure OnAfterGetMyName(var Name: Text)
begin
end;
```

---

## <a id="remarks_tag"></a><remarks>
See the [\<remarks>](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/xmldoc/remarks) documentation.

---

## <a id="returns_tag"></a><returns>
See the [\<returns>](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/xmldoc/returns) documentation.

---

## <a id="see_tag"></a><see>
See the [\<see>](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/xmldoc/see) documentation.

---

## <a id="seealso_tag"></a><seealso>
See the [\<seealso>](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/xmldoc/seealso) documentation.

---

## <a id="summary_tag"></a>\<summary>
See the [\<summary>](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/xmldoc/summary) documentation


