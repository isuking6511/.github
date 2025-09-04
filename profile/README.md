# 🌐 Cloud Infrastructure for Global OliveYoung

> K-뷰티 리더 올리브영의 글로벌 확장을 위한 MSA 기반 제로 트러스트(Zero Trust) 보안 인프라

<p align="center">
  <img src="https://img.shields.io/badge/AWS-232F3E?logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white" />
  <img src="https://img.shields.io/badge/Terraform-7B42BC?logo=terraform&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/Helm-0F1689?logo=helm&logoColor=white" />
</p>
<p align="center">
  <img src="https://img.shields.io/badge/Go-00ADD8?logo=go&logoColor=white" />
  <img src="https://img.shields.io/badge/Java-007396?logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/Spring-6DB33F?logo=spring&logoColor=white" />
  <img src="https://img.shields.io/badge/Apache%20Kafka-231F20?logo=apachekafka&logoColor=white" />
  <img src="https://img.shields.io/badge/Amazon%20DynamoDB-4053D6?logo=amazondynamodb&logoColor=white" />
</p>
<p align="center">
  <img src="https://img.shields.io/badge/GitLab-FC6D26?logo=gitlab&logoColor=white" />
  <img src="https://img.shields.io/badge/Jenkins-D24939?logo=jenkins&logoColor=white" />
  <img src="https://img.shields.io/badge/ArgoCD-EF7B4D?logo=argocd&logoColor=white" />
  <img src="https://img.shields.io/badge/Amazon%20ECR-FF9900?logo=amazonelasticcontainerregistry&logoColor=white" />
</p>
<p align="center">
  <img src="https://img.shields.io/badge/SPIRE-A6C444?logo=spiffe&logoColor=white" />
  <img src="https://img.shields.io/badge/Falco-00A5E6?logo=falco&logoColor=white" />
  <img src="https://img.shields.io/badge/SonarQube-4E9BCD?logo=sonarqube&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS%20WAF-FF9900?logo=awswaf&logoColor=white" />
  <img src="https://img.shields.io/badge/NIST-000000?logo=nist&logoColor=white" />
</p>
<p align="center">
  <img src="https://img.shields.io/badge/Prometheus-E6522C?logo=prometheus&logoColor=white" />
  <img src="https://img.shields.io/badge/Grafana-F46800?logo=grafana&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenSearch-005EB8?logo=opensearch&logoColor=white" />
  <img src="https://img.shields.io/badge/Amazon%20Athena-7D4099?logo=amazonathena&logoColor=white" />
</p>

---

### CJ OliveNetworks Cloud Wave 6기 | 팀 `최강zl존`

| [<img src="https://github.com/DongilMin.png" width="100">](https://github.com/DongilMin) | [<img src="https://github.com/gyuseon25.png" width="100">](https://github.com/gyuseon25) | [<img src="https://github.com/isuking6511.png" width="100">](https://github.com/isuking6511) | [<img src="https://github.com/dfadsfa.png" width="100">](https://github.com/dfadsfa) | [<img src="https://github.com/sojung102.png" width="100">](https://github.com/sojung102) |
| :---: | :---: | :---: | :---: | :---: |
| **민동일** | **심규선** | **김지호** | **장욱재** | **박소정** |

<br>

## 🚀 프로젝트 목표

| 구분 | 목표 |
| :---: | :--- |
| **🔐 보안** | **Zero Trust 기반 다층 방어**: 내/외부 위협 실시간 탐지 및 100% 자동화 대응 |
| **⚡ 성능** | **대규모 트래픽 처리 및 무중단 DR**: '올영세일' 수준 트래픽 처리, 2분 내 재해 복구 |
| **💰 비용** | **FinOps 기반 비용 최적화**: 유휴 리소스 및 스토리지 비용 자동 관리 및 추적 |

<br>

## 🏗️ 아키텍처

<table border="0">
 <tr>
  <td align="center"><img src="https://github.com/user-attachments/assets/4116044f-862b-48aa-bac7-13a4b1975c0b" width="100%" /></td>
  <td align="center"><img src="https://github.com/user-attachments/assets/18b6b3bf-4d14-400b-80cc-8e5352d1e712" width="100%" /></td>
 </tr>
 <tr>
  <td colspan="2" align="center"><strong> AWS Seoul Region (Production / Staging)</strong></td>
 </tr>
</table>

<br>

<p align="center">
  <img src="https://github.com/user-attachments/assets/323898de-7179-4fde-b4a0-7fde79ba35f5" width="700" />
  <br>
  <strong> AWS Tokyo Region </strong>
</p>

* **Hybrid Cloud**: `On-Premise` (GitLab) + `AWS Cloud` (EKS) 연동
* **Multi-AZ**: `운영계(Seoul)` 다중 AZ 구성으로 고가용성 확보
* **Disaster Recovery**: `DR Site(Tokyo)` Warm Standby 구성 (2분 내 자동 전환)

<br>

## ✨ 핵심 기능

### 🔐 보안 (Security)

* **Zero Trust Architecture**:
    * **SPIRE**: 플랫폼 독립적인 신원 증명을 통한 서비스 간 상호 인증(mTLS) 구현
    * **초단기 인증서**: 60초 수명 인증서 30초 주기 자동 갱신 (인증서 탈취 피해 최소화)
* **다층 방어 체계**:
    * **AWS WAF**: SQL Injection, XSS 등 OWASP Top 10 기반 외부 웹 공격 방어
    * **Falco**: 컨테이너 런타임 환경 커널 레벨 이상 행위 실시간 탐지 (내부 위협 대응)
    * **SonarQube & Secret Scanner**: CI 단계 코드 취약점 및 민감 정보 노출 사전 차단
* **자동화된 위협 대응 및 리포팅**:
    * **WAF → OpenSearch → Slack**: 외부 공격 실시간 탐지-시각화-알림 파이프라인
    * **S3 → Athena → SES**: 방대한 로그를 `Athena`로 자동 분석, 일일 보안 보고서 이메일 발송

### ⚡ 성능 (Performance)

* **지능형 오토스케일링**:
    * **Prometheus → HPA → Karpenter**: `Prometheus` 커스텀 메트릭 기반 Pod 확장(`HPA`), `Karpenter`의 Just-in-Time 방식 Node 프로비저닝 연동
* **성능 향상 기술**:
    * **Kafka**: 대규모 주문 요청 비동기 메시지 큐 방식으로 처리, 병목 현상 해소
    * **VPC Endpoint**: AWS 내부망을 통한 서비스-DB 간 통신 지연 시간 최소화
    * **AWS Graviton (ARM)**: x86 아키텍처 대비 최대 40% 향상된 가성비의 ARM 프로세서 도입

<br>

## 성능 검증: '올영세일' 시나리오 스트레스 테스트

> '올영세일'과 같은 최대 부하 상황을 가정하여, 지능형 오토스케일링 시스템이 안정적으로 동작하는지 검증했습니다.

* **시나리오 정의**:
    * **기준**: 올리브영 공식 트래픽 5단계 모델 기반
    * **목표**: 최고 부하 단계인 **'(S) Special - 올영세일'** (평시 20배 이상) 트래픽을 안정적으로 처리

<p align="center">
  <img width="800" alt="Traffic Level Scenario" src="https://github.com/user-attachments/assets/3cf9d698-9d68-42bf-9ef7-fcc1b7d77565" />
</p>

---

* **실시간 스케일링 동작**:
    * **Pod 확장 (HPA)**: `Prometheus`로 수집된 CPU/Memory 임계값 초과 시 HPA가 Pod 수를 **4개에서 13개로 확장**
    * **Node 프로비저닝 (Karpenter)**: HPA에 의해 스케줄링 불가능한 Pod 발생 시 `Karpenter`가 신규 Node(7개→10개)를 **Just-in-Time 방식으로 즉시 프로비저닝**

<p align="center">
  <img width="800" alt="Real-time Scaling Visualization" src="https://github.com/user-attachments/assets/cdbfa3ab-24c4-495a-a1a4-512d92d87bef" />
</p>

---

* **테스트 결과 (Grafana 대시보드)**:
    * **결과**: 트래픽 폭증에 성공적으로 대응 후, 트래픽 감소 시 Pod와 Node가 설정된 기준에 따라 안정적으로 축소됨을 확인
    * **Pod 수**: **4 → 13 → 4** (안정적 복귀)
    * **Node 수**: **7 → 10 → 8** (비용 최적화를 위한 점진적 축소)

<p align="center">
  <img width="800" alt="Grafana Dashboard Results" src="https://github.com/user-attachments/assets/6dd70aae-8b88-481e-9981-8c9bf5053d62" />
</p>
---
### 💰 비용 (Cost)

* **FinOps 적용**: 모든 리소스에 태그를 적용하여 팀/서비스 단위 비용 추적 및 분석
* **스토리지 비용 절감**:
    * **S3 Lifecycle Policy**: 데이터 접근 빈도에 따라 `Standard → IA → Glacier` 자동 이전 (44% 절감)
* **유휴 리소스 관리**:
    * **Lambda + EventBridge**: 심야 시간 개발 환경 리소스 자동 축소/종료 스케줄링

<br>

## 🛠️ 기술 스택

| 구분 | 기술 |
| :--- | :--- |
| **Cloud & Infra** | `AWS` `EC2` `EKS` `RDS Aurora` `S3` `Route53` `Lambda` `VPC` `ECS` `Fargate` |
| **Container** | `Docker` `Kubernetes` `Karpenter` `Helm` `HPA` |
| **Backend** | `Go` `Java (Spring Boot)` |
| **CI/CD & IaC** | `GitLab` `Jenkins` `ArgoCD` `Terraform` `Amazon ECR` |
| **Security** | `SPIRE (mTLS)` `Falco` `SonarQube` `AWS WAF` `Secret Scanner` `NIST ZTA` |
| **Monitoring** | `Prometheus` `Grafana` `OpenSearch` |
| **Message Queue** | `Kafka` |
| **Data Analysis** | `Amazon Athena` |

<br>

## 📊 핵심 성과

| 영역 | 성과 |
| :---: | :--- |
| **보안** | SSL Labs `B` → `A` 등급 달성 |
| **성능** | '올영세일' 부하 테스트 통과 (무중단 트래픽 처리) |
| **DR** | 재해 복구 전환 **2분 이내** 달성 (목표 60% 단축) |
| **비용** | 스토리지 비용 **44% 절감** (실제 환경 54% 기대) |

<br>

## 📂 레포지토리

* **MSA (Go)**: `product-service`, `order-service`
* **MSA (Java)**: `user-service`
* **Infrastructure**: `eks-cluster`, `aws-infra-terraform`
