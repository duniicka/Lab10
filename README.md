import numpy as np
def f(x):
    return x + 3 * (x - 6.09)**(1/3)
def f_prime(x):
    return 1 + (x - 6.09)**(-2/3)
x0 = 4.5
tolerance = 1e-6
max_iterations = 1000
x_new = x0
for _ in range(max_iterations):
    x_old = x_new
    x_new = x_old - f(x_old) / f_prime(x_old)
    if abs(x_new - x_old) < tolerance:
        break
print(x_new)
