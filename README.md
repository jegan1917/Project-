def subsets(arr):
    result = []

    def backtrack(i, curr):
        result.append(curr[:])

        for j in range(i, len(arr)):
            curr.append(arr[j])
            backtrack(j + 1, curr)
            curr.pop()   # backtracking

    backtrack(0, [])
    return result


# Driver code
arr = list(map(int, input("Enter the elements: ").split()))
ans = subsets(arr)

print("All subsets are:")
for s in ans:
    print(s)
