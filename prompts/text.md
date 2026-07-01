Act as a university teaching assistant, grading quality of identifiers in a piece of code written by a novice programmer.

```
{code}
```

This code contains the following identifiers (code line: identifier):
{identifiers}

Grade the quality of each identifier in the code as good, medium or bad. A bad identifier is one that must be pointed out to the student and the student should fix it. A medium identifier could be pointed out if there are no more serious issues in the code, but the student doesn't have to fix it. A good identifier is either well-chosen or pointing it out is not beneficial to the student; it is good enough.

For each medium or bad identifier, output a reason and subreason for why the identifier should be changed. If multiple subreasons are applicable, choose the most serious one. Possible reasons are: uninformative, confusing, overly informative, language and syntactic. Each reason has several subreasons.

Uninformative identifier can be: single letter arbitrary (single letter variable name without any obvious logic, like a, b, c), single letter systematic (single letter variable with some logic, like s for student or u for user), vague (name that reflect what the identifier represents, but is insufficiently specific, like number for a divisor, or data), nonsense (name with no relation to the identifier’s purpose, like foo, proper nouns, metaphores or jokes), or unnecessary abbreviation (name that is abbreviated, but the abbreviation is not a common term, like cnt for count; there are common, acceptable abbreviations, like tmp for a temporary variable).

Confusing identifiers can be: contradicting common use (the identifier has some connotation that is not followed in the specific case, like using i for a letter in a text, or score for count), contradicting meaning (the meaning of the identifier directly contradicts the identifier’s purpose, like using sum for product), negated boolean (a boolean identifier which is negated, like not_logged_in), not respecting count (a singular noun phrase used to describe multiple items or vice versa, like count for a list of counts), not respecting type (a noun phrase used for a function or a verb phrase used for a variable, like primes for print_primes), inconsistent (identifiers with a similar purpose having different names, like is_valid_date and check_time in one file), false analogy (identifiers with different purpose having similar names, like data1 and data2 with completely different types of data).

Overly informative identifiers can be: overly specific (when the identifier contains unnecessary information or is overly verbose, like compute_the_total_of_elements_in_a_list, ourPrice with no theirPrice), or including type (when the identifier also contains type information, like student_list).

Language identifiers can be: misspelled (if the identifier contains a typo, like lenght) or not in English.

Syntactic identifiers can be: easy to confuse (if the identifier is a single letter that is easy to confuse with another symbol, like l, I and O), breaking naming conventions (localVariable in Python, unused i instead of _), shadowing builtin (if the identifier shadows a built-in functions, like sum or max), or shadowing other identifier (like using i in two nested for loops).

