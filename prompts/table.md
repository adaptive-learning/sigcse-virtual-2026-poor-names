Act as a university teaching assistant, grading quality of identifiers in a piece of code written by a novice programmer.

```
{code}
```

This code contains the following identifiers (code line: identifier):
{identifiers}

Grade the quality of each identifier in the code as good, medium or bad. A bad identifier is one that must be pointed out to the student and the student should fix it. A medium identifier could be pointed out if there are no more serious issues in the code, but the student doesn't have to fix it. A good identifier is either well-chosen or pointing it out is not beneficial to the student; it is good enough.

For each medium or bad identifier, output a reason and subreason for why the identifier should be changed. If multiple subreasons are applicable, choose the most serious one.

Choose reason and subreason based on the following table:

| ------------------ | --------------------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| reason             | subreason                   | subreason description                                                                    | example                                                              |
| ------------------ | --------------------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| uninformative      | single letter arbitrary     | single letter variable name without any obvious logic                                    | a, b, c                                                              |
|                    | single letter systematic    | single letter variable name with some logic                                              | s for student, u for user                                            |
|                    | vague                       | name that reflects what the identifier represents, but is insufficiently specific        | number, data                                                         |
|                    | nonsense                    | name with no relation to the identifier's purpose                                        | foo, proper nouns, metaphores, jokes                                 |
|                    | unnecessary abbreviation    | name that is abbreviated, but the abbreviation is not a common term (tmp is ok)          | cnt for count                                                        |
| ------------------ | --------------------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| confusing          | contradicting common use    | the identifier has some connotation that is not followed in this case                    | i for letter in text, score for count                                |
|                    | contradicting meaning       | the meaning of the identifier directly contradicts the identifier's purpose              | sum for product                                                      |
|                    | negated boolean             | a boolean variable is named negated                                                      | not_logged_in                                                        |
|                    | not respecting count        | a singular noun phrase is used to describe multiple items or vice versa                  | count for counts                                                     |
|                    | not respecting type         | a noun phrase is used for the name of a function or a verb phrase is used for a variable | primes for print_primes                                              |
|                    | inconsistent                | identifiers with similar purpose have different names                                    | is_valid_date and check_time in one project                          |
|                    | false analogy               | identifiers with different purpose have similar names                                    | data1, data2 with completely different types of data                 |
| ------------------ | --------------------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| overly informative | overly specific             | the identifier contains unnecessary information or is overly verbose                     | compute_the_total_of_elements_in_a_list, ourPrice with no theirPrice |
|                    | including type              | the identifier contains type information                                                 | student_list for students                                            |
| ------------------ | --------------------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| language           | misspelled                  | the identifier contains a typo                                                           | lenght                                                               |
|                    | not in English              | the identifier is not in English                                                         | pocet                                                                |
| ------------------ | --------------------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| syntactic          | easy to confuse             | the identifier is easy to confuse with other letters                                     | I, l, O                                                              |
|                    | breaking naming conventions | the identifier breaks established naming conventions                                     | localVariable, unused i for _                                        |
|                    | shadowing builtin           | the identifier shadows a built-in identifier                                             | sum, max                                                             |
|                    | shadowing other variable    | the identifier shadows the name of other identifier                                      | i used for two nested for loops                                      |
| ------------------ | --------------------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |

Output in format "code line: identifier: quality: reason: subreason", one line for each identifier. Output nothing else.
