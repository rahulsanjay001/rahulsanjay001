import math

# Function to check if a number is prime
def is_prime(num):
    if num < 2:
        return False
    for i in range(2, int(math.sqrt(num)) + 1):
        if num % i == 0:
            return False
    return True

# Input: list of distinct natural numbers
numbers = list(map(int, input().split()))
n = numbers[0]  # q is the smallest natural number
numbers.remove(n)  # Remove q from the list

# Iterate through possible values of p starting from n
p = n
while True:
    divisible = True
    for num in numbers:
        if p % num != n:
            divisible = False
            break
    if divisible and is_prime(p):
        print(p)
        break
    p += 1

# If no suitable p is found, print "None"
if p >= 10**10:
    print("None")
