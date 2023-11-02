import numpy as np

n = 4
adj_matrix = [[0, 1, 1, 1],
              [0, 0, 0, 1],
              [0, 1, 0, 1],
              [0, 0, 1, 1]]

print("the entered matrix is:")
for row in adj_matrix:
    print(row)

out_deg = [sum(row) for row in adj_matrix]
print("the number of out-degrees in each node:")
for i in range(n):
    print(f'Node {i + 1}: {out_deg[i]}')

a = np.zeros((n, n), dtype=float)
for i in range(n):
    for j in range(n):
        if adj_matrix[i][j] == 1:
            a[i][j] = round(1 / out_deg[j], 2)

print("Transition matrix:")
print(a)

X = np.ones((n, 1), dtype=float)
prev = np.array([])

print("\nFinal matrix after 7 transitions:")

for i in range(0, 7):
    X = a @ X
    prev = X
    print(f'\n{X}')

ans = dict()
for i in range(0, X.size):
    ans[f'Page {i + 1}'] = X[i][0]

ans = dict(sorted(ans.items(), key=lambda item: -item[1]))
ctn = 1

for i in ans:
    print(f'\nRank {ctn}: {i}')
    ctn += 1
