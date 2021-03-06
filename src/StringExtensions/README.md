<h2>ToNullableStringExtension</h2>
More convenient than using T.TryParse(string, out T).
Works with primitive types, structs, and enums.
Tries to parse the string to an instance of the type specified.
If the input cannot be parsed, null will be returned.
If the value of the caller is null, null will be returned.
So if you have "string s = null;" and then you try "s.ToNullable...",
null will be returned. No null exception will be thrown. 



<h3>Examples</h3>
int? numVotes = "123".ToNullable&lt;int&gt;();<br>
decimal price = tbxPrice.Text.ToNullable&lt;decimal&gt;() ?? 0.0M;<br>
PetTypeEnum petType = "Cat".ToNullable&lt;PetTypeEnum&gt;() ?? PetTypeEnum.DefaultPetType;<br>
PetTypeEnum petTypeByIntValue = "2".ToNullable&lt;PetTypeEnum>() ?? PetTypeEnum.DefaultPetType;<br>
string thisWillNotThrowException = null;<br>
int? nullsAreSafe = thisWillNotThrowException.ToNullable&lt;int&gt;();<br>
