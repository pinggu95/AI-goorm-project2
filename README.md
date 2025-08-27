# AI-goorm-project2

https://www.kaggle.com/competitions/jigsaw-agile-community-rules

# 🧠 Jigsaw - Agile Community Rules Classification

> **Using AI models to help moderators uphold community-specific norms.**  
> 댓글이 커뮤니티 규칙을 위반했는지를 분류하는 모델을 개발하는 케글 대회입니다.

---

## 📌 Overview

Reddit에 댓글을 남겼다가 삭제된 경험이 있나요?  
각 서브레딧(subreddit)은 각자의 규칙을 갖고 있으며, 이를 이해하고 예측하는 일은 어렵습니다.  
이 대회에서는 실제 Reddit 데이터를 기반으로 **댓글이 특정 규칙을 위반했는지를 예측하는 모델**을 개발합니다.

---

## 📅 Timeline

- 🟢 **Start**: 약 1개월 전
- ⏳ **Deadline**: 약 2개월 남음

---

## 🎯 Task Description

- **Task Type**: Binary Classification
- **Goal**: 각 댓글이 특정 규칙을 위반했는지 여부 예측
- **Dataset Source**:
  - 다양한 subreddit의 **규칙, 댓글, 모더레이션 로그**
  - 실제 규칙을 바탕으로 작성된 **가상의 규칙 목록(hypothetical rules)**
  - **소규모 labeled dev set** 제공 (few-shot 학습 가능)

---

## 📚 Background

이 대회는 아래 연구진들의 작업을 기반으로 합니다:

- Deepak Kumar, Yousef AbuHashem, Zakir Durumeric: LLM을 활용한 Reddit 댓글 위반 이유 추론 연구
- Eshwar Chandrasekharan, Eric Gilbert: 수백만 개의 모더레이션 댓글을 수집한 연구

이 대회는 커뮤니티의 고유한 규범을 이해하고, 실제 적용 가능한 **AI 기반 모더레이션 도구**를 설계하는 기회를 제공합니다.

---

## 📊 Evaluation

- **Metric**: `Column-Averaged AUC (Area Under the ROC Curve)`
- **Note**: 다중 이진 분류(Multi-label classification) 문제입니다.
  - 각 규칙별로 확률 예측
  - 규칙들 간 상관관계 고려하지 않음

---

## 📁 Submission Format

- 제출 파일은 아래와 같은 CSV 형식이어야 합니다:

```
...
row_id,rule_1,rule_2,rule_3,...,rule_N
1,0.01,0.73,0.00,...,0.02
2,0.20,0.09,0.11,...,0.00
...
각 row_id에 대해 규칙 위반 확률 (0.0 ~ 1.0) 을 예측하여 제출합니다.
