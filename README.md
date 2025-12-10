# import matplotlib.pyplot as plt

def fibonacci(n):
    """
    Return a list of first n Fibonacci numbers (starting from 0, 1).
    """
    if n <= 0:
        return []
    if n == 1:
        return [0]
    seq = [0, 1]
    while len(seq) < n:
        seq.append(seq[-1] + seq[-2])
    return seq

def plot_fibonacci(seq):
    """
    Plot Fibonacci sequence values vs their index.
    """
    plt.figure(figsize=(8, 5))
    x = list(range(len(seq)))
    y = seq
    plt.plot(x, y, marker='o', linestyle='-', color='blue')
    plt.title(f"Fibonacci Series (first {len(seq)} terms)")
    plt.xlabel("Index (n)")
    plt.ylabel("Fibonacci number F(n)")
    plt.grid(True)
    plt.show()

def main():
    n_terms = int(input("Enter number of Fibonacci terms to generate: "))
    fib_seq = fibonacci(n_terms)
    print("Fibonacci sequence:", fib_seq)
    plot_fibonacci(fib_seq)

if __name__ == "__main__":
    main()
