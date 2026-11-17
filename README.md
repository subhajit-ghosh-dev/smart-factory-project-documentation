\# Cyber-Resilient Digital Twin of a Smart Factory with AI/ML Intrusion Detection



\## 1. Project Overview



This project presents a software-based Cyber-Resilient Digital Twin of a Smart Factory integrated with an AI/ML-based Intrusion Detection System (IDS).



The system simulates factory operations and monitors operational telemetry, machine conditions, security events, and potential cyberattacks.



The implementation consists of five major components:



1\. Smart Factory Digital Twin

2\. Rule-Based Security Gateway

3\. AI/ML Intrusion Detection System

4\. FastAPI Backend

5\. Streamlit Monitoring Dashboard



The Digital Twin generates simulated factory telemetry. The backend receives telemetry and security events. The Security Gateway validates incoming factory commands, while the ML IDS independently monitors activity and predicts potentially malicious behavior.



This is an academic software simulation. It does not require physical industrial equipment.



\## 2. Project Objectives



\- Develop a software-based Smart Factory Digital Twin.

\- Simulate factory operations, sensors, conveyor movement, and machine conditions.

\- Implement a rule-based Security Gateway for command validation.

\- Detect unauthorized and suspicious command activity.

\- Integrate a machine-learning-based Intrusion Detection System.

\- Monitor factory telemetry and cybersecurity events.

\- Record security events and ML predictions.

\- Provide a dashboard for operational and security monitoring.

\- Evaluate the implementation using automated tests and attack scenarios.



\## 3. Main Features



\### Smart Factory Digital Twin

\- Factory operation simulation.

\- Conveyor state and speed monitoring.

\- Sensor telemetry generation.

\- Temperature monitoring.

\- Item presence and processing simulation.

\- Machine fault detection and handling.



\### Rule-Based Security Gateway

\- Command authorization checks.

\- Unauthorized command rejection.

\- Replay attack prevention.

\- Command rate limiting.

\- Conveyor speed range validation.

\- Machine fault protection.



\### Machine Learning IDS

\- Trained Random Forest classification model.

\- Normal and attack prediction.

\- Attack probability estimation.

\- ML prediction event logging.

\- Monitoring-only operation.



\### Backend and Dashboard

\- FastAPI REST API.

\- Factory telemetry collection.

\- Security event collection.

\- Streamlit monitoring dashboard.

\- Factory status monitoring.

\- Security event history.

\- ML prediction monitoring.



\## 4. System Architecture



```text

&#x20;            SMART FACTORY DIGITAL TWIN

&#x20;                        |

&#x20;                 Sensor Simulation

&#x20;                 Factory Controller

&#x20;                 Factory Simulation

&#x20;                        |

&#x20;                     Telemetry

&#x20;                        |

&#x20;                 FASTAPI BACKEND

&#x20;                        |

&#x20;             +----------+----------+

&#x20;             |                     |

&#x20;             v                     v

&#x20;      SECURITY GATEWAY          ML IDS ENGINE

&#x20;      Rule-based checks         Trained ML model

&#x20;             |                     |

&#x20;             v                     v

&#x20;      Command Decision         ML Prediction

&#x20;      ACCEPT / REJECT          NORMAL / ATTACK

&#x20;             |                     |

&#x20;             +----------+----------+

&#x20;                        |

&#x20;               SECURITY EVENT LOGS

&#x20;                        |

&#x20;               STREAMLIT DASHBOARD

&#x20;                        |

&#x20;             Factory and Security

&#x20;                   Monitoring

```



\### Important Architectural Principle



The Security Gateway and ML IDS have separate responsibilities.



\*\*Security Gateway\*\*

\- Checks command authorization.

\- Applies security rules.

\- Accepts or rejects factory commands.

\- Enforces machine fault protection.



\*\*ML Intrusion Detection System\*\*

\- Analyses factory activity.

\- Predicts normal or suspicious behavior.

\- Estimates attack probability.

\- Records intrusion detection results.



The ML model operates in monitoring-only mode. It does not independently authorize or reject factory commands.



\## 5. Technology Stack



| Component | Technology |

|---|---|

| Programming Language | Python 3.12 |

| Backend Framework | FastAPI |

| API Server | Uvicorn |

| Dashboard | Streamlit |

| Data Processing | Pandas |

| Numerical Processing | NumPy |

| Machine Learning | Scikit-learn |

| Model Loading | Joblib |

| Communication | REST API |

| Event Logging | JSONL |

| Automated Testing | Python unittest |

| Version Control | Git and GitHub |



\## 6. Security Gateway Capabilities



The Security Gateway provides command-level protection for the simulated factory.



Its security checks include:



\- \*\*Authorization validation:\*\* Rejects commands that do not satisfy authorization requirements.

\- \*\*Replay attack prevention:\*\* Detects previously processed command identifiers and rejects replayed commands.

\- \*\*Rate limiting:\*\* Restricts excessive command requests.

\- \*\*Command range validation:\*\* Rejects conveyor speed values outside the permitted range.

\- \*\*Machine fault protection:\*\* Prevents unsafe machine operation while a machine fault is active.



The Security Gateway is responsible for command enforcement.



\## 7. AI/ML Intrusion Detection



The project uses a Random Forest classification model to identify suspicious factory activity.



The model uses eight operational features:



\- Tick

\- Conveyor speed

\- Conveyor state

\- Temperature

\- Item presence

\- Machine fault

\- Command

\- Authorization status



The IDS produces a prediction label and, when supported, an attack probability estimate.



Possible prediction outcomes include:



\- NORMAL

\- ATTACK DETECTED



The IDS operates independently of the Security Gateway. Its predictions support monitoring and security analysis rather than direct command enforcement.



\## 8. Research and Experimental Evaluation



The research uses a synthetic Smart Factory IDS dataset. It must not be interpreted as a publicly sourced industrial dataset.



The validation work includes duplicate-record analysis, stratified cross-validation, grouped cross-validation, model evaluation, and gateway integration tests.



\### Holdout Evaluation



The documented evaluation report records the following baseline results:



| Metric | Result |

|---|---:|

| Accuracy | 85.37% |

| Precision | 92.31% |

| Recall | 85.71% |

| F1-score | 88.89% |



These results are specific to the documented synthetic dataset and evaluation split. They do not establish real-world industrial detection performance.



\### Cross-Validation Results



The validation report records the following five-fold results:



| Metric | Stratified CV Mean | Grouped CV Mean |

|---|---:|---:|

| Accuracy | 82.37% | 85.76% |

| Precision | 87.93% | 93.47% |

| Recall | 86.24% | 84.38% |

| F1-score | 86.83% | 88.43% |



Grouped validation keeps identical feature rows in the same fold.



\### Gateway Integration Tests



The documented integration report covers five scenarios:



\- Normal authorized command.

\- Unauthorized command.

\- Replay attack.

\- Command flooding.

\- Setpoint manipulation.



The report records four gateway rejections and five completed ML inferences.



The replay scenario demonstrates that the first command was accepted and the repeated command was rejected.



\## 9. Automated Testing



The assembled application package was tested using Python 3.12.10.



The recorded final package verification result was:



```text

Ran 14 tests in 7.529s



OK

```



All 14 tests passed during final package assembly verification.



| Test Module | Test Count |

|---|---:|

| Factory tests | 4 |

| Security tests | 6 |

| Dataset generator tests | 4 |

| \*\*Total\*\* | \*\*14\*\* |



The test groups cover factory initialization, telemetry, item processing, conveyor operation, command authorization, replay rejection, rate limiting, invalid speed rejection, and machine fault protection.



\## 10. Public Repository Contents



This repository is intended for public project documentation and approved research reports.



```text

SmartFactory\_Public\_Documentation/

|

+-- README.md

|

+-- reports/

&#x20;   +-- attack\_scenario\_results.json

&#x20;   +-- gateway\_ids\_integration.json

&#x20;   +-- gateway\_test\_results.json

&#x20;   +-- ids\_evaluation.json

&#x20;   +-- ids\_experiment\_comparison.csv

&#x20;   +-- ids\_validation\_report.json

```



The application source code, datasets, trained model files, and runtime logs are maintained separately and are not included in this public documentation repository.



\## 11. Dataset and Research Limitations



The IDS dataset contains synthetic project data.



Important limitations:



\- Synthetic data does not establish real-world industrial detection performance.

\- Model performance may differ on real industrial telemetry.

\- Synthetic feature combinations may not represent every real factory operating condition.

\- The current ML feature set does not include every possible temporal or frequency-based attack indicator.

\- Gateway decisions and ML predictions may differ because they perform different functions.

\- Conflicting labels for identical feature rows may limit reliable classification.

\- Further validation with real industrial data is required before deployment in a physical industrial environment.



The published research reports should be consulted when interpreting the evaluation results.



\## 12. Future Scope



Possible future improvements include:



\- Integration with physical IoT devices.

\- Industrial protocol integration.

\- Real-time alert notifications.

\- Database-based event storage.

\- Cloud deployment.

\- Docker containerization.

\- CI/CD automation.

\- Authentication improvements.

\- Additional historical and frequency-based ML features.

\- Validation using real industrial datasets.

\- Improved anomaly detection and model retraining.



These are future improvements and are not claimed as completed features.



\## 13. Academic Project Information



\*\*Project Title:\*\*  

Cyber-Resilient Digital Twin of a Smart Factory with AI/ML Intrusion Detection



\*\*Project Domain:\*\*

\- Digital Twin Technology

\- Smart Manufacturing

\- Industrial Cybersecurity

\- Machine Learning

\- Intrusion Detection

\- Software Simulation

\- REST API Development

\- Real-Time Monitoring



This project demonstrates the integration of factory simulation, rule-based cybersecurity, machine-learning-based intrusion detection, backend communication, and dashboard monitoring in a unified software environment.



\## 14. Project Status



| Module | Status |

|---|---|

| Smart Factory Digital Twin | Implemented |

| Factory and Sensor Simulation | Implemented |

| Security Gateway | Implemented |

| Command Authorization | Implemented |

| Replay Protection | Implemented |

| Command Rate Limiting | Implemented |

| Machine Fault Protection | Implemented |

| FastAPI Backend | Implemented |

| Telemetry Integration | Implemented |

| Security Event Logging | Implemented |

| ML Intrusion Detection | Integrated |

| ML Prediction Logging | Implemented |

| Streamlit Dashboard | Implemented |

| Research Reports | Published in this repository |

| Automated Test Suite | 14/14 Passed |

| Cloud Deployment | Future Scope |

| Physical IoT Integration | Future Scope |

| CI/CD Pipeline | Future Scope |



\---



\*\*End of Project Documentation\*\*

