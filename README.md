# Huffman-Shannon_fano
# Aim:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that by drawing the tree diagram, and 
Calculate the average code word length, entropy, variance, redundancy, and efficiency.
# Tools Required:
Python: A versatile language for scientific computing and signal processing.
NumPy & Matplotlib: Libraries for numerical operations and high-quality visualizations, essential for demonstrating sampling.
# Program:
```
import numpy as np
import math

L = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of samples: "))

for i in range(n):
    pr = float(input(f"Enter the probability of sample value {i + 1}: "))  
    p.append(pr)

for j in range(n):
    l = float(input(f"Enter the length of the sample value {j + 1}: "))  
    lk.append(l)

for k in range(n):
    L += p[k] * lk[k]

for k in range(n):
    hs += p[k] * math.log(1 / p[k], 2)
hs = round(hs, 3)

eff = round(hs / L, 3)
red = round(1 - eff, 3)

var = sum(p[k] * (lk[k] - L) ** 2 for k in range(n))
var = round(var, 3)

print("\nResults:")
print(f"Average Codeword Length: {L}")
print(f"Entropy: {hs}")
print(f"Efficiency: {eff * 100} %")
print(f"Redundancy: {red}")
print(f"Variance: {var}")
```
# Calculation:
``` 
<img width="1137" height="493" alt="image" src="https://github.com/user-attachments/assets/569f734e-760b-4b16-a82e-c123d85b16b0" />

```
# Output
```
Attach the Output waveform
``` 
# Results:
```
For the given probabilities {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25}:

Average Codeword Length: 2.625
Entropy: 2.625
Efficiency: 100.0%
Redundancy: 0.0
Variance: 0.484
```
