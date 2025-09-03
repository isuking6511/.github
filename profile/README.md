# Cloud Infrastructure for Global OliveYoung

> CJ 올리브네트웍스 클라우드 웨이브 6기 팀 프로젝트

## Member

| [![민동일](https://github.com/DongilMin.png)](https://github.com/DongilMin) | [![심규선](https://github.com/gyuseon25.png)](https://github.com/gyuseon25) | [![김지호](https://github.com/isuking6511.png)](https://github.com/isuking6511) | [![장욱재](https://github.com/dfadsfa.png)](https://github.com/dfadsfa) | [![박소정](https://github.com/sojung102.png)](https://github.com/sojung102) |
| :---: | :---: | :---: | :---: | :---: |
| **민동일** | **심규선** | **김지호** | **장욱재** | **박소정** |

# 글로벌 올리브영을 위한 최적의 보안 인프라

> 본 프로젝트는 CJ올리브네트웍스 클라우드웨이브 6기 5팀 '최강zl존'이 진행한 프로젝트입니다.  
K-뷰티의 글로벌 리더 올리브영이 전 세계로 뻗어나가는 과정에서 마주할 수 있는 인프라 과제를 해결하고, **보안, 성능, 비용** 세 마리 토끼를 모두 잡는 최적의 보안 인프라를 설계하고 구축했습니다.

---

## 📚 Table of Contents
- 프로젝트 개요  
- 핵심 목표  
- 구현 아키텍처  
- 주요 기능 및 구현  
- 보안 (Security)  
- 성능 (Performance)  
- 비용 (Cost)  
- 기술 스택  
- 프로젝트 성과  

---

## 📌 프로젝트 개요
**기획 배경**  
K-뷰티의 인기가 전 세계적으로 확산되면서 올리브영은 글로벌 시장에서 급격한 성장을 경험하고 있습니다.  
현재 **189개국 외국인 고객의 942만 건 결제**를 처리하며 K-뷰티 산업의 글로벌 리더십을 확보하고 있습니다.

하지만 이러한 성장은 인프라 관점에서 다음과 같은 도전 과제를 동반합니다.

- **전 세계 트래픽의 동시 처리**: 글로벌 고객을 대상으로 안정적인 서비스 제공 필요  
- **사이버 위협 증가**: KISA 보고서 기준, 침해사고 연간 50% 증가 / 유통·리테일 업계 주요 타겟  
- **24/7 무중단 서비스**: 글로벌 비즈니스는 중단 없는 운영 요구  

---

## 💡 핵심 목표

| 구분 | 목표 | 세부 내용 |
|------|------|-----------|
| 🔐 보안 (Security) | Zero Trust 기반 다층 방어 체계 | 제로 트러스트 원칙 설계, 실시간 위협 탐지 및 자동 대응 |
| ⚡ 성능 (Performance) | 대규모 트래픽 처리 및 무중단 서비스 | ‘올영세일’ 수준(평소 10배) 트래픽 처리, 2분 내 DR 전환 |
| 💰 비용 (Cost) | 클라우드 리소스·비용 최적화 | 스토리지 최적화, 자동 스케일링, 태그 기반 비용 관리 |

---

## 🏗️ 구현 아키텍처
- 보안성과 확장성을 모두 확보하기 위해 **하이브리드 클라우드** 환경 채택 

<p align="center">
  <img src="https://github.com/user-attachments/assets/4116044f-862b-48aa-bac7-13a4b1975c0b" width="500" />
  <img src="https://github.com/user-attachments/assets/323898de-7179-4fde-b4a0-7fde79ba35f5" width="500" />
</p>


**On-Premise**
- GitLab 서버: 소스코드 유출 원천 차단 (격리 사설망)  
- VPC Peering: 온프레 ↔ 클라우드 통신 암호화  

**AWS Cloud**
- **EKS 기반 MSA**: 유연하고 확장 가능한 아키텍처  
- **Karpenter**: 트래픽 기반 노드 자동 확장·축소  
- **환경 분리**: Staging ↔ Production VPC 분리  

**DR (재해복구)**
- 도쿄 리전 Warm Standby  
- **RDS Aurora 실시간 복제**  
- **Route53 자동 전환 (2분 이내)**  

---

## ✨ 주요 기능 및 구현

### 🔐 보안 (Security)
- **제로 트러스트 아키텍처**
  - SPIRE 기반 mTLS (서비스 간 상호 인증)  
  - 60초 수명 인증서 발급 / 30초 주기 자동 갱신  
- **다층 방어 체계**
  - AWS WAF: 웹 공격 방어 (SQLi, XSS 등)  
  - Falco: 컨테이너 런타임 이상행위 탐지  
- **자동화된 보안 대응**
  - 외부 위협: WAF 차단 + OpenSearch 대시보드 + Slack 알림  
  - 내부 위협: SonarQube 코드 취약점 검사 + 시크릿 스캐너  

### ⚡ 성능 (Performance)
- **지능형 자동 스케일링**: HPA ↔ Karpenter 연동  
- **성능 향상 기술**
  - Kafka: 대규모 요청 비동기 처리  
  - VPC Endpoint: 네트워크 지연 최소화  
  - ARM (Graviton): x86 대비 최대 40% 성능 ↑  

### 💰 비용 (Cost)
- **스토리지 최적화**
  - S3 Lifecycle Policy  
    - 0~30일: Standard  
    - 30~90일: Standard-IA  
    - 90일+: Glacier  
- **리소스 최적화**
  - Lambda + EventBridge로 야간 개발 리소스 자동 축소  
  - 태그 기반 비용 추적 및 불필요 리소스 자동 정리  

---

## 🛠️ 기술 스택

| 구분 | 기술 |
|------|------|
| Cloud | AWS (EC2, EKS, RDS Aurora, S3, Route53, WAF, Lambda) |
| Container | Docker, Kubernetes, EKS, Karpenter, HPA |
| CI/CD | GitLab, Jenkins, ArgoCD |
| Security | SPIRE, Falco, SonarQube, AWS WAF, mTLS |
| Monitoring | Prometheus, Grafana, OpenSearch |
| IaC | Terraform, Helm |
| Message Queue | Kafka |

---

## 📊 프로젝트 성과

| 영역 | 성과 | 비고 |
|------|------|------|
| 보안 | **SSL Labs B → A 등급** | TLS 최적화 |
| 성능 | ‘올영세일’ 부하 테스트 통과 | 무중단 처리 확인 |
| DR | 전환 시간 2분 이내 달성 | 목표 시간 충족 |
| 비용 | **스토리지 비용 44% 절감** | 실제 적용 시 54% 예상 |
| 운영 효율 | 자동 스케일링 → 유휴 리소스 최소화 | 최적 자원 유지 |

---
<img width="468" height="241" alt="스크린샷 2025-08-30 14 24 24" src="https://github.com/user-attachments/assets/7737403a-f46a-400c-956c-3335847f36b0" />
<img width="846" height="281" alt="스크린샷 2025-08-30 14 24 56" src="https://github.com/user-attachments/assets/eab3515b-ccc4-4218-bbc3-57edf77311c2" />
<img width="568" height="433" alt="스크린샷 2025-08-30 14 22 36" src="https://github.com/user-attachments/assets/3e953462-e8dd-485b-8d13-8fb76cf800bb" />
<img width="647" height="338" alt="스크린샷 2025-08-30 14 23 10" src="https://github.com/user-attachments/assets/40b3eaa9-7047-4091-a97c-49f067daa151" />
<img width="891" height="276" alt="스크린샷 2025-08-30 14 23 30" src="https://github.com/user-attachments/assets/8deeb054-d753-4473-b935-98fab946519a" />
<img width="849" height="372" alt="스크린샷 2025-08-30 14 23 40" src="https://github.com/user-attachments/assets/56219913-ebc1-47af-a105-3e80d7b8d5a4" />
<img width="735" height="433" alt="스크린샷 2025-08-30 14 23 56" src="https://github.com/user-attachments/assets/f667249c-a80a-492d-8f23-e628e7b79b27" />
