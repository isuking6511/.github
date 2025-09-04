# 🌐 Cloud Infrastructure for Global OliveYoung

> K-뷰티 리더 올리브영의 글로벌 서비스 확장을 위한 MSA 기반 제로 트러스트(Zero Trust) 보안 인프라 구축 프로젝트

<p align="center">
  <img src="https://img.shields.io/badge/AWS-232F3E?logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white" />
  <img src="https://img.shields.io/badge/SPIRE-A6C444?logo=spiffe&logoColor=white" />
  <img src="https://img.shields.io/badge/Falco-00A5E6?logo=falco&logoColor=white" />
  <img src="https://img.shields.io/badge/Kafka-231F20?logo=apachekafka&logoColor=white" />
  <img src="https://img.shields.io/badge/Terraform-7B42BC?logo=terraform&logoColor=white" />
</p>
<p align="center">
  <img src="https://img.shields.io/badge/Go-00ADD8?logo=go&logoColor=white" />
  <img src="https://img.shields.io/badge/Java-007396?logo=java&logoColor=white" />
  <img src="https://img.shields.io/badge/Prometheus-E6522C?logo=prometheus&logoColor=white" />
  <img src="https://img.shields.io/badge/Grafana-F46800?logo=grafana&logoColor=white" />
</p>

---

### CJ OliveNetworks Cloud Wave 6기 | 팀 `최강zl존`

| [<img src="https://github.com/DongilMin.png" width="100">](https://github.com/DongilMin) | [<img src="https://github.com/gyuseon25.png" width="100">](https://github.com/gyuseon25) | [<img src="https://github.com/isuking6511.png" width="100">](https://github.com/isuking6511) | [<img src="https://github.com/dfadsfa.png" width="100">](https://github.com/dfadsfa) | [<img src="https://github.com/sojung102.png" width="100">](https://github.com/sojung102) |
| :---: | :---: | :---: | :---: | :---: |
| **민동일** | **심규선** | **김지호** | **장욱재** | **박소정** |

<br>

## 🚀 프로젝트 목표

> 전 세계로 확장하는 올리브영의 대규모 트래픽과 고도화된 사이버 위협에 대응하고, 24/7 무중단 서비스를 제공하기 위해 **보안, 성능, 비용**을 모두 최적화한 클라우드 네이티브 인프라를 설계하고 구축합니다.

| 구분 | 목표 | 세부 구현 전략 |
| :---: | :--- | :--- |
| **🔐 보안** | **Zero Trust 기반 다층 방어** | **SPIRE(mTLS)**, **Falco**, **AWS WAF**를 통한 내/외부 위협 자동 탐지 및 실시간 대응 |
| **⚡ 성능** | **대규모 트래픽 처리 및 DR** | '올영세일' 수준(평시 10배) 트래픽 처리, **Karpenter** 및 **Kafka** 도입, 2분 내 DR 전환 |
| **💰 비용** | **FinOps 기반 비용 최적화** | **S3 Lifecycle**, **Lambda** 자동화, 태그 기반 비용 추적을 통한 유휴 리소스 및 스토리지 비용 관리 |

<br>

## 🏗️ 아키텍처

> 소스코드 보안을 위한 **On-Premise** 환경과 서비스 운영을 위한 **AWS Cloud**를 연동한 하이브리드 클라우드 환경을 채택했습니다. DR Site는 최소 지연 시간을 고려하여 도쿄 리전에 **Warm Standby** 방식으로 구축했습니다.

<p align="center">
  <img src="https://github.com/user-attachments/assets/4116044f-862b-48aa-bac7-13a4b1975c0b" width="700" />
  <br /><br />
  <img src="https://github.com/user-attachments/assets/323898de-7179-4fde-b4a0-7fde79ba35f5" width="700" />
</p>

* **On-Premise**: 격리 사설망 내 **GitLab** 서버를 구축하여 소스코드 유출을 원천 차단합니다.
* **AWS Cloud (Seoul)**: **EKS** 기반 MSA 운영 환경으로, 개발(Staging)과 운영(Production) 환경을 VPC로 완벽히 분리합니다.
* **DR Site (Tokyo)**: **Route53** 및 **RDS Aurora** 실시간 복제를 통해 2분 내 자동 전환이 가능한 재해 복구 환경을 구성합니다.

<br>

## ✨ 핵심 기능 및 구현

### 🔐 보안 (Security): "절대 신뢰하지 말고, 항상 검증하라"
* **Zero Trust 아키텍처**:
    - **SPIRE**: 플랫폼 독립적인 신원 증명을 통해 서비스 간 상호 인증(**mTLS**)을 구현합니다.
    - **초단기 인증서**: 60초 수명의 인증서를 30초마다 자동 갱신하여 인증서 탈취 시 피해를 최소화합니다.
* **다층 방어 체계**:
    - **AWS WAF**: SQL Injection, XSS 등 외부 웹 공격을 최전선에서 방어합니다.
    - **Falco**: 컨테이너 런타임 환경에서 커널 레벨의 이상 행위를 실시간으로 탐지하여 내부 위협에 대응합니다.
    - **SonarQube & 시크릿 스캐너**: CI 단계에서 코드 취약점 및 민감 정보 노출을 사전에 차단합니다.
* **자동화된 위협 대응 및 리포팅**:
    - **WAF → OpenSearch → Slack**: 외부 공격 탐지, 시각화, 알림까지의 파이프라인을 자동화했습니다.
    - **S3 → Athena → SES**: 방대한 로그를 **Athena**로 자동 분석하여 일일 보안 보고서를 이메일로 발송합니다.

### ⚡ 성능 (Performance): "빠르고, 끊김 없이"
* **지능형 오토 스케일링**:
    - **HPA & Karpenter**: **Prometheus** 메트릭 기반으로 Pod를 확장(HPA)하고, 부족한 컴퓨팅 자원을 **Karpenter**가 실시간으로 프로비저닝하여 '올영세일' 수준의 트래픽을 안정적으로 처리합니다.
* **성능 향상 기술**:
    - **Kafka**: 대규모 주문 요청을 비동기 메시지 큐 방식으로 처리하여 병목 현상을 해소합니다.
    - **VPC Endpoint**: AWS 내부 네트워크를 활용하여 서비스-DB 간 통신 지연 시간을 최소화합니다.
    - **ARM (Graviton)**: x86 아키텍처 대비 최대 40% 향상된 가성비의 ARM 프로세서를 도입하여 성능을 최적화했습니다.

### 💰 비용 (Cost): "데이터 기반의 비용 관리"
* **스토리지 최적화**:
    - **S3 Lifecycle Policy**: 데이터 접근 빈도에 따라 Standard → Standard-IA → Glacier 스토리지 클래스로 자동 이전하여 스토리지 비용을 44% 절감했습니다.
* **리소스 최적화**:
    - **Lambda & EventBridge**: 트래픽이 적은 심야 시간에 개발 환경 리소스를 자동으로 축소/종료하여 유휴 비용을 최소화합니다.
    - **태그 기반 비용 추적**: 모든 리소스에 태그를 적용하여 팀별/서비스별 비용을 추적하고 불필요 리소스를 식별 및 자동 정리합니다.

<br>

## 🛠️ 기술 스택

| 구분 | 기술 |
| :--- | :--- |
| **Cloud & Infra** | `AWS` `EC2` `EKS` `RDS Aurora` `S3` `Route53` `Lambda` `VPC` `ECS` `Fargate` |
| **Container** | `Docker` `Kubernetes` `Karpenter` `Helm` `HPA` |
| **Backend** | `Go` `Java (Spring Boot)` |
| **CI/CD & IaC** | `GitLab` `Jenkins` `ArgoCD` `Terraform` |
| **Security** | `SPIRE (mTLS)` `Falco` `SonarQube` `AWS WAF` `Secret Scanner` |
| **Monitoring** | `Prometheus` `Grafana` `OpenSearch` |
| **Message Queue** | `Kafka` |
| **Data Analysis** | `Amazon Athena` |

<br>

## 📊 핵심 성과

| 영역 | 성과 | 비고 |
| :---: | :--- | :--- |
| **보안** | SSL Labs `B` → `A` 등급 | TLS 프로토콜 및 암호화 스위트 최적화 |
| **성능** | '올영세일' 부하 테스트 통과 | **Prometheus** 및 **Grafana**로 안정적인 처리 성능 입증 |
| **DR** | 전환 시간 **2분 이내** 달성 | 목표 시간(5분) 대비 60% 단축 |
| **비용** | 스토리지 비용 **44% 절감** | S3 Lifecycle 적용, 실제 환경에서 54%까지 기대 |

<br>

## 📂 레포지토리

* **MSA (Go)**
    * `product-service`: 상품 관리 서비스 (Go 리팩토링)
    * `order-service`: 주문 관리 서비스 (Go 리팩토링)
* **MSA (Java)**
    * `user-service`: 사용자 인증/인가 서비스 (Spring Boot)
* **Infrastructure**
    - `eks-cluster`: EKS 클러스터 설정 및 운영 (ArgoCD 연동)
    - `aws-infra-terraform`: Terraform 기반 AWS 인프라 코드 (IaC)
