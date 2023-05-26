
# Pridevel's Smart Contracts Auditing Checklist

### **Description** :  This is  quick set of condensed checkpoints for your reference to perform security audit and gas optimized version of any smart contract

Initial Tips before you start following this checklist :

* Though you can follow any order ,and their is no strict rule as such .but we recommend you to check for **GAS OPTIMIZATION**
 ,then **LOW RISK/QA** ,and at the end look for **MEDIUM/HIGH** risk issues






### Severity Categorization
---

#### Estimating Risk

Where assets refer to funds, NFTs, data, authorization, and any information intended to be private or confidential:


**QA (Quality Assurance)**  Includes both Non-critical (code style, clarity, syntax, versioning, off-chain monitoring (events, etc) and Low risk (e.g. assets are not at risk: state handling, function incorrect as to spec, issues with comments). Excludes Gas optimizations

**2 — Med**: Assets not at direct risk, but the function of the protocol or its availability could be impacted, or leak value with a hypothetical attack path with stated assumptions, but external requirements.

**3 — High**: Assets can be stolen/lost/compromised directly (or indirectly if there is a valid attack path that does not have hand-wavy hypotheticals).




> NOTE:  For both medium and high risk issues , there are 10 common types of attacks vectors we have to look for. If we find via certain behavior ,or attack vector that it is impacting specific user  at extreme hypothetical random condition,we will keep that in “Medium” Category.
If it affects the main vault,or will impact all the users ,or its access mechanism ,we should put it as high.
So, in PVL category checklist,we would be keeping all  those common attack vectors in category “Med/HIGH”


---

Looking for getting your smart contract audited?Or if you are looking for more information , request you to DM us at :

* [Twitter](https://twitter.com/Web3tech_)
* [Discord](https://discord.gg/3MRWE5BgQN)
* [Telegram](https://t.me/blockchainweb3tech)
* [LinkedIn](https://www.linkedin.com/company/web3tech-blockchain-solutions/)


---

| S.No |            Test Cases                                                                                                    | Category | Compiler Version | CONTRACT CATEGORY TYPE |   |
|------|--------------------------------------------------------------------------------------------------------------------------|----------|------------------|------------------------|---|
| 1    | [array[index] += amount is cheaper than array[index] = array[index] + amount]()                                          | GAS      | ALL              | GENERIC                |   |
| 2    | [Cache array length outside of loop]()                                                                                   | GAS      | ALL              | GENERIC                |   |
| 3    | [Use calldata instead of memory for function arguments that do not get mutated]()                                        | GAS      | ALL              | GENERIC                |   |
| 4    | [Don't initialize variables with default value]()                                                                        | GAS      | ALL              | GENERIC                |   |
| 5    | [plus plus i costs less gas than i plus plus, especially when its used in for-loops (same for decrement operator too)]() | GAS      | ALL              | GENERIC                |   |
| 6    | [Using private rather than public for constants, saves gas]()                                                            | GAS      | ALL              | GENERIC                |   |
| 7    | [Use != 0 instead of > 0 for unsigned integer comparison]()                                                              | GAS      | ALL              | GENERIC                |   |
| 8    | [Use Custom Errors]()                                                                                                    | GAS      | 0.8.0 and above  | GENERIC                |   |
| 9    | [Use Mappings instead of Arrays]()                                                                                       | GAS      | ALL              | GENERIC                |   |
| 10   | [Use Short-Circuiting rules to your advantage]()                                                                         | GAS      | ALL              | GENERIC                |   |
| 11   | [If use case allows , use  “External” modifier instead of “Public” ]()                                                   | GAS      | ALL              | GENERIC                |   |
| 12   | [Limit the string length in the Require/Revert Statements]()                                                             | GAS      | ALL              | GENERIC                |   |
| 13   |  [Make use of single line swaps to optimize gas]()                                                                       | GAS      | ALL              | GENERIC                |   |
| 14   | "[Optimize gas by carefully choosing ""function name""]()"                                                               | GAS      | ALL              | GENERIC                |   |
| 15   | [Optimized packing of storage variables]()                                                                               | GAS      | ALL              | GENERIC                |   |
| 16   | [Catch frequently used storage variables in memory/stack]()                                                              | GAS      | ALL              | GENERIC                |   |
| 17   | [Use fixed size bytes array rather than string or bytes[]]()                                                             | GAS      | ALL              | GENERIC                |   |
| 18   | [Use unchecked for arithmetic where you are sure it won't over or underflow]()                                           | GAS      | ALL              | GENERIC                |   |
| 19   | [Use indexed events as they are less costly compared to non-indexed ones]()                                              | GAS      | ALL              | GENERIC                |   |
| 20   | [Less than or equal to” (<=) is more expensive than just “less than” (<)]()                                              | GAS      | ALL              | GENERIC                |   |
| 21   | [Don’t compare to boolean literals (true/false)]()                                                                       | GAS      | ALL              | GENERIC                |   |
| 22   | [use the Solidity Optimizer]()                                                                                           | GAS      | ALL              | GENERIC                |   |
| 23   | [If possible use fixed size array than dynamic size array to save gas]()                                                 | GAS      | ALL              | GENERIC                |   |
| 24   | [Write to storage last]()                                                                                                | GAS      | ALL              | GENERIC                |   |
| 25   | [Non-strict inequalities are cheaper than strict ones]()                                                                 | GAS      | ALL              | GENERIC                |   |
| 26   | [internal functions are cheaper than public]()                                                                           | GAS      | ALL              | GENERIC                |   |
| 27   | [Avoid Use of floating Pragma]()                                                                                         | QA/NC    | ALL              | GENERIC                |   |
| 28   | [Avoid use of older compiler version]()                                                                                  | QA/NC    | ALL              | GENERIC                |   |
| 29   | [Avoid use of very recent compiler version]()                                                                            | QA/NC    | ALL              | GENERIC                |   |
| 30   |  [Avoid use of multiple solidity pragma across different files]()                                                        | QA/NC    | ALL              | GENERIC                |   |
| 31   | [Import statements should always be placed at the top of the file]()                                                     | QA/NC    | ALL              | GENERIC                |   |
| 32   | [Order of Functions]()                                                                                                   | QA/NC    | ALL              | GENERIC                |   |
| 33   | [Whitespace in Expressions]()                                                                                            | QA/NC    | ALL              | GENERIC                |   |
| 34   |  [Function Declaration]()                                                                                                | QA/NC    | ALL              | GENERIC                |   |
| 35   | [Modifier order for a function]()                                                                                        | QA/NC    | ALL              | GENERIC                |   |
| 36   | [Declarations of array variables should not have a space between the type and the brackets]()                            | QA/NC    | ALL              | GENERIC                |   |
| 37   | [Strings should be quoted with double-quotes instead of single-quotes]()                                                 | QA/NC    | ALL              | GENERIC                |   |
| 38   | [Surround operators with a single space on either side]()                                                                | QA/NC    | ALL              | GENERIC                |   |
| 39   | [Check layout contract elements order]()                                                                                 | QA/NC    | ALL              | GENERIC                |   |
| 40   | [ Inside each contract, library or interface, use the proper order]()                                                    | QA/NC    | ALL              | GENERIC                |   |
| 41   | [Contract and Library Naming Convention]()                                                                               | QA/NC    | ALL              | GENERIC                |   |
| 42   | [Struct,Event ,Functions & Functions Argument Naming Convention]()                                                       | QA/NC    | ALL              | GENERIC                |   |
| 43   | [Local and State Variable Names]()                                                                                       | QA/NC    | ALL              | GENERIC                |   |
| 44   |  [Constants , Modifiers & Enums Naming Conventions]()                                                                    | QA/NC    | ALL              | GENERIC                |   |
| 45   |  [Use latest version of OpenZeppelin from dependencies]()                                                                | QA/NC    | ALL              | GENERIC                |   |
| 46   | [storing floating point  number / Arithmetic Precision]()                                                                | QA/NC    | ALL              | GENERIC                |   |
| 47   |  [Returns bool after transfer()]()                                                                                       | QA/NC    | ALL              | GENERIC                |   |
| 48   | [Be extra careful transferring tokens to the 0x0 address]()                                                              | QA/NC    | ALL              | GENERIC                |   |
| 49   |  [Low decimals]()                                                                                                        | QA/NC    | ALL              | GENERIC                |   |
| 50   | [High decimals]()                                                                                                        | QA/NC    | ALL              | GENERIC                |   |
| 51   |  [Revert on Large Approvals & Transfers]()                                                                               | QA/NC    | ALL              | GENERIC                |   |
| 52   | [Avoid creating tokens with multiple addresses]()                                                                        | QA/NC    | ALL              | GENERIC                |   |
| 53   | [No user  should own most of the supply]()                                                                               | QA/NC    | ALL              | GENERIC                |   |
| 54   | [Take Compiler Warnings Seriously]()                                                                                     | QA/NC    | ALL              | GENERIC                |   |
| 55   | [ DoS with block gas limit]()                                                                                            | MED/HIGH | ALL              | GENERIC                |   |
| 56   | [ Reentrancy Attack]()                                                                                                   | MED/HIGH | ALL              | GENERIC                |   |
| 57   | [Arithmetic Underflow/Overflow]()                                                                                        | MED/HIGH | ALL              | GENERIC                |   |
| 58   |  [Phishing Attacks (via tx origin) ]()                                                                                   | MED/HIGH | ALL              | GENERIC                |   |
| 59   | [Randomness Vulnerabilities]()                                                                                           | MED/HIGH | ALL              | GENERIC                |   |
| 60   |  [Replay Attacks]()                                                                                                      | MED/HIGH | ALL              | GENERIC                |   |
|      |                                                                                                                          |          |                  |                        |   |
|      |                                                                                                                          
