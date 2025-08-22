# 6.3 Validation & Verification

## Common types of Verification:

### Data Entry verification:
- ensure what was entered matches the user's intend
- many different implementations.
	- (e.g. show password, or double entry)

### Data Transfer Verification:
- ensure that data received is the same as the data sent
- Ways of implementation:
	- **Parity Bits**: In every byte one bit states if the byte is odd or even (number of 1s). Then there are parity bits for rows and columns of bytes stating if the number of 1s for parity bits is even or odd.
	- **Checksums**: Somehow creating a unique value individual to the message that is processed by the checksum function. If the checksum for the sent and received data matches, then it's likely equal.
		- ↳ uses e.g. hashing or bit adding

---
## Parity Bit Explanation

*The top row represents the parity bits for each column. The first column represents the parity bits for each row.*

| | Parity Bits → | | | | | | |
|---|---|---|---|---|---|---|---|
|**Parity Bits ↓**| 1 | 1 | 0 | 0 | 0 | 1 | 1 |
|**0**| 0 | 0 | 1 | 0 | 1 | 1 | 1 |
|**0**| 1 | 1 | 0 | 0 | 1 | 0 | 1 |
|**0**| 1 | 0 | 1 | 1 | 1 | 0 | 0 |
|**1**| 0 | 0 | 1 | 1 | 0 | 1 | 0 |
|**1**| 1 | 1 | 0 | 1 | 0 | 1 | 1 |
|**0**| 1 | 0 | 0 | 1 | 0 | 1 | 1 |
|**0**| 1 | 1 | 1 | 0 | 0 | 1 | 0 |

---
## Book Notes ♡

- Validation and verification are processes used to improve data integrity. → doesn't guarantee it!
- Validation and verification happen during data transfer (usually?)

### Validation of Data Entry
⇒ Check if entered data meets specified requirements (is reasonable)
- validation only includes following checks: *(e.g. birth date < 2020)*
	- **presence check** → for entry fields
	- **format check** → (e.g. YY/MM/DD)
	- **length check** → (e.g. characters)
	- **range check** → (e.g. 1 to 12)
	- **limit check** → (e.g. > 100)
	- **type check** → (e.g. is integer?)
	- **existence check** → for files
> Validation doesn't guarantee data is correct

### Verification of Data Entry
⇒ ensuring data entered is alligned with what the user intended to enter
- doesn't guarantee entered data is correct
- Methods for data entry verification:
	- Double entry
	- Visual check, (showing what was entered)

---
## Check Digit
- a very simple implementation of check sum, used for ISBN (books) and barcodes
- only used for all-number strings
- How it works:
	- numbers are added, multiplied, etc. in various ways
	- final step is dividing the number and taking the remainder
	- the remainder is the check digit
	- usually 1 to 10 (but X is used for 10)

---
## Verification During Transfer

### One-Bit Parity Check
**Even parity** → all correct bytes must have an eaven number of 1s
**Odd Parity** → there must be an uneven number of 1s for it to get accepted

Assuming even parity: One parity bit is added to every 7 bits of data
`1 0 0 1 1 0 1 0`
↑ parity bit | data (7b)
↳ makes a total of 4 (even) 1s
- If any one bit is flipped, the 1s won't be even anymore
	- ↳ the entire byte will be resent
- we can detect when there was **only one error**!
- we don't know which bit is wrong

### Checksum
=> another method to validate accurate transfer
- **Sender:**
	- Transmission is devided into blocks.
	- at the end of each block a few bytes are reserved for the checksum.
	- All bytes in the block are treated as binary values and summed up
	- The sum is stored as the checksum.
	- The block is sent
- **Receiver:**
	- Adds all block bytes together and compares sum with the checksum
	- might accept block or request to have it resent.
↳ This process can't find the faulty bit position

---
## Good to know:
### Universal Product Code Checksum Verification
- UPC barcodes have 12 digits
	↳ 11 for the code, 1 as check digit
- Example code: `0 36000 29145 2` (coding + checksum)
- formula for check digit:
  1. $$ x = (\text{sum of odd position digits}) \times 3 + (\text{sum of even position digits}) $$
  2. $$ y = x \pmod{10} $$
  3. If $y \ne 0$, the check digit is $10-y$. If $y=0$, the check digit is $0$.

- **example:** `0 36000 29145 2`
  - $$ (0+6+0+2+1+5) \times 3 + (3+0+0+9+4) $$
  - $$ = 14 \times 3 + 16 = 42 + 16 = 58 $$
  - $$ 58 \pmod{10} = 8 $$
  - $$ 10 - 8 = 2 $$
  - 2 is the check digit ✓

---
## Exam Style Questions 1, 3, 5

**1.** 
   **a)** 
      i. accuracy ✓ and type⁻¹
      ii. Validation is concerned with the correctness of the form of the data, e.g. formatting. It checks if the data is feasible. Verification ensures that the data doesn't corrupt or unintentionally change along the way. ✓
      iv. As data validation is only concerned about the right format and data verification with the data being transmitted correctly, the data entered doesn't have to be correct. E.g. when asked to enter your name, you can just enter the name of your friend instead. It passes both validation and verification. ✓
      iii. Entry validation: Prompt the user to enter a value, e.g. his password two times to increase the chances of data integrity, i.e. the password being what the user intended it to be. ✓
          - *more detail: strong password, biometric tests, unauthorized acc.*
   **b)** The data is stored on a system that is password protected, and the hard-drive is encrypted ✓ *access rights*

**3.** 
   **a)** 
      i. First, the system has to decide if it chooses even or odd parity. ✓ This has to be equal for both the sending and receiving end. We assume even parity. ✓
         - **On the sending side:**
             - for each 7 bits, the number of ones is counted.
             - If the number is odd, a one is added at the parity bit to make the number even. ✓
             - The data is sent
         - **On the receiving end:**
             - The data is received and the ones are counted.
             - If a byte has an odd number of ones there was a mistake ✓ and the byte is requested again. ✓
      ii. Checksum works as follows: Data is split into blocks of data. To each block a few bytes are appended that will later contain the checksum. All bytes in the block are treated as if they were binary numbers and added together. ✓ Usually they undergo some complex calculations and are then stored on checksum. Often the last step is to take the mod of the value and store that as checksum. ✓
          - The value is recalculated on the receiving end and compared
   **b)** It cannot be determined which exact bit is wrong. → both
      - Only one mistake per byte can be recognized → parity bit
      - two might cancel
   **c)** ~~0v 0v 0x 1x 0v 1x 0v 0v~~ *bad question, actually 2d parity check*
      - bytes 3, 4, and 6 would be resend

**5.** Verification is needed to ensure that the data received is the same data that was sent.
Validation is needed to ensure the data is feasible, which increases the likelyhood of it being correct.
Both are needed to improve, not ensure data integrity.

**5.** 
   **Verification:** Ensures that data entered is what was intended
   - Can include comparison with the source data if there exists such source data
     - ↳ e.g. checksum
   - Options for manual data entry verification:
     - double entry check
     - visual check → show what was entered
   - For transmission verification:
     - checksum & check digit
     - parity bits
   
   **Validation:** Used to check if data is in the correct form and is the correct type
   - Checks might include:
     - type check
     - presence check
     - format check
     - range check
     - limit check
     - length check

Both are needed to improve the chances for data integrity, i.e. the data to be accurate. Validation and verification don't guarantee data integrity though.