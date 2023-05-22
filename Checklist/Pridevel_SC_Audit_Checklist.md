
# Pridevel's Smart Contracts Auditing Checklist

### **Description** :  This is  quick set of condensed checkpoints for your reference to perform security audit and gas optimized version of any smart contract

Initial Tips before you start following this checklist :

* Though you can follow any order ,and their is no strict rule as such .but we recommend you to check for **GAS OPTIMIZATION**
 ,then **LOW RISK/QA** ,and at the end look for **MEDIUM/HIGH** risk issues






### Severity Categorization
---

#### Estimating Risk

Where assets refer to funds, NFTs, data, authorization, and any information intended to be private or confidential:


**QA (Quality Assurance)**  Includes both Non-critical (code style, clarity, syntax, versioning, off-chain monitoring (events, etc) and Low risk (e.g. assets are not at risk: state handling, function incorrect as to spec, issues with comments). Excludes Gas optimizations, which are submitted and judged separately.

**2 — Med**: Assets not at direct risk, but the function of the protocol or its availability could be impacted, or leak value with a hypothetical attack path with stated assumptions, but external requirements.

**3 — High**: Assets can be stolen/lost/compromised directly (or indirectly if there is a valid attack path that does not have hand-wavy hypotheticals).




> NOTE:  For both medium and high risk issues , there are 15-20 common types of attacks vectors we have to look for. If we find via certain behavior ,or attack vector that it is impacting specific user  at extreme hypothetical random condition,we will keep that in “Medium” Category.
If it affects the main vault,or will impact all the users ,or its access mechanism ,we should put it as high.
So, in PVL category checklist,we would be keeping all  those common attack vectors in category “Med/HIGH”


---


| S.No |            Test Cases                                                                                                                                  | Category | Compiler Version | CONTRACT CATEGORY TYPE |   |
|------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------|------------------|------------------------|---|
| 1    | [Use assembly to check for address(0)]()                                                                                                               | GAS      | ALL              | GENERIC                |   |
| 2    | [array[index] += amount is cheaper than array[index] = array[index] + amount]()                                                                        | GAS      | ALL              | GENERIC                |   |
| 3    | [ Using bools for storage incurs overhead ]()                                                                                                          | GAS      | ALL              | GENERIC                |   |
| 4    |  [Cache array length outside of loop]()                                                                                                                | GAS      | ALL              | GENERIC                |   |
| 5    |               [Use calldata instead of memory for function arguments that do not get mutated]()                                                        | GAS      | ALL              | GENERIC                |   |
| 6    | [Don't initialize variables with default value]()                                                                                                      | GAS      | ALL              | GENERIC                |   |
| 7    | [plus plus i costs less gas than i++, especially when it's used in for-loops]()                                                                        | GAS      | ALL              | GENERIC                |   |
| 8    | [Using private rather than public for constants, saves gas]()                                                                                          | GAS      | ALL              | GENERIC                |   |
| 9    | [Use != 0 instead of > 0 for unsigned integer comparison]()                                                                                            | GAS      | ALL              | GENERIC                |   |
| 10   | [Use Custom Errors]()                                                                                                                                  | GAS      | 0.8.0 and above  | GENERIC                |   |
| 11   | [Use Mappings instead of Arrays]()                                                                                                                     | GAS      | ALL              | GENERIC                |   |
| 12   | [Use Short-Circuiting rules to your advantage]()                                                                                                       | GAS      | ALL              | GENERIC                |   |
| 13   | [Use Events : Data that does not need to be accessed on-chain can be stored in events to save gas]()                                                   | GAS      | ALL              | GENERIC                |   |
| 14   | [If use case allows , use  “External” modifier instead of “Public” ]()                                                                                 | GAS      | ALL              | GENERIC                |   |
| 15   | [Use 'bytes' instead of 'strings' to save gas ]()                                                                                                      | GAS      | ALL              | GENERIC                |   |
| 16   | [Limit the string length in the Require/Revert Statements]()                                                                                           | GAS      | ALL              | GENERIC                |   |
| 17   | [Use libraries to save some bytecodes]()                                                                                                               | GAS      | ALL              | GENERIC                |   |
| 18   | [Use of Multiple require(s)]()                                                                                                                         | GAS      | ALL              | GENERIC                |   |
| 19   | [Make use of single line swaps to optimize gas]()                                                                                                      | GAS      | ALL              | GENERIC                |   |
| 20   | [Delete the variables you do not need]()                                                                                                               | GAS      | ALL              | GENERIC                |   |
| 21   | [If you are defining/using public state variable make it 'constant' or immutable to save gas ,if its value is not going to change]()                   | GAS      | ALL              | GENERIC                |   |
| 22   | "[Optimize gas by carefully choosing ""function name""]()"                                                                                             | GAS      | ALL              | GENERIC                |   |
| 23   | [Optimized packing of storage variables]()                                                                                                             | GAS      | ALL              | GENERIC                |   |
| 24   | [Catch frequently used storage variables in memory/stack]()                                                                                            | GAS      | ALL              | GENERIC                |   |
| 25   | [Use fixed size bytes array rather than string or bytes[]]()                                                                                           | GAS      | ALL              | GENERIC                |   |
| 26   | [ Use unchecked for arithmetic where you are sure it won't over or underflow]()                                                                        | GAS      | ALL              | GENERIC                |   |
| 27   | [Refactor a modifier to call a local function instead of directly having the code in the modifier, saving bytecode size and thereby deployment cost]() | GAS      | ALL              | GENERIC                |   |
| 28   | [Use indexed events as they are less costly compared to non-indexed ones]()                                                                            | GAS      | ALL              | GENERIC                |   |
| 29   | [ Common cases >> Rare cases]()                                                                                                                        | GAS      | ALL              | GENERIC                |   |
| 30   | [Runtime cost >> Deployment cost]()                                                                                                                    | GAS      | ALL              | GENERIC                |   |
| 31   | [Payable functions are cheaper]()                                                                                                                      | GAS      | ALL              | GENERIC                |   |
| 32   | [ Less than or equal to” (<=) is more expensive than just “less than” (<)]()                                                                           | GAS      | ALL              | GENERIC                |   |
| 33   | [Don’t make multiple updates to storage variables if possible]()                                                                                       | GAS      | ALL              | GENERIC                |   |
| 34   | [Use ‘send’ instead of ‘transfer’]()                                                                                                                   | GAS      | ALL              | GENERIC                |   |
| 35   | [Use selfdestruct to send eth]()                                                                                                                       | GAS      | ALL              | GENERIC                |   |
| 36   | [Use chained conditionals in the order of cheapest gas]()                                                                                              | GAS      | ALL              | GENERIC                |   |
| 37   | [Don’t compare to boolean literals (true/false)]()                                                                                                     | GAS      | ALL              | GENERIC                |   |
| 38   | [use the Solidity Optimizer]()                                                                                                                         | GAS      | ALL              | GENERIC                |   |
| 39   | [Use eth-gas-reporter]()                                                                                                                               | GAS      | ALL              | GENERIC                |   |
| 40   | [ If possible use fixed size array than dynamic size array to save gas]()                                                                              | GAS      | ALL              | GENERIC                |   |
| 41   | [uint256 can be cheaper than uint8]()                                                                                                                  | GAS      | ALL              | GENERIC                |   |
| 42   | [Write to storage last]()                                                                                                                              | GAS      | ALL              | GENERIC                |   |
| 43   | [ Non-strict inequalities are cheaper than strict ones]()                                                                                              | GAS      | ALL              | GENERIC                |   |
| 44   | [internal functions are cheaper than public]()                                                                                                         | GAS      | ALL              | GENERIC                |   |
| 45   | [Booleans use 8 bits while you only need 1 bit]()                                                                                                      | GAS      | ALL              | GENERIC                |   |
| 46   | [Byte constants are more efficient than string constants]()                                                                                            | GAS      | ALL              | GENERIC                |   |
| 47   | [ Structs can be packed into fewer storage slots ]()                                                                                                   | GAS      | ALL              | GENERIC                |   |
| 48   | [ Using storage instead of memory for structs/arrays saves gas]()                                                                                      | GAS      | ALL              | GENERIC                |   |
| 49   | [ Avoid contract existence checks by using low level calls]()                                                                                          | GAS      | ALL              | GENERIC                |   |
| 50   | [<x> += <y> costs more gas than <x> = <x> + <y> for state variables]()                                                                                 | GAS      | ALL              | GENERIC                |   |
| 51   | [Usage of uints/ints smaller than 32 bytes (256 bits) incurs overhead ]()                                                                              | GAS      | ALL              | GENERIC                |   |
| 52   | [Avoid Use of floating Pragma]()                                                                                                                       | QA/NC    | ALL              | GENERIC                |   |
| 53   | [Avoid use of older compiler version]()                                                                                                                | QA/NC    | ALL              | GENERIC                |   |
| 54   | [Avoid use of very recent compiler version]()                                                                                                          | QA/NC    | ALL              | GENERIC                |   |
| 55   | [Avoid use of multiple solidity pragma across different files]()                                                                                       | QA/NC    | ALL              | GENERIC                |   |
| 56   | [Import statements should always be placed at the top of the file]()                                                                                   | QA/NC    | ALL              | GENERIC                |   |
| 57   | [Order of Functions]()                                                                                                                                 | QA/NC    | ALL              | GENERIC                |   |
| 58   | [Whitespace in Expressions]()                                                                                                                          | QA/NC    | ALL              | GENERIC                |   |
| 59   | [Control Structures]()                                                                                                                                 | QA/NC    | ALL              | GENERIC                |   |
| 60   | [Function Declaration]()                                                                                                                               | QA/NC    | ALL              | GENERIC                |   |
| 61   | [Modifier order for a function ]()                                                                                                                     | QA/NC    | ALL              | GENERIC                |   |
| 62   | [ Declarations of array variables should not have a space between the type and the brackets]()                                                         | QA/NC    | ALL              | GENERIC                |   |
| 63   | [Strings should be quoted with double-quotes instead of single-quotes]()                                                                               | QA/NC    | ALL              | GENERIC                |   |
| 64   | [Surround operators with a single space on either side]()                                                                                              | QA/NC    | ALL              | GENERIC                |   |
| 65   | "[Operators with a higher priority than others can exclude surrounding whitespace in order to denote precedence]()                                     |
| "    | QA/NC                                                                                                                                                  | ALL      | GENERIC          |                        |
| 66   | [Check layout contract elements order]()                                                                                                               | QA/NC    | ALL              | GENERIC                |   |
| 67   | [Inside each contract, library or interface, use the proper order]()                                                                                   | QA/NC    | ALL              | GENERIC                |   |
| 68   | [Contract and Library Naming Convention]()                                                                                                             | QA/NC    | ALL              | GENERIC                |   |
| 69   | [Struct,Event ,Functions & Functions Argument Naming Convention]()                                                                                     | QA/NC    | ALL              | GENERIC                |   |
| 70   | [Local and State Variable Names]()                                                                                                                     | QA/NC    | ALL              | GENERIC                |   |
| 71   | [Constants , Modifiers & Enums Naming Conventions]()                                                                                                   | QA/NC    | ALL              | GENERIC                |   |
| 72   | [Use latest version of OpenZeppelin from dependencies]()                                                                                               | QA/NC    | ALL              | GENERIC                |   |
| 73   | [storing floating point  number / Arithmetic Precision]()                                                                                              | QA/NC    | ALL              | GENERIC                |   |
| 74   | [ Keep fallback functions simple]()                                                                                                                    | QA/NC    | ALL              | GENERIC                |   |
| 75   | [Unchecked External Call]()                                                                                                                            | QA/NC    | ALL              | GENERIC                |   |
| 76   | [Returns bool after transfer()]()                                                                                                                      | QA/NC    | ALL              | GENERIC                |   |
| 77   | [ Be extra careful transferring tokens to the 0x0 address]()                                                                                           | QA/NC    | ALL              | GENERIC                |   |
| 78   | [Be careful transferring tokens to the contract address]()                                                                                             | QA/NC    | ALL              | GENERIC                |   |
| 79   | [ Override _beforeTokenTransfer hook]()                                                                                                                | QA/NC    | ALL              | GENERIC                |   |
| 80   | [ Pausable tokens.An admin controlled pause feature opens users of the token to risk from a malicious or compromised token owner. ]()                  | QA/NC    | ALL              | GENERIC                |   |
| 81   | [Reentrant Calls (ERC777). The token is not an ERC777 token and has no external function call in transfer and transferFrom.]()                         | QA/NC    | ALL              | GENERIC                |   |
| 82   | [ Fee on transfer. Transfer and transferFrom should not take a fee. ]()                                                                                | QA/NC    | ALL              | GENERIC                |   |
| 83   | [Upgradable tokens.]()                                                                                                                                 | QA/NC    | ALL              | GENERIC                |   |
| 84   | [ A change to the token semantics can break any smart contract that depends on the past behavior.]()                                                   | QA/NC    | ALL              | GENERIC                |   |
| 85   | [  Tokens that block address]()                                                                                                                        | QA/NC    | ALL              | GENERIC                |   |
| 86   | [ Approval Race Protections.]()                                                                                                                        | QA/NC    | ALL              | GENERIC                |   |
| 87   | [ Revert on Zero Value Transfers.]()                                                                                                                   | QA/NC    | ALL              | GENERIC                |   |
| 88   | [ Low decimals]()                                                                                                                                      | QA/NC    | ALL              | GENERIC                |   |
| 89   | [High decimals.]()                                                                                                                                     | QA/NC    | ALL              | GENERIC                |   |
| 90   | [Revert on Transfer to the Zero Address.]()                                                                                                            | QA/NC    | ALL              | GENERIC                |   |
| 91   | [ Revert on Large Approvals & Transfers]()                                                                                                             | QA/NC    | ALL              | GENERIC                |   |
| 92   | [The token should be a simple contract ]()                                                                                                             | QA/NC    | ALL              | GENERIC                |   |
| 93   | [ Avoid creating tokens with multiple addresses.]()                                                                                                    | QA/NC    | ALL              | GENERIC                |   |
| 94   | [No user  should own most of the supply.]()                                                                                                            | QA/NC    | ALL              | GENERIC                |   |
| 95   | [ Take Compiler Warnings Seriously]()                                                                                                                  | QA/NC    | ALL              | GENERIC                |   |
| 96   | [ Restrict the Amount of Ether.]()                                                                                                                     | QA/NC    | ALL              | GENERIC                |   |
| 97   | [Keep contract Small and Modular]()                                                                                                                    | QA/NC    | ALL              | GENERIC                |   |
| 98   | [Include a Fail-Safe Mode]()                                                                                                                           | QA/NC    | ALL              | GENERIC                |   |
| 99   | [Ask for Peer Review]()                                                                                                                                | QA/NC    | ALL              | GENERIC                |   |
| 100  | [ Improved Security Through Bytecode Verification]()                                                                                                   | QA/NC    | ALL              | GENERIC                |   |
| 101  | [ Add a timelock to critical functions]()                                                                                                              | QA/NC    | ALL              | GENERIC                |   |
| 102  | [Use a single file for all system-wide constants]()                                                                                                    | QA/NC    | ALL              | GENERIC                |   |
| 103  | [ Insufficient test coverage]()                                                                                                                        | QA/NC    | ALL              | GENERIC                |   |
| 104  | [For modern and more readable code; update import usages]()                                                                                            | QA/NC    | ALL              | GENERIC                |   |
| 105  | [WETH address definition can be use directly  ]()                                                                                                      | QA/NC    | ALL              | GENERIC                |   |
| 106  | [Add to indexed parameter for countable Events]()                                                                                                      | QA/NC    | ALL              | GENERIC                |   |
| 107  | [Include return parameters in NatSpec comments]()                                                                                                      | QA/NC    | ALL              | GENERIC                |   |
| 108  | [abicoder v2 is enabled by default]()                                                                                                                  | QA/NC    | ALL              | GENERIC                |   |
| 109  | [ Danger “while” loop]()                                                                                                                               | QA/NC    | ALL              | GENERIC                |   |
| 110  | [Front-running aka transaction-ordering dependence  ]()                                                                                                | MED/HIGH | ALL              | GENERIC                |   |
| 111  | [DoS with block gas limit  ]()                                                                                                                         | MED/HIGH | ALL              | GENERIC                |   |
| 112  | [Block stuffing ]()                                                                                                                                    | MED/HIGH | ALL              | GENERIC                |   |
| 113  | [DoS with (unexpected) revert  ]()                                                                                                                     | MED/HIGH | ALL              | GENERIC                |   |
| 114  | [ Forcibly sending Ether to a contract]()                                                                                                              | MED/HIGH | ALL              | GENERIC                |   |
| 115  | [ Insufficient gas griefing ]()                                                                                                                        | MED/HIGH | ALL              | GENERIC                |   |
| 116  | [Reentrancy ]()                                                                                                                                        | MED/HIGH | ALL              | GENERIC                |   |
| 117  | [Arithmetic Underflow/Overflow]()                                                                                                                      | MED/HIGH | ALL              | GENERIC                |   |
| 118  | [Phishing Attacks (via tx origin) ]()                                                                                                                  | MED/HIGH | ALL              | GENERIC                |   |
| 119  | [Randomness Vulnerabilities]()                                                                                                                         | MED/HIGH | ALL              | GENERIC                |   |
| 120  | [Access Control and Default Vulnerabilities]()                                                                                                         | MED/HIGH | ALL              | GENERIC                |   |
| 121  | [Replay Attacks]()                                                                                                                                     | MED/HIGH | ALL              | GENERIC                |   |
| 122  | [ Flash Loans Attack  ]()                                                                                                                              | MED/HIGH | ALL              | GENERIC                |   |
| 123  | [DAO and Governance Attacks ]()                                                                                                                        | MED/HIGH | ALL              | GENERIC                |   |
| 124  | [Oracle Manipulation]()                                                                                                                                | MED/HIGH | ALL              | GENERIC                |   |
| 125  | [ Call/Delegate Call Attack   ]()                                                                                                                      | MED/HIGH | ALL              | GENERIC                |   |
| 126  | [  Uninitialised Storage Pointers  ]()                                                                                                                 | MED/HIGH | ALL              | GENERIC                |   |
| 127  | [ External Contract Referencing]()                                                                                                                     | MED/HIGH | ALL              | GENERIC                |   |
| 128  | [Entropy Illusion  ]()                                                                                                                                 | MED/HIGH | ALL              | GENERIC                |   |
| 129  | [ Floating Points and Precision   ]()                                                                                                                  | MED/HIGH | ALL              | GENERIC                |   |
