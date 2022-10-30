- ## 📝Definition
  The name is the essence of this topic.
- ## 🎯Intent
  Lexical analyzer divides program text into “words” or “tokens”
- ## 🧠Intuition
  Lexical analysis can be seen as dividing the sentence into correct tokens.
	- For
		- "This is a sentence."
		- ✅ correct analysis
			- `This` `is` `a` `sentence` `.`
		- ❌ wrong analysis
			- `T` `hi` `sis` `ase` `nte` `nce.`
	- For
		- "If x == y then z = 1; else z = 2;"
		- ✅ correct analysis
			- `If` `x == y` `then` `z = 1;` `else z = 2;`