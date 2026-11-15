# Java Prime Number Checker

A small Java console program that reads an integer and tells whether it is a prime number.

## What Is a Prime Number?

A prime number is greater than 1 and divisible only by 1 and itself, such as 2, 3, 5, 7, and 11.

## How It Works

1. Numbers less than or equal to 1 are not prime.
2. For any other number, the loop tries every divisor `i` from 2 up to `number - 1`.
3. If `number % i == 0` for any `i`, the number has another divisor, so it is not prime and the loop stops with `break`.
4. If no divisor is found, the number is prime.

```java
boolean isPrime = true;

if (number <= 1) {
    isPrime = false;
} else {
    for (int i = 2; i < number; i++) {
        if (number % i == 0) {
            isPrime = false;
            break;
        }
    }
}
```

## Sample Runs

```
Enter a number: 7
7 is a prime number.
```

```
Enter a number: 10
10 is not a prime number.
```

| Input | Result |
|-------|--------|
| 2 | Prime |
| 7 | Prime |
| 10 | Not prime |
| 1 | Not prime |
| 0 or negative | Not prime |

## Requirements

- Java Development Kit (JDK) 8 or higher

## Getting Started

```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
javac PrimeNumber.java
java PrimeNumber
```

## Notes

- The loop checks every number below the input, which works but is slow for very large numbers. It is enough to check divisors up to the square root of the number (`i * i <= number`).
- Entering something that is not a whole number throws an `InputMismatchException`.

## Project Structure

```
.
├── PrimeNumber.java
└── README.md
```

## Possible Improvements

- Stop the loop at the square root of the number
- Move the check into a method such as `isPrime(int n)`
- Print all prime numbers up to a limit
- Handle invalid input with `hasNextInt()`
