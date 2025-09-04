<div align="center">

# 🌐 Cloud Infrastructure for Global OliveYoung

> K-뷰티 리더 올리브영의 글로벌 확장을 위한 MSA 기반 제로 트러스트(Zero Trust) 보안 인프라

<p>
  <img src="https://img.shields.io/badge/AWS-232F3E?logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white" />
  <img src="https://img.shields.io/badge/Terraform-7B42BC?logo=terraform&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/Helm-0F1689?logo=helm&logoColor=white" />
</p>
<p>
  <img src="https://img.shields.io/badge/Go-00ADD8?logo=go&logoColor=white" />
  <img src="https://img.shields.io/badge/Java-007396?logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/Spring-6DB33F?logo=spring&logoColor=white" />
  <img src="https://img.shields.io/badge/Apache%20Kafka-231F20?logo=apachekafka&logoColor=white" />
  <img src="https://img.shields.io/badge/Amazon%20DynamoDB-4053D6?logo=amazondynamodb&logoColor=white" />
</p>
<p>
  <img src="https://img.shields.io/badge/GitLab-FC6D26?logo=gitlab&logoColor=white" />
  <img src="https://img.shields.io/badge/Jenkins-D24939?logo=jenkins&logoColor=white" />
  <img src="https://img.shields.io/badge/ArgoCD-EF7B4D?logo=argocd&logoColor=white" />
  <img src="https://img.shields.io/badge/Amazon%20ECR-FF9900?logo=amazonelasticcontainerregistry&logoColor=white" />
</p>
<p>
  <img src="https://img.shields.io/badge/SPIRE-A6C444?logo=spiffe&logoColor=white" />
  <img src="https://img.shields.io/badge/Falco-00A5E6?logo=falco&logoColor=white" />
  <img src="https://img.shields.io/badge/SonarQube-4E9BCD?logo=sonarqube&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS%20WAF-FF9900?logo=awswaf&logoColor=white" />
  <img src="https://img.shields.io/badge/NIST-000000?logo=nist&logoColor=white" />
</p>
<p>
  <img src="https://img.shields.io/badge/Prometheus-E6522C?logo=prometheus&logoColor=white" />
  <img src="https://img.shields.io/badge/Grafana-F46800?logo=grafana&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenSearch-005EB8?logo=opensearch&logoColor=white" />
  <img src="https://img.shields.io/badge/Amazon%20Athena-7D4099?logo=amazonathena&logoColor=white" />
</p>

<hr>

<h3 align="center">CJ OliveNetworks Cloud Wave 6기 | 팀 `최강zl존`</h3>

| [<img src="https://github.com/DongilMin.png" width="100">](https://github.com/DongilMin) | [<img src="https://github.com/gyuseon25.png" width="100">](https://github.com/gyuseon25) | [<img src="https://github.com/isuking6511.png" width="100">](https://github.com/isuking6511) | [<img src="https://github.com/dfadsfa.png" width="100">](https://github.com/dfadsfa) | [<img src="https://github.com/sojung102.png" width="100">](https://github.com/sojung102) |
| :---: | :---: | :---: | :---: | :---: |
| **민동일** | **심규선** | **김지호** | **장욱재** | **박소정** |

<br>

<h2 align="center">🚀 프로젝트 목표</h2>

| 구분 | 목표 |
| :---: | :--- |
| **🔐 보안** | **Zero Trust 기반 다층 방어**: 내/외부 위협 실시간 탐지 및 100% 자동화 대응 |
| **⚡ 성능** | **대규모 트래픽 처리 및 무중단 DR**: '올영세일' 수준 트래픽 처리, 2분 내 재해 복구 |
| **💰 비용** | **FinOps 기반 비용 최적화**: 유휴 리소스 및 스토리지 비용 자동 관리 및 추적 |

<br>

<h2 align="center">🏗️ 아키텍처</h2>

> 💡 **아래 제목을 클릭하면 상세 아키텍처 다이어그램이 펼쳐집니다.**

<br>

<details>
<summary><strong>[Architecture Diagram] 📍 AWS Seoul Region (Production / Staging)</strong></summary>
<br>
<table border="0">
 <tr>
  <td align="center"><img src="https://github.com/user-attachments/assets/4116044f-862b-48aa-bac7-13a4b1975c0b" width="100%" /></td>
  <td align="center"><img src="https://github.com/user-attachments/assets/18b6b3bf-4d14-400b-80cc-8e5352d1e712" width="100%" /></td>
 </tr>
</table>
</details>

<br>

<details>
<summary><strong>[Architecture Diagram] 🇯🇵 AWS Tokyo Region (DR Site)</strong></summary>
<br>
<p align="center">
  <img src="https://github.com/user-attachments/assets/323898de-7179-4fde-b4a0-7fde79ba35f5" width="800" />
</p>
</details>

<table border="0"><tr><td align="left">
<ul>
<li><strong>Hybrid Cloud</strong>: <code>On-Premise</code> (GitLab) + <code>AWS Cloud</code> (EKS) 연동</li>
<li><strong>Multi-AZ</strong>: <code>운영계(Seoul)</code> 다중 AZ 구성으로 고가용성 확보</li>
<li><strong>Disaster Recovery</strong>: <code>DR Site(Tokyo)</code> Warm Standby 구성 (2분 내 자동 전환)</li>
</ul>
</td></tr></table>

<br>

<h2 align="center">✨ 핵심 기능</h2>

<h3 align="center">🔐 보안 (Security)</h3>

> 💡 **아래 3개의 주제를 클릭하면 상세 구현 내용과 증명 자료(이미지)가 펼쳐집니다.**

<br>

<details>
<summary><strong>[구현 상세] 1. 원칙: "절대 신뢰하지 말고, 항상 검증하라"</strong></summary>
<br>
    
* **서비스 간 상호 인증**: MSA 환경 내 모든 서비스 통신에 **mTLS** 상호 인증 적용
    <p align="center">
      <img width="650" height="300" alt="TLS vs mTLS Communication" src="https://github.com/user-attachments/assets/cef71004-f042-469f-8170-5d9a2d2fbbb8" />
    </p>

* **mTLS 자동화**: 수동 관리의 한계 → **SPIRE** 도입으로 **워크로드 증명(Attestation)** 기반 인증서 발급/갱신 **100% 자동화**
    <p align="center">
      <img width="650" height="400" alt="SPIRE Architecture" src="https://github.com/user-attachments/assets/9066d6a4-4674-4074-a3d4-7337d745c2c0" />
    </p>

* **인증서 탈취 대응**: **60초 수명**의 초단기 인증서(SVID)를 **30초** 주기로 자동 갱신하여 탈취 피해 최소화
    <p align="center">
      <img width="650" height="300" alt="Short-Lived SVID Renewal Proof" src="https://github.com/user-attachments/assets/e127d6e8-d7ae-444a-9cc5-bae5b10797fe" />
    </p>
</details>

<details>
<summary><strong>[구현 상세] 2. 자동화된 외부 위협 대응</strong></summary>
<br>

* **테스트 시나리오**: 대규모 **Credential Stuffing** 공격 및 개인정보 유출 상황 모의
    <p align="center">
      <img width="650" height="300" alt="Simulated Data Breach Scenario" src="https://github.com/user-attachments/assets/a8d7f2c6-47a4-45dd-8f6a-0ec858e66e51" />
    </p>

* **대응 파이프라인**: **탐지 → 차단 → 시각화 → 알림 → 분석 → 리포팅** 전 과정 100% 자동화
    <p align="center">
      <img width="650" height="300" alt="Automated Threat Response Pipeline" src="https://github.com/user-attachments/assets/b21fe029-d27e-47c5-a3ed-87f287392acf" />
    </p>

* **실시간 대응**: **WAF** 자동 차단 → **OpenSearch** 실시간 시각화 → **Slack** 즉각 알림
    <p align="center">
      <img width="650" height="300" alt="Real-time Detection & Alerting Demo" src="https://github.com/user-attachments/assets/32254136-5039-4a6f-819c-e56f287a5e64" />
    </p>

* **분석 및 리포팅**: **WAF Log (S3)** → **Athena** 자동 쿼리 → **SES** 일일 보고서 발송
    <p align="center">
      <img width="650" height="300" alt="Automated Log Analysis & Reporting" src="https://github.com/user-attachments/assets/b6717032-9c6d-4d8d-8d33-fa9f08b03cbe" />
    </p>
</details>

<details>
<summary><strong>[구현 상세] 3. CI/CD 파이프라인 보안 (DevSecOps)</strong></summary>
<br>

* **정적 코드 분석**: `SonarQube`를 통한 소스 코드 레벨의 잠재적 보안 취약점 사전 탐지
    <p align="center">
      <img width="650" height="300" alt="SonarQube SAST" src="https://github.com/user-attachments/assets/75a51d55-d680-4b82-b2bb-e7f67bd3bd56" />
    </p>

* **민감 정보 스캐닝**: `Git` 커밋 내 민감 정보(API 키 등) 실시간 탐지, 자동 비활성화 및 경고
    <p align="center">
      <img width="650" height="300" alt="Secret Scanning & Alerting" src="https://github.com/user-attachments/assets/06b46a5b-798d-4369-b2be-7ee69d49fe3d" />
    </p>
</details>

<hr>

<h3 align="center">⚡ 성능 (Performance)</h3>

<table border="0"><tr><td align="left">
<ul>
<li><strong>유연한 리소스 확장</strong>: <code>Prometheus</code> → <code>HPA</code> → <code>Karpenter</code> 연동으로 트래픽에 따른 동적 오토스케일링</li>
<li><strong>안정적인 요청 처리</strong>: <code>Kafka</code> 메시지 큐를 통한 비동기 처리로 대규모 트래픽 병목 현상 해소</li>
<li><strong>응답 속도 향상</strong>: <code>VPC Endpoint</code>를 통한 AWS 내부망 통신으로 네트워크 지연 최소화</li>
<li><strong>비용 대비 성능 극대화</strong>: <code>AWS Graviton</code>(ARM) 프로세서 도입으로 컴퓨팅 효율 최적화</li>
</ul>
</td></tr></table>

<hr>

<h2 align="center">🔬 성능 검증: '올영세일' 시나리오 스트레스 테스트</h2>

> 💡 **아래 제목을 클릭하면 상세 테스트 과정 및 결과가 펼쳐집니다.**

<br>

<details>
<summary><strong>[Test Details] 시나리오 정의, 실시간 스케일링, 테스트 결과</strong></summary>
<br>

* **시나리오 정의**:
    * **기준**: 올리브영 공식 트래픽 5단계 모델 기반
    * **목표**: 최고 부하 단계인 **'(S) Special - 올영세일'** (평시 20배 이상) 트래픽을 안정적으로 처리

    <p align="center">
      <img width="650" height="300" alt="Traffic Level Scenario" src="https://github.com/user-attachments/assets/3cf9d698-9d68-42bf-9ef7-fcc1b7d77565" />
    </p>

* **실시간 스케일링 동작**:
    * **Pod 확장 (HPA)**: `Prometheus`로 수집된 CPU/Memory 임계값 초과 시 HPA가 Pod 수를 **4개에서 13개로 확장**
    * **Node 프로비저닝 (Karpenter)**: HPA에 의해 스케줄링 불가능한 Pod 발생 시 `Karpenter`가 신규 Node(7개→10개)를 **Just-in-Time 방식으로 즉시 프로비저닝**

    <p align="center">
      <img width="650" height="300" alt="Real-time Scaling Visualization" src="https://github.com/user-attachments/assets/be64eb3d-67c9-4313-a2b5-355df6f53814" />
    </p>

* **테스트 결과 (Grafana 대시보드)**:
    * **결과**: 트래픽 폭증에 성공적으로 대응 후, 트래픽 감소 시 Pod와 Node가 설정된 기준에 따라 안정적으로 축소됨을 확인
    * **Pod 수**: **4 → 13 → 4** (안정적 복귀)
    * **Node 수**: **7 → 10 → 8** (비용 최적화를 위한 점진적 축소)

    <p align="center">
      <img width="650" height="300" alt="Grafana Dashboard Results" src="https://github.com/user-attachments/assets/6dd70aae-8b88-481e-9981-8c9bf5053d62" />
    </p>
</details>

<hr>

<h3 align="center">💰 비용 (Cost)</h3>

<table border="0"><tr><td align="left">
<ul>
<li><strong>체계적인 비용 관리</strong>: 전 리소스 <strong>태깅(Tagging)</strong>을 통한 팀/서비스 단위 비용 추적 및 분석 (FinOps)</li>
<li><strong>스토리지 비용 절감</strong>: <strong>S3 Lifecycle Policy</strong> (<code>Standard → IA → Glacier</code>) 자동 이전 (44% 절감)</li>
<li><strong>유휴 리소스 관리</strong>: <strong>Lambda + EventBridge</strong>로 심야 시간 개발 환경 리소스 자동 축소/종료</li>
<li><strong>예산 초과 방지</strong>: <strong>AWS Budget</strong> 설정으로 지정된 비용 임계값 초과 시 자동 알림 발송</li>
</ul>
</td></tr></table>
<br>

<h2 align="center">🛠️ 기술 스택</h2>

| 구분 | 기술 |
| :--- | :--- |
| **Cloud & Infra** | `AWS` `EC2` `EKS` `RDS Aurora` `S3` `Route53` `Lambda` `VPC` `ECS` `Fargate` `EventBridge` |
| **Container** | `Docker` `Kubernetes` `Karpenter` `Helm` `HPA` |
| **Backend** | `Go` `Java (Spring Boot)` `DynamoDB`|
| **CI/CD & IaC** | `GitLab` `Jenkins` `ArgoCD` `Terraform` `Amazon ECR` |
| **Security** | `SPIRE (mTLS)` `Falco` `SonarQube` `AWS WAF` `Secret Scanner` `NIST ZTA` |
| **Monitoring** | `Prometheus` `Grafana` `OpenSearch` `Slack` |
| **Message Queue** | `Kafka` |
| **Data Analysis** | `Amazon Athena` `Amazon SES`|

<br>

<h2 align="center">📊 핵심 성과</h2>

| 영역 | 성과 |
| :---: | :--- |
| **보안** | SSL Labs `B` → `A` 등급 달성 |
| **성능** | '올영세일' 부하 테스트 통과 (무중단 트래픽 처리) |
| **DR** | 재해 복구 전환 **2분 이내** 달성 (목표 60% 단축) |
| **비용** | 스토리지 비용 **44% 절감** (실제 환경 54% 기대) |

<br>

<h2 align="center">📂 레포지토리</h2>

<table border="0"><tr><td align="left">
<ul>
<li><strong>MSA (Go)</strong>: <code>product-service</code>, <code>order-service</code></li>
<li><strong>MSA (Java)</strong>: <code>user-service</code></li>
<li><strong>Infrastructure</strong>: <code>eks-cluster</code>, <code>aws-infra-terraform</code></li>
</ul>
</td></tr></table>

</div>
