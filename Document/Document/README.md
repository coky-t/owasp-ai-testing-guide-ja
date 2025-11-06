

# OWASP AI テストガイド目次

## 1. [はじめに](content/1.0_Introduction.md)

- 1.1 [序文と貢献者 (Preface and Contributors)](content/1.1_Preface_and_Contributors.md)

- 1.2 [AI テストの原則 (Principles of AI Testing)](content/1.2_Principles_of_AI_Testing.md)

- 1.3 [OWASP AI テストガイドの目的 (Objectives of OWASP AI Testing Guide)](content/1.3_Objectives_of_AI_Testing_Guide.md)

## 2. [AI システムの脅威モデリング (Threat Modeling AI Systems)](content/2.0_Threat_Modeling_for_AI_Systems.md)

- 2.1 [AI システム脅威を特定する (Identify AI System Threats)](content/2.1_Identify_AI_Threats.md)

- 2.1.1 [OWASP AI 脅威を AI アーキテクチャコンポーネントにマップする (Map OWASP AI Threats To AI Architectural Components)](content/2.1.1_Architectural_Mapping_of_OWASP_Threats.md)

- 2.1.2 [AI システム 責任ある AI (RAI)/信頼できる AI の脅威を特定する (Identify AI System Responsible AI (RAI)/Trustworthy AI Threats)](content/2.1.2_Identify_RAI_threats.md)

- 2.2 [付録 A: SAIF (Secure AI Framework) を使用する理由 (Appendix A: Rationale For Using SAIF (Secure AI Framework))](content/2.2_Appendix_A.md)

- 2.2 [付録 B: 分散型、不変的、一時的 (DIE) 脅威の特定 (Appendix B: Distributed, Immutable, Ephemeral (DIE) Threat Identification)](content/2.2_Appendix_B.md)

- 2.2 [付録 C: 安全な AI システムのためのリスクライフサイクル (Appendix C: Risk Lifecycle for Secure AI Systems)](content/2.2_Appendix_C.md)

- 2.2 [付録 D: AI アーキテクチャコンポーネントへの脅威の列挙 (Appendix D: Threat Enumeration to AI Architecture Components)](content/2.2_Appendix_D.md)

- 2.2 [付録 E: AI システムの脆弱性 (CVE および CWE) に対する AI 脅威のマッピング (Appendix E: Mapping AI Threats Against AI Systems Vulnerabilities (CVEs & CWEs))](content/2.2_Appendix_E.md)

## 3. [OWASP AI テストガイドフレームワーク (OWASP AI Testing Guide Framework)](content/3.0_OWASP_AI_Testing_Guide_Framework.md)

- 3.1 🟦 [AI アプリケーションテスト (AI Application Testing)](content/3.1_AI_Application_Testing.md)

| テスト ID     | テスト名とリンク |
|---------------|------------------|
| AITG-APP-01   | [プロンプトインジェクションのテスト (Testing for Prompt Injection)](content/tests/AITG-APP-01_Testing_for_Prompt_Injection.md) |
| AITG-APP-02   | [間接プロンプトインジェクションのテスト (Testing for Indirect Prompt Injection)](content/tests/AITG-APP-02_Testing_for_Indirect_Prompt_Injection.md) |
| AITG-APP-03   | [機密データ漏洩のテスト (Testing for Sensitive Data Leak)](content/tests/AITG-APP-03_Testing_for_Sensitive_Data_Leak.md) |
| AITG-APP-04   | [入力漏洩のテスト (Testing for Input Leakage)](content/tests/AITG-APP-04_Testing_for_Input_Leakage.md) |
| AITG-APP-05   | [安全でない出力のテスト (Testing for Unsafe Outputs)](content/tests/AITG-APP-05_Testing_for_Unsafe_Outputs.md) |
| AITG-APP-06   | [エージェント動作限界のテスト (Testing for Agentic Behavior Limits)](content/tests/AITG-APP-06_Testing_for_Agentic_Behavior_Limits.md) |
| AITG-APP-07   | [プロンプト開示のテスト (Testing for Prompt Disclosure)](content/tests/AITG-APP-07_Testing_for_Prompt_Disclosure.md) |
| AITG-APP-08   | [エンベディング操作のテスト (Testing for Embedding Manipulation)](content/tests/AITG-APP-08_Testing_for_Embedding_Manipulation.md) |
| AITG-APP-09   | [モデル抽出のテスト (Testing for Model Extraction)](content/tests/AITG-APP-09_Testing_for_Model_Extraction.md) |
| AITG-APP-10   | [コンテンツバイアスのテスト (Testing for Content Bias)](content/tests/AITG-APP-10_Testing_for_Content_Bias.md) |
| AITG-APP-11   | [ハルシネーションのテスト (Testing for Hallucinations)](content/tests/AITG-APP-11_Testing_for_Hallucinations.md) |
| AITG-APP-12   | [有害な出力のテスト (Testing for Toxic Output)](content/tests/AITG-APP-12_Testing_for_Toxic_Output.md) |
| AITG-APP-13   | [AI への過度な依存のテスト (Testing for Over-Reliance on AI)](content/tests/AITG-APP-13_Testing_for_Over-Reliance_on_AI.md) |
| AITG-APP-14   | [説明可能性と解釈可能性のテスト (Testing for Explainability and Interpretability)](content/tests/AITG-APP-14_Testing_for_Explainability_and_Interpretability.md) |


- 3.2 🟪 [AI モデルテスト (AI Model Testing)](content/3.2_AI_Model_Testing.md)

| テスト ID     | テスト名とリンク |
|---------------|------------------|
| AITG-MOD-01   | [回避攻撃のテスト (Testing for Evasion Attacks)](content/tests/AITG-MOD-01_Testing_for_Evasion_Attacks.md) |
| AITG-MOD-02   | [ランタイムモデルポイズニングのテスト (Testing for Runtime Model Poisoning)](content/tests/AITG-MOD-02_Testing_for_Runtime_Model_Poisoning.md) |
| AITG-MOD-03   | [汚染されたトレーニングセットのテスト (Testing for Poisoned Training Sets)](content/tests/AITG-MOD-03_Testing_for_Poisoned_Training_Sets.md) |
| AITG-MOD-04   | [メンバーシップ推論のテスト (Testing for Membership Inference)](content/tests/AITG-MOD-04_Testing_for_Membership_Inference.md) |
| AITG-MOD-05   | [反転攻撃のテスト (Testing for Inversion Attacks)](content/tests/AITG-MOD-05_Testing_for_Inversion_Attacks.md) |
| AITG-MOD-06   | [新しいデータに対する頑健性のテスト (Testing for Robustness to New Data)](content/tests/AITG-MOD-06_Testing_for_Robustness_to_New_Data.md) |
| AITG-MOD-07   | [目標との整合のテスト (Testing for Goal Alignment)](content/tests/AITG-MOD-07_Testing_for_Goal_Alignment.md) |

---

- 3.3 🟩 [AI インフラストラクチャテスト (AI Infrastructure Testing)](content/3.3_AI_Infrastructure_Testing.md)

| テスト ID     | テスト名とリンク |
|---------------|------------------|
| AITG-INF-01   | [サプライチェーン改竄のテスト (Testing for Supply Chain Tampering)](content/tests/AITG-INF-01_Testing_for_Supply_Chain_Tampering.md) |
| AITG-INF-02   | [リソース枯渇のテスト (Testing for Resource Exhaustion)](content/tests/AITG-INF-02_Testing_for_Resource_Exhaustion.md) |
| AITG-INF-03   | [プラグイン境界違反のテスト (Testing for Plugin Boundary Violations)](content/tests/AITG-INF-03_Testing_for_Plugin_Boundary_Violations.md) |
| AITG-INF-04   | [ケイパビリティ不正使用のテスト (Testing for Capability Misuse)](content/tests/AITG-INF-04_Testing_for_Capability_Misuse.md) |
| AITG-INF-05   | [ファインチューニングポイズニングのテスト (Testing for Fine-tuning Poisoning)](content/tests/AITG-INF-05_Testing_for_Fine-tuning_Poisoning.md) |
| AITG-INF-06   | [開発時のモデル盗用のテスト (Testing for Dev-Time Model Theft)](content/tests/AITG-INF-06_Testing_for_Dev-Time_Model_Theft.md) |

---

- 3.4 🟨 [AIデータテスト (AI Data Testing)](content/3.4_AI_Data_Testing.md)

| テスト ID     | テスト名とリンク |
|---------------|------------------|
| AITG-DAT-01   | [トレーニングデータ露出のテスト (Testing for Training Data Exposure)](content/tests/AITG-DAT-01_Testing_for_Training_Data_Exposure.md) |
| AITG-DAT-02   | [ランタイム流出のテスト (Testing for Runtime Exfiltration)](content/tests/AITG-DAT-02_Testing_for_Runtime_Exfiltration.md) |
| AITG-DAT-03   | [データセットの多様性とカバレッジのテスト (Testing for Dataset Diversity & Coverage)](content/tests/AITG-DAT-03_Testing_for_Dataset_Diversity_and_Coverage.md) |
| AITG-DAT-04   | [データ内の有害なコンテンツのテスト (Testing for Harmful Content in Data)](content/tests/AITG-DAT-04_Testing_for_Harmful_Content_in_Data.md) |
| AITG-DAT-05   | [データ最小化と同意のテスト (Testing for Data Minimization & Consent)](content/tests/AITG-DAT-05_Testing_for_Data_Minimization_and_Consent.md) |



## 4. [ドメイン固有テスト (Domain Specific Testing)](content/4.0_Domain_Specific_Testing.md)

 [参考情報](content/References.md)
