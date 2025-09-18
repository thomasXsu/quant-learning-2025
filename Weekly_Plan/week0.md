# September 18–21, 2025 — Warm-Up Week Plan

This is my **warm-up week task list** as I begin my journey into Quant / Risk / Asset Management.  
The goal is to set up the environment, run the first small demo, import the Notion schedule, and build a habit of study and reflection.  

---

## 📅 Task Schedule

### September 18 (Thursday)  
**Goal**: Environment setup + GitHub repository  
- [x] Install **Python 3.11** (or confirm `python --version` ≥ 3.10).  
- [x] Install the development environment:  
  ```bash
  pip install jupyterlab pandas numpy matplotlib statsmodels yfinance cvxpy
  ```  
  Save it in `requirements.txt` and run:  
  ```bash
  pip install -r requirements.txt
  ```  
- [x] Create a new GitHub repository: **quant-learning-2025**.  
- [x] Run locally:  
  ```bash
  jupyter lab
  ```  
  Confirm that you can create a new notebook.  

---

### September 19 (Friday)  
**Goal**: Probability & statistics basics  
- [ ] Study [Khan Academy Statistics and Probability](https://www.khanacademy.org/math/statistics-probability)  
  - Watch 2 lessons: `Mean` and `Variance`.  
- [ ] Write a 20-line Python script:  
  ```python
  import yfinance as yf
  data = yf.download("SPY", start="2020-01-01", end="2023-12-31", interval="1mo")
  returns = data['Adj Close'].pct_change().dropna()
  print("Mean:", returns.mean())
  print("Variance:", returns.var())
  returns.hist(bins=30)
  ```  
- [ ] Upload the notebook to the GitHub repository.  

---

### September 20 (Saturday)  
**Goal**: First step in asset pricing (CAPM)  
- [ ] Watch: [CAPM Explained in 5 minutes](https://www.youtube.com/watch?v=4bqn1uT2XGk)  
- [ ] Download AAPL stock data and run regression with market (SPY):  
  ```python
  import statsmodels.api as sm
  import yfinance as yf

  stock = yf.download("AAPL", start="2020-01-01", end="2023-12-31", interval="1mo")['Adj Close'].pct_change().dropna()
  market = yf.download("SPY", start="2020-01-01", end="2023-12-31", interval="1mo")['Adj Close'].pct_change().dropna()

  X = sm.add_constant(market)
  model = sm.OLS(stock, X).fit()
  print(model.summary())
  ```  
- [ ] Interpret the results:  
  - Constant = α  
  - Coefficient = β  
- [ ] Write a 1-page PDF summary: “My First CAPM Regression”.  

---

### September 21 (Sunday)  
**Goal**: Organize workspace + build reflection habit  
- [ ] Browse [QuantStart Free Resources](https://www.quantstart.com/articles/Free-Quantitative-Finance-Resources/) and bookmark: Probability & Statistics, Backtesting, Fixed Income.  
- [ ] Write a 1-page weekly reflection: What did I learn? Where did I get stuck? What will I improve next week?  

---

## 🔁 Mentor Actions (Warm-Up Week)  
- [ ] Update LinkedIn profile:  
  “Currently exploring Quant/Risk/Asset Management. Building small quant projects in Python.”  
- [ ] Follow:  
  - [PyQuantNews](https://www.pyquantnews.com/)  
  - [QuantStart](https://twitter.com/QuantStart)  
  - [Two Sigma Careers](https://www.twosigma.com/careers/)  
- [ ] Send 1 LinkedIn connection request, explaining that I’m learning quant and would like to know more about their work.  

---

## ✅ Completion Checklist for the Week  
- [ ] Python environment + GitHub repo ✔  
- [ ] SPY mean/variance notebook ✔  
- [ ] CAPM regression notebook ✔  
- [ ] Notion weekly plan imported ✔  
- [ ] LinkedIn profile updated ✔  
