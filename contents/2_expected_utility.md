# 第2回　期待効用理論

<!-- ## 講義概要 -->

### 復習

### 到達目標

- 期待効用理論を理解し，期待効用を計算できる．

### キーワード

- 意思決定
- 選好
- 効用，期待効用理論
- リスク回避型・リスク中立型・リスク愛好型
- ベイジアン仮説

## 意思決定のモデル

選択対象の集合：$X$

## 不確実性の下での意思決定

ゲーム理論では，他者の行動だけでなく，確率的な結果が関わる場面が多い．

例として次を挙げる．

- 相手のタイプが確率的にしか分からない（情報不完備ゲーム）
- ランダム化した戦略を用いる（混合戦略）
- 環境の状態が確率的に変動する（経済状態，通信品質など）

これらを扱うために，まず不確実性の下での合理的意思決定の基礎として**期待効用理論**を学ぶ．

---

## 2．基本概念：結果，くじ，選好

### 結果（outcome）

結果の集合を $X$ とする．要素 $x\in X$ は「金銭額」「評価」「状態」などを表す．

### くじ（lottery）

有限個の結果に対して確率が割り当てられたものをくじと呼ぶ．

結果 $x_1,\dots,x_m$ と確率 $p_1,\dots,p_m$（$\sum_k p_k=1$）によるくじを

$$
L = (p_1,x_1;\; p_2,x_2;\; \dots;\; p_m,x_m)
$$

と表す．

### 選好（preference）

意思決定主体の選好関係を $\succeq$ と表す．

$L \succeq M$ は「くじ $L$ を $M$ 以上に好む」ことを意味する．

---

## 3．期待効用仮説

直観的には，意思決定主体がくじを評価するとき

- 各結果 $x$ に対し効用 $u(x)$ を与え，
- 確率で重み付けして平均を取る

という形で比較するという仮説である．

$$
EU(L)=\sum_{k=1}^m p_k\,u(x_k)
$$

この形で比較できるとき，選好は期待効用で表現されるという．

---

## 4．期待効用定理（表現定理）の主張

期待効用理論の核心は，次の主張である．

> くじに対する選好 $\succeq$ が一定の合理性公理を満たすならば，ある効用関数 $u$ が存在して，すべてのくじを期待効用で順位づけできる．
> 

すなわち，公理 $\Rightarrow$ 表現（期待値の形）である．

本講義では証明の詳細には深入りせず，公理の意味と使い方に重点を置く．

---

## 5．公理（合理性条件）の内容

教科書に沿って，重要な公理を整理する．

### 完備性（completeness）

任意の2つのくじ $L,M$ について，$L\succeq M$ または $M\succeq L$ が成り立つ．

比較不能がないという仮定である．

### 推移性（transitivity）

$L\succeq M$ かつ $M\succeq N$ なら $L\succeq N$．

選好が矛盾しないという条件である．

### 連続性（continuity）

極端に飛びがある選好を排除し，「少し混ぜれば同程度になる」状況を保証する．

直観としては，最良と最悪のくじを適当に混合することで中間のくじと無差別になるような混合比が存在する，という性質である．

### 独立性（independence）

くじ $L,M,N$ と $0<\alpha<1$ に対し

$$
L\succeq M \iff \alpha L + (1-\alpha)N \succeq \alpha M + (1-\alpha)N
$$

が成り立つ．

ここで $\alpha L+(1-\alpha)N$ は「確率 $\alpha$ で $L$，確率 $1-\alpha$ で $N$ を行うくじ」を意味する．

独立性は期待値形式を導く決定的条件であり，期待効用理論の最も特徴的な公理である．

---

## 6．効用の一意性（アフィン変換）

期待効用を表す効用関数 $u$ は一般に一意ではない．

しかし次の形の変換では同じ選好を表す．

$$
v(x)=a\,u(x)+b \quad (a>0)
$$

このように，期待効用の効用関数は**正のアフィン変換まで一意**である．

これはゲーム理論で効用を扱う際の重要な注意点である．

---

## 7．危険回避と効用関数の形（応用的視点）

金銭額 $m$ を結果とするとき，効用 $u(m)$ の曲率が態度を表す．

- 危険回避（risk averse）：$u$ が凹（concave）
- 危険中立（risk neutral）：$u$ が線形
- 危険愛好（risk loving）：$u$ が凸（convex）

この議論は，後のオークション，交渉，不完備情報ゲームにおいて頻出する．

---

## 演習の目的

- くじをデータ構造として表す
- 期待効用を正しく計算できる
- 効用関数の形（凹凸）が意思決定に与える影響を，計算で確認する
- 次回以降（戦略形ゲーム，混合戦略，不完備情報）で再利用できる形式にする

---

## 演習0　くじの表現（提出用）

::: {admonition} 提出
次の「くじ」を文章で定義し，確率と結果を整理して提出する．
:::

- くじ \(L\)：確率 \(\*\*\) で結果 \(\*\*\)，確率 \(\*\*\) で結果 \(\*\*\)
- くじ \(M\)：確率 \(\*\*\) で結果 \(\*\*\)，確率 \(\*\*\) で結果 \(\*\*\)
- あなたの直観ではどちらが好ましいか：
- その理由：

---

## 演習1　期待効用の計算（手計算）

次の効用関数を用いる．

$$
u(x)=\sqrt{x} \quad (x\ge 0)
$$

くじ $L=(0.5,\,100;\;0.5,\,0)$ と

確実な結果 $C=(1,\,40)$ を比較する．

1. $EU(L)$ を計算せよ．
2. $EU(C)$ を計算せよ．
3. この意思決定主体はどちらを選ぶか．
4. なぜこの選択が「危険回避」と整合的か説明せよ．

---

## 演習2　Pythonで期待効用を計算する（提出用セル）

以下のコードセルを実行し，演習1の計算結果と一致することを確認せよ．

```python
import math

def expected_utility(lottery, u):
    """
    lottery: list of (p, x)
    u: utility function u(x)
    """
    return sum(p * u(x) for p, x in lottery)

u = lambda x: math.sqrt(x)

L = [(0.5, 100), (0.5, 0)]
C = [(1.0, 40)]

EU_L = expected_utility(L, u)
EU_C = expected_utility(C, u)

EU_L, EU_C
```

---

## 演習3　効用関数の違いによる選択の変化

同じくじ ($L$) と確実な結果 ($C$) に対して，次の3つの効用関数で比較せよ．

- 危険回避：($u_1(x)=\sqrt{x}$)
- 危険中立：($u_2(x)=x$)
- 危険愛好：($u_3(x)=x^2$)

### 提出用セル（Python）

```python
u1 = lambda x: math.sqrt(x)
u2 = lambda x: x
u3 = lambda x: x**2

for name, ufun in [("sqrt(x)", u1), ("x", u2), ("x^2", u3)]:
    EU_L = expected_utility(L, ufun)
    EU_C = expected_utility(C, ufun)
    print(name, "EU(L)=", EU_L, "EU(C)=", EU_C, "choose", "L" if EU_L > EU_C else "C")
```

### 提出（Markdown）

- 3つの効用関数で選択がどう変わったか
- その理由を凹凸（危険回避・中立・愛好）と結びつけて説明せよ

---

## 演習4　くじをJSONとして保存する（次回以降に再利用）

第10回（情報不完備ゲーム）などでは「タイプの確率」や「状態の確率」が重要になる．そこで，くじをデータとして保存し再利用する．

### 提出用セル（Python）

```python
import json

lotteries = {
    "L": {"description": "0.5 for 100, 0.5 for 0", "lottery": L},
    "C": {"description": "certain 40", "lottery": C},
}

with open("lecture2_lotteries.json", "w", encoding="utf-8") as f:
    json.dump(lotteries, f, ensure_ascii=False, indent=2)

print("Saved:", "lecture2_lotteries.json")
```

---

## 演習5（次回以降への接続）混合戦略との対応

混合戦略は「戦略に確率を割り当てたもの」である．

期待効用の計算は，混合戦略の利得計算と同じ構造を持つ．

### 確認問題（提出）

- くじの確率 ($p_k$) と，混合戦略の確率は何に対応するか
- 結果 ($x_k$) と，ゲーム理論における「利得」は何に対応するか
- 期待効用の式が，混合戦略の期待利得の計算にどう現れるか

---

# 演習（自分の効用関数を推定する）

```bash
import math
import random
import numpy as np
import pandas as pd

# 推定で scipy を使う
from scipy.optimize import minimize_scalar

# =========================
# 1. 効用関数と期待効用
# =========================

def crra_utility(x, gamma):
    """
    CRRA効用関数
    x > 0 を想定
    gamma = 1 のときは log x
    """
    x = max(x, 1e-8)  # log(0)回避
    if abs(gamma - 1.0) < 1e-8:
        return math.log(x)
    return (x ** (1.0 - gamma) - 1.0) / (1.0 - gamma)

def expected_utility(lottery, gamma):
    """
    lottery: [(p1, x1), (p2, x2), ...]
    """
    return sum(p * crra_utility(x, gamma) for p, x in lottery)

# =========================
# 2. 実験問題の生成
# =========================

def generate_lottery():
    """
    2点分布のくじを1つ生成する
    """
    p = random.choice([0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9])
    x_high = random.choice([20, 30, 40, 50, 60, 80, 100, 120, 150])
    x_low = random.choice([0, 5, 10, 15, 20, 30, 40])

    # high > low になるように補正
    if x_high <= x_low:
        x_high = x_low + random.choice([10, 20, 30, 40])

    return [(p, x_high), (1 - p, x_low)]

def lottery_to_text(lottery):
    return " + ".join([f"{p:.1f}で{x}" for p, x in lottery])

def generate_question_set(n_questions=12, seed=42):
    random.seed(seed)
    questions = []

    for i in range(n_questions):
        A = generate_lottery()
        B = generate_lottery()

        questions.append({
            "id": i + 1,
            "A": A,
            "B": B,
            "A_text": lottery_to_text(A),
            "B_text": lottery_to_text(B),
        })

    return questions

# =========================
# 3. 問題を表示
# =========================

def show_questions(questions):
    rows = []
    for q in questions:
        rows.append({
            "問題番号": q["id"],
            "選択肢A": q["A_text"],
            "選択肢B": q["B_text"],
        })
    return pd.DataFrame(rows)

# =========================
# 4. 回答を入力
# =========================

def collect_answers_interactive(questions):
    """
    Notebook上で対話的に回答を集める
    A または B を入力
    """
    answers = []

    print("各問題について A または B を入力してください．\n")
    for q in questions:
        print(f"問題 {q['id']}")
        print(f"  A: {q['A_text']}")
        print(f"  B: {q['B_text']}")
        while True:
            ans = input("選択（A/B）: ").strip().upper()
            if ans in ["A", "B"]:
                answers.append(ans)
                break
            print("A または B を入力してください．")
        print()

    return answers

# =========================
# 5. 確率的選択モデル
# =========================

def choice_prob_logit(EU_A, EU_B, beta=1.0):
    """
    ロジット型の選択確率
    P(A) = exp(beta*EU_A) / (exp(beta*EU_A)+exp(beta*EU_B))
    数値安定化のため差分で計算
    """
    d = beta * (EU_A - EU_B)

    # オーバーフロー回避
    if d >= 0:
        return 1.0 / (1.0 + math.exp(-d))
    else:
        ed = math.exp(d)
        return ed / (1.0 + ed)

def negative_log_likelihood(gamma, questions, answers, beta=1.0):
    """
    与えられた gamma に対する負の対数尤度
    """
    nll = 0.0
    eps = 1e-12

    for q, ans in zip(questions, answers):
        EU_A = expected_utility(q["A"], gamma)
        EU_B = expected_utility(q["B"], gamma)
        pA = choice_prob_logit(EU_A, EU_B, beta=beta)

        if ans == "A":
            nll -= math.log(max(pA, eps))
        else:
            nll -= math.log(max(1 - pA, eps))

    return nll

# =========================
# 6. gamma を推定
# =========================

def estimate_gamma(questions, answers, beta=1.0, bounds=(-2.0, 3.0)):
    """
    負の対数尤度を最小化して gamma を推定
    """
    result = minimize_scalar(
        lambda g: negative_log_likelihood(g, questions, answers, beta=beta),
        bounds=bounds,
        method="bounded"
    )
    return result

# =========================
# 7. 結果表示
# =========================

def interpret_gamma(gamma, tol=0.15):
    if gamma > tol:
        return "危険回避的"
    elif gamma < -tol:
        return "危険愛好的"
    else:
        return "危険中立に近い"

def summarize_results(questions, answers, gamma_hat, beta=1.0):
    rows = []
    for q, ans in zip(questions, answers):
        EU_A = expected_utility(q["A"], gamma_hat)
        EU_B = expected_utility(q["B"], gamma_hat)
        pred = "A" if EU_A >= EU_B else "B"

        rows.append({
            "問題番号": q["id"],
            "A": q["A_text"],
            "B": q["B_text"],
            "回答": ans,
            "推定モデルの予測": pred,
            "EU(A)": round(EU_A, 4),
            "EU(B)": round(EU_B, 4),
            "一致": ans == pred
        })

    df = pd.DataFrame(rows)
    accuracy = df["一致"].mean()

    print("推定された gamma =", round(gamma_hat, 4))
    print("解釈：", interpret_gamma(gamma_hat))
    print("予測一致率 =", round(accuracy, 3))
    print()

    return df

# =========================
# 8. 一連の実行
# =========================

questions = generate_question_set(n_questions=12, seed=42)

print("=== 実験問題一覧 ===")
display(show_questions(questions))

# 対話入力で回答収集
answers = collect_answers_interactive(questions)

# 推定
result = estimate_gamma(questions, answers, beta=1.0, bounds=(-2.0, 3.0))
gamma_hat = result.x

print("=== 推定結果 ===")
df_result = summarize_results(questions, answers, gamma_hat, beta=1.0)
display(df_result)
```

# 本日のまとめ

- 不確実性の下での選好は，合理性公理のもとで期待効用で表現できる．
- 効用関数は正のアフィン変換まで一意である．
- 効用関数の凹凸は危険回避・中立・愛好の態度に対応する．
- 期待効用計算は，混合戦略や不完備情報ゲームの基礎となる．

---

## 次回予告

第3回は戦略形ゲームである．プレイヤー・戦略・利得関数（利得行列）により相互作用を定式化し，後の均衡概念（第4回）につなげる．