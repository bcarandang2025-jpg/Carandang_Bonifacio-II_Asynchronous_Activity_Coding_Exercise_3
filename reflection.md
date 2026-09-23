1. Conceptual Distinction

1.1 What error occurred when trying to access atm.__pin directly? Why does Python behave this way?
- When I tried to access atm.__pin directly, I got an AttributeError. This happened because __pin is a private attribute created using two underscores. Python uses name mangling to make these types of attributes harder to access directly from outside the class. This is useful for protecting sensitive information like a PIN because it helps prevent it from being accidentally accessed or changed.

1.2 How did using @property allow you to change internal data structures or add validation without altering the public API for the caller?
- Using @property made it easier to control how the balance is accessed and changed. I can simply use account.balance without needing to know how the actual value is stored internally. The setter also allows me to add validation, such as preventing the balance from becoming negative. This means I can change the internal way the balance works while keeping the same way for the user to access it.

1.3 How did the ATM class demonstrate abstraction relative to the underlying BankAccount logic?
- The ATM class demonstrates abstraction by hiding the complicated processes inside the BankAccount class. As a user, I don't need to directly change the balance or access the transaction records. Instead, I can use simple methods like check_balance, perform_deposit, and perform_withdrawal. The complicated operations are handled in the background, while the user only interacts with the functions that are available to them.

2. Final Reflection Questions

2.1 What error occurred when trying to access atm.__pin directly? Why does Python behave this way?
- When I tried to access atm.__pin directly, I received an AttributeError. This happened because __pin is a private attribute in the ATM class. Python uses name mangling for attributes that start with two underscores, which makes them more difficult to access directly from outside the class. This helps protect important information, such as a user's PIN and other personal data, from being accidentally accessed or changed.

2.2 How did using @property allow you to change internal data structures or add validation without altering the public API for the caller?
- Using @property allowed me to access the balance using account.balance instead of using a separate getter method. Even though the actual value is stored internally as _balance, the user does not need to know how it is stored. The setter also allows validation to be added, such as preventing the balance from being set to a negative number. This allows the internal code to change without affecting how the user interacts with account.balance.

2.3 How did the ATM class demonstrate abstraction relative to the underlying BankAccount logic?
- The ATM class demonstrates abstraction by hiding the more complicated account operations from the user. Instead of directly accessing _balance or _transactions, the user can simply use methods like check_balance, perform_deposit, and perform_withdrawal. The user does not have direct access to edit or change the internal account information. This makes the system easier and safer to use.
