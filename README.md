<h1 align="center">Hi, I'm Bala 👋</h1>
<h3 align="center">Senior Platform Engineer / DevOps Lead — AWS · Kubernetes · AI Agent Infrastructure</h3>

<p align="center">
  I design and build production-grade cloud infrastructure: Kubernetes platforms on AWS,
  Infrastructure-as-Code systems teams can actually trust, and — increasingly —
  the infrastructure layer for AI agent orchestration.
</p>

<p align="center">
  <a href="mailto:bkrishnagatla@gmail.com"><img src="https://img.shields.io/badge/Email-bkrishnagatla%40gmail.com-D14836?logo=gmail&logoColor=white" alt="Email"/></a>
  <!-- Add your LinkedIn once you have the URL handy:
  <a href="https://linkedin.com/in/YOUR-HANDLE"><img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  -->
</p>

---

### 🧰 Stack

<p align="left">
  <img src="https://img.shields.io/badge/Terraform-844FBA?logo=terraform&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenTofu-FFDA18?logo=opentofu&logoColor=black" />
  <img src="https://img.shields.io/badge/AWS-232F3E?logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/Amazon%20EKS-FF9900?logo=amazoneks&logoColor=white" />
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white" />
  <img src="https://img.shields.io/badge/Helm-0F1689?logo=helm&logoColor=white" />
  <img src="https://img.shields.io/badge/AWS%20Bedrock-FF9900?logo=amazonaws&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub%20Actions-2088FF?logo=githubactions&logoColor=white" />
  <img src="https://img.shields.io/badge/Datadog-632CA6?logo=datadog&logoColor=white" />
  <img src="https://img.shields.io/badge/CloudWatch-FF4F8B?logo=amazoncloudwatch&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" />
</p>

### 🚀 Featured projects

**[bedrock-agent-orchestration](https://github.com/balakrishnagatla/bedrock-agent-orchestration)** —
a production-pattern reference for an AWS Bedrock multi-agent orchestration
platform: a supervisor agent routing to specialist collaborator agents
(knowledge-base-grounded RAG + Lambda tool execution), fronted by a
Helm-deployed gateway on EKS. Zero static AWS credentials anywhere — OIDC
for CI/CD, IRSA for the cluster. Wraps `aws-ia/bedrock/aws` and
`terraform-aws-modules/eks/aws` rather than reinventing them, with a full
GitHub Actions GitOps pipeline (`tflint` + `checkov`/`tfsec` on every PR,
OIDC-authenticated apply on merge).

| | |
|---|---|
| **IaC** | Terraform / OpenTofu, modular, remote state (S3 + DynamoDB locking) |
| **AI/ML** | Bedrock Agents, multi-agent supervisor/collaborator pattern, OpenSearch Serverless RAG |
| **Platform** | EKS, Helm, IRSA, HPA/PDB, Datadog + CloudWatch observability |
| **CI/CD** | GitHub Actions, OIDC auth, environment-gated apply, policy-as-code scanning |

**[aws-landing-zone-foundation](https://github.com/balakrishnagatla/aws-landing-zone-foundation)** —
the foundational layer `bedrock-agent-orchestration` (and any other
workload repo) sits on top of: an AWS Organization with guardrail SCPs
(deny-leave-org, require-IMDSv2, region restriction), per-account VPC/NAT
topology sized by environment, and a CloudTrail + Config + GuardDuty
security baseline that's on by default in every account, not opt-in. The
Organization/SCP change path is deliberately manual-apply-only in CI —
never triggered by a merge to `main` — given how much a bad SCP can break
at once.

| | |
|---|---|
| **Governance** | AWS Organizations, OUs, root-level SCPs |
| **Networking** | Wraps `terraform-aws-modules/vpc/aws`; env-sized NAT topology (single vs. per-AZ) |
| **Security baseline** | CloudTrail, AWS Config + managed rules, GuardDuty, IAM password policy |
| **CI/CD** | Same OIDC pipeline pattern, with a hard manual-apply gate on the org-wide change path |

### 🧭 Reference architectures I build on

I don't reinvent well-maintained IaC — I wrap it, pin it, and compose it into
opinionated platform patterns. These are the modules underpinning my
current work:

**AI & Automation (AWS Bedrock & Agents)**
- [`aws-ia/terraform-aws-bedrock`](https://github.com/aws-ia/terraform-aws-bedrock) — AWS's own Integration & Automation team module for Bedrock Agents, OpenSearch Serverless knowledge bases, and guardrails. Core of [bedrock-agent-orchestration](https://github.com/balakrishnagatla/bedrock-agent-orchestration).
- [`aws-samples/bedrock-agents-for-eks`](https://github.com/aws-samples/bedrock-agents-for-eks) — AWS sample combining EKS and Bedrock Agents; a useful cross-check for gateway/IRSA design choices.

**Kubernetes & Container Infrastructure (AWS EKS)**
- [`terraform-aws-modules/terraform-aws-eks`](https://github.com/terraform-aws-modules/terraform-aws-eks) — the community-standard EKS module (4,000+ ⭐); what I reach for over hand-rolled cluster resources every time.
- [`aws-ia/terraform-aws-eks-blueprints`](https://github.com/aws-ia/terraform-aws-eks-blueprints) — AWS's enterprise EKS starter kit (Karpenter, GitOps tooling, observability operators) for the cluster-platform layer underneath multi-workload clusters.

**Multi-Account Landing Zone & Networking**
- [`aws-samples/aws-startup-landing-zone-terraform-example`](https://github.com/aws-samples/aws-startup-landing-zone-terraform-example) — AWS's reference pattern for VPCs, NAT gateways, subnets, and remote-state management. What [aws-landing-zone-foundation](https://github.com/balakrishnagatla/aws-landing-zone-foundation) follows the principles of.
- [`MitocGroup/terraform-aws-landing-zone`](https://github.com/MitocGroup/terraform-aws-landing-zone) — open-source multi-account AWS Organizations and IAM baseline provisioning; a useful design-tradeoff comparison.

### 📊 GitHub activity

<p align="left">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=balakrishnagatla&show_icons=true&theme=default&hide_border=true&count_private=true" />
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=balakrishnagatla&layout=compact&hide_border=true" />
</p>

---

<p align="center"><sub>This profile and the pinned repo above were scaffolded with an AI coding assistant and reviewed/edited by me — the infrastructure patterns reflect real production practices, not generated filler.</sub></p>
