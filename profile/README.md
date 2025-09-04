# 🌐 Cloud Infrastructure for Global OliveYoung

> K-뷰티 리더 올리브영의 글로벌 서비스 확장을 위한 MSA 기반 보안 인프라 구축 프로젝트

<p align="center">
  <img src="https://img.shields.io/badge/AWS-232F3E?logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white" />
  <img src="https://img.shields.io/badge/Go-00ADD8?logo=go&logoColor=white" />
  <img src="https://img.shields.io/badge/Java-007396?logo=java&logoColor=white" />
  <img src="https://img.shields.io/badge/Terraform-7B42BC?logo=terraform&logoColor=white" />
  <img src="https://img.shields.io/badge/GitLab-FC6D26?logo=gitlab&logoColor=white" />
</p>

---

### CJ OliveNetworks Cloud Wave 6기 | 팀 `최강zl존`

| [<img src="https://github.com/DongilMin.png" width="100">](https://github.com/DongilMin) | [<img src="https://github.com/gyuseon25.png" width="100">](https://github.com/gyuseon25) | [<img src="https://github.com/isuking6511.png" width="100">](https://github.com/isuking6511) | [<img src="https://github.com/dfadsfa.png" width="100">](https://github.com/dfadsfa) | [<img src="https://github.com/sojung102.png" width="100">](https://github.com/sojung102) |
| :---: | :---: | :---: | :---: | :---: |
| **민동일** | **심규선** | **김지호** | **장욱재** | **박소정** |

<br>

## 🚀 프로젝트 목표

> 전 세계로 확장하는 올리브영의 대규모 트래픽과 사이버 위협에 대응하고, 24/7 무중단 서비스를 제공하기 위해 **보안, 성능, 비용**을 모두 최적화한 클라우드 인프라를 설계하고 구축합니다.

| 구분 | 목표 | 세부 내용 |
| :---: | :--- | :--- |
| **🔐 보안** | Zero Trust 기반 다층 방어 | SPIRE(mTLS), AWS WAF, Falco를 통한 내/외부 위협 자동 탐지 및 대응 |
| **⚡ 성능** | 대규모 트래픽 및 DR | '올영세일' 수준(평시 10배) 트래픽 처리, 2분 내 DR 전환(Warm Standby) |
| **💰 비용** | 리소스 및 비용 최적화 | Karpenter, S3 Lifecycle, Lambda를 활용한 스토리지 및 유휴 리소스 자동 관리 |

<br>

## 🏗️ 아키텍처

> 보안과 확장성을 위해 On-Premise GitLab과 AWS Cloud를 연동한 **하이브리드 클라우드** 환경을 채택했습니다.


<p align="center">
  <img src="https://github.com/user-attachments/assets/4116044f-862b-48aa-bac7-13a4b1975c0b" width="700" />
  <br /><br />
  <img src="https://github.com/user-attachments/assets/323898de-7179-4fde-b4a0-7fde79ba35f5" width="700" />
</p>


* **On-Premise**: 소스코드 유출을 원천 차단하기 위한 GitLab 서버 (격리 사설망)
* **AWS Cloud (Seoul)**: EKS 기반 MSA 운영 환경 (Staging/Production 분리)
* **DR Site (Tokyo)**: Route53을 통한 2분 내 자동 전환이 가능한 재해 복구 환경

<br>

## 🛠️ 기술 스택

| 구분 | 기술 |
| :--- | :--- |
| **Cloud & Infra** | `AWS` `EC2` `EKS` `RDS Aurora` `S3` `Route53` `Lambda` |
| **Container** | `Docker` `Kubernetes` `Karpenter` `Helm` `HPA` |
| **Backend** | `Go` `Java (Spring Boot)` `Kafka` |
| **CI/CD & IaC** | `GitLab` `Jenkins` `ArgoCD` `Terraform` |
| **Security** | `SPIRE (mTLS)` `Falco` `SonarQube` `AWS WAF` |
| **Monitoring** | `Prometheus` `Grafana` `OpenSearch` |

<br>

## 📊 핵심 성과

| 영역 | 성과 | 비고 |
| :---: | :--- | :--- |
| **보안** | SSL Labs `B` → `A` 등급 | TLS 프로토콜 및 암호화 스위트 최적화 |
| **성능** | '올영세일' 부하 테스트 통과 | Auto Scaling을 통한 무중단 트래픽 처리 확인 |
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
    * `eks-cluster`: EKS 클러스터 설정 및 운영 (ArgoCD 연동)
    * `aws-infra-terraform`: Terraform 기반 AWS 인프라 코드 (IaC)
* **Legacy (Spring Boot)**
    * `product-service-springboot`: 상품 서비스 (리팩토링 전)
    * `order-service-springboot`: 주문 서비스 (리팩토링 전)
