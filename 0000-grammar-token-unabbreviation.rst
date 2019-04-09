- Feature Name: Grammar token unabbreviation
- Start Date: 2019-04-08
- RFC PR: Leave this empty, filled on proposal accept
- Haskell Report Issue: Leave this empty, filled on proposal accept


#######
Summary
#######

Many of the grammar tokens are difficult to recognize, because they use hard-to-understand abbreviations. I propose unabbreviating them. This change only affects documentation.


##########
Motivation
##########

It would make Haskell's structure/syntax/grammar much easier to understand, especially for those unfamiliar with it. Currently, to understand the tokens, one must find their definitions and then attempt to use the definition and the name to figure out what the token means, possibly looking up other tokens in the process, and likely forgetting it again, making it very slow to understand. Making the tokens more readable by unabbreviating them would make Haskell's structure/syntax/grammar much easier to understand.


###############
Detailed design
###############

This would involve renaming abbreviated tokens within sections 2, 3, 4, 5, 8, 10, and 12, between `@@@`s. (I am assuming that none of the libraries have syntax specifications. Please let me know if I somehow missed any sections.) This change only affects documentation. Here are some examples:

| Current   | Preffered                        | Compromise          |
| --------- | -------------------------------- | ------------------- |
| `qvarid`  | `qualified-variable`             | `qualVar`           |
| `qconid`  | `qualified-constructor`          | `qualConstr`        |
| `qtycon`  | `qualified-type-constructor`     | `qualTypeConstrID`  |
| `qtycls`  | `qualified-type-class`           | `qualTypeClass`     |
| `qvarsym` | `qualified-variable-symbol`      | `qualVarSym`        |
| `qconsym` | `qualified-constructor-symbol`   | `qualConstrSym`     |
| `gtycon`  | `generalized-type-constructor`   | `generalTypeConstr` |
| `qconop`  | `qualified-constructor-operator` | `qualConstrOp`      |
| `chname`  | `c-header-filename`              | `cHeadName`         |


#########
Drawbacks
#########

This would make the Report a bit longer, and possibly cause line wrapping or horizontal scrolling if long enough names are used.


############
Alternatives
############

I do not know of any similar, existing proposals. Two things that could be used either in addition to or instead of this, but would harder to implement would be tooltips showing unabbreviated names and links to definitions. (Although there are often multiple places where the same token is (identically) defined.)


####################
Unresolved questions
####################

The main question is what the new tokens should be. The global issues are whether the tokens should be partially abbreviated or not and what casing style to use. I personally prefer either `snake_case` or `kebab-case`, but `camelCase` seems to be the only one used other than `abrvtdlwrcs` (abbreviated lowercase).


################
Additional links
################

I first proposed this on the Haskell-prime mailing list: https://mail.haskell.org/pipermail/haskell-prime/2019-April/004443.html
