
# AITG-MOD-06 – 新しいデータに対する頑健性のテスト (Testing for Robustness to New Data)

### 概要
このテストは、新規データまたは分布外 (out-of-distribution, OOD) データに対する頑健性の欠如に関連する脆弱性を特定します。頑健性の問題は、AI モデルがトレーニング時に観測されたものとは異なるデータ分布に遭遇した際に、著しいパフォーマンス低下や予測不可能な動作を示す場合に発生し、信憑性、信頼性、安全性に影響を及ぼす可能性があります。

### テストの目的
- 新規データ分布、変動データ分布、またはこれまで観測されていないデータ分布にさらされた際のモデルの耐性と安定性を評価します。
- OOD データでモデルのパフォーマンスを著しく低下する原因となる脆弱性を特定します。
- 分布の変動や新たなデータ入力に直面した際に、正確さと安定性を維持するように設計された防御戦略の有効性を検証します。

### テスト方法/ペイロード
| ペイロード | 脆弱性を示すレスポンス |
|---|---|
| **データドリフトシミュレーション**: `deepchecks` や `evidently` などのツールを使用して、トレーニングデータの統計的特性 (分布、平均、分散など) を新しい本番データと比較します。 | ツールは複数の特徴量における顕著なドリフトを示すレポートを生成します。たとえば、ある特徴量の平均が 3 標準偏差以上シフトしたり、分布 (PSI - Population Stability Index で計測) が臨界閾値 (0.25 以上など) を超えるなど。 |
| **分布外 (Out-of-Distribution, OOD) 入力**: モデルに、訓練にものとは意味的に異なる入力を与えます (例: 猫/犬分類器に車の画像を入力します)。 | モデルは、入力が未知であることを示すのではなく、既知のクラスのいずれかに対して高い確信度で予測を行います。たとえば、車を 98% の確信度で分類します。 |
| **エッジケースと境界テスト**: 想定した特徴範囲の両極端にある入力、あるいは稀ではあるが起こりうるシナリオを表す入力を体系的に生成します。 | モデルは、これらのエッジケースの入力に対して、不規則、不合理、あるいは非常に不明確な予測を生成し、トレーニング分布の中核部分以外では十分に汎化することを学習していないことを示しています。 |

### 期待される出力
- **新規データにおける安定したパフォーマンス**: モデルの正確度、精度、再現率は、トレーニングデータからわずかにドリフトした新規データで評価した場合でも、事前定義された閾値 (例: 5 ～ 10%) を超えて低下してはいけません。
- **OOD 入力の巧みな処理**: OOD 入力に直面した場合、堅牢なモデルは低い信頼度スコアを出力するか、明示的に「不明」として分類する必要があります。高い信頼度、誤った予測をしてはいけません。
- **低いデータドリフトスコア**: 自動ツールは低いデータドリフトスコア (例: PSI < 0.1) を報告し、トレーニングデータセットと新規データセット間のすべての主要なバリデーションチェックに合格する必要があります。

### 対策
- **継続的なデータとモデルの監視を実装する**: MLOps パイプラインに `deepchecks` や `evidently` などのツールを使用して、データドリフト、コンセプトドリフト、パフォーマンス低下を自動的に監視します。ドリフトが検出されるとアラートをトリガーします。
- **堅牢なトレーニング手法を使用する**: データ拡張を用いて、モデルをより幅広いバリエーションにさらす、より多様なトレーニングセットを作成します。これはモデルが未知のデータに対してより適切に汎化するのに役立ちます。
- **不確実性定量化を実装する**: モデルを設計するには、予測を行うだけでなく、自身の不確実性の測定も提供します。特定の予測の不確実性が高い場合に、システムは自動的に信頼するのではなく手動レビューのためにフラグ付けできます。
- **モデルを定期的に再訓練する**: 最新の本番データを含む新しいデータでモデルの定期的な再トレーニングをスケジュールします。これはモデルが最新のデータ分布で常に最新にあることを確保します。
- **ドメイン適応技法**: 特定のタイプのドリフトを予想する場合、トレーニング時にドメイン適応技法を使用して、モデルをそれらの変化に不変になるように明示的に学習します。

### 推奨されるツール
- **DeepChecks**: An open-source Python library for validating and testing ML models and data, with a strong focus on detecting data drift, corruption, and other issues - [DeepChecks on GitHub](https://github.com/deepchecks/deepchecks)
- **Evidently AI**: An open-source Python library for evaluating, testing, and monitoring ML models in production. It provides interactive reports on data drift and model performance - [Evidently AI on GitHub](https://github.com/evidentlyai/evidently)
- **Alibi Detect**: A Python library focused on outlier, adversarial, and drift detection. It provides a range of algorithms for detecting OOD data - [Alibi Detect on GitHub](https://github.com/SeldonIO/alibi-detect)


### 参考情報
- "Failing Loudly: An Empirical Study of Methods for Detecting Dataset Shift." Rabanser, Stephan, et al. NeurIPS 2019. [Link](https://arxiv.org/abs/1810.11953)
- OWASP Top 10 for LLM Applications 2025. "LLM05: Improper Output Handling." OWASP, 2025. [Link](https://genai.owasp.org/llmrisk/llm052025-improper-output-handling/)
- NIST AI 100-2e2025, "Adversarial Machine Learning: A Taxonomy and Terminology of Attacks and Mitigations," Section 4.2 "Evaluation – Robustness and Resilience to Distribution Shifts." NIST, March 2025. [Link](https://doi.org/10.6028/NIST.AI.100-2e2025)
