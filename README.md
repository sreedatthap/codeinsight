# 🧠 CodeInsight — FAANG-Level AI Code Pattern Detector & Explainer

CodeInsight is an elite AI-powered system designed to analyze code snippets and generate **top-tier, structured technical documentation** — the kind you'd expect from senior engineers at Google, Amazon, or Microsoft.

Whether you're prepping for interviews, writing documentation, or building dev tools, **CodeInsight gives you crystal-clear insights** into how the code works, why it was written that way, and what patterns it follows.

---

## 🚀 Features

- 🔍 **Pattern Detection**: Detects common algorithmic patterns like DFS, BFS, DP, Greedy, Two-Pointer, Backtracking, Graph, etc.
- 🧠 **AI-Powered Explanations**: Generates ultra-clean, readable documentation in a consistent format — **exactly like a FAANG SDE-2/3 would explain it**.
- 🧱 **Segmented Output**:
  - `// Pattern Detected:` — Pattern classification (e.g., "Dynamic Programming – 0/1 Knapsack")
  - Inline commented code — well-documented with intent and strategy
  - `// Key Insights:` — High-level takeaways in bullet points
  - `// Sample Input and Output:` — Clear usage examples
  - `// Time and Space Complexity:` — No ambiguity, just direct analysis
- ⚙️ **Language Support**: Currently supports Python, with support for JavaScript and Java coming soon.
- 🛠️ **CLI & Web Interface (Coming Soon)**

---

## 📦 Example Output

> Input: A 0/1 Knapsack solution in Python

```python
// Pattern Detected: Dynamic Programming — 0/1 Knapsack using Bottom-Up Tabulation

def knapsack(weights, values, capacity):
    n = len(weights)
    dp = [[0 for _ in range(capacity + 1)] for _ in range(n + 1)]  # Initialize DP table

    for i in range(1, n + 1):  # Iterate through items
        for w in range(1, capacity + 1):  # Iterate through capacities
            if weights[i - 1] <= w:
                # Choose max between not including or including the item
                dp[i][w] = max(
                    dp[i - 1][w],
                    dp[i - 1][w - weights[i - 1]] + values[i - 1]
                )
            else:
                # Item too heavy; carry forward previous best
                dp[i][w] = dp[i - 1][w]

    return dp[n][capacity]  # Final result

// Key Insights:
- Uses bottom-up dynamic programming to build optimal substructure.
- Iterates through item/capacity pairs to maximize value within limits.
- Avoids repeated subproblem computation by storing intermediate results.
- Works well for standard 0/1 constraints (items cannot be reused).
- Space can be optimized to 1D DP if required.

// Sample Input and Output:
weights = [1, 3, 4, 5]
values = [10, 40, 50, 70]
capacity = 8
Output: 110

// Time and Space Complexity:
Time: O(n * capacity)
Space: O(n * capacity)
```

---

## 🧩 Use Cases

- ✅ Competitive programming preparation
- ✅ Codebase documentation at scale
- ✅ Building coding platforms or AI dev tools
- ✅ Generating smart documentation for interviews or portfolios

---

## 🛠 Tech Stack

- **Language**: Python, Java, C++, JavaScript
- **AI Models**: GPT-4 / Claude / Local LLMs via OpenRouter or LMStudio
- **Frontend (Optional)**: React.js + Tailwind CSS + Framer Motion
- **Backend**: FastAPI (Python)
- **Deployment**: Vercel (Frontend), Render (Backend)

---

## 🧪 Getting Started

```bash
# Clone the repo
git clone https://github.com/yourusername/codeinsight-ai.git
cd codeinsight-ai

# Install dependencies (Python 3.8+)
pip install -r requirements.txt

# Run backend server
uvicorn app.main:app --reload

# Access the API at:
http://localhost:8000/docs
```
---

## 📄 License

MIT License — free for personal and commercial use.

---

## 💬 Credits

Built with ❤️ by Sree Dattha P — inspired by the way senior engineers explain code in whiteboard interviews and code reviews.

---

## 🌟 Star This Repo

If you find this useful, **star it** and share it with devs prepping for coding interviews. Help others write better code, with better understanding.
