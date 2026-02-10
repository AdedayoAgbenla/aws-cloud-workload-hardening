<h1>Container, Kubernetes &amp; Serverless Security Implementation</h1>
<h3>AWS Enterprise Environment</h3>

<h2>Overview</h2>
<p>
  This repository documents the implementation of security controls for containerized and serverless workloads in AWS.
  The solution focuses on reducing vulnerability risk in container images, enforcing secure Kubernetes runtime standards,
  tightening Lambda permissions, and preventing secrets leakage using managed secrets services.
</p>

<hr/>

<h2>Key Responsibilities</h2>
<ul>
  <li>Created a private Amazon ECR repository and enabled <strong>scan on push</strong> for container image vulnerability scanning</li>
  <li>Integrated Amazon Inspector with ECR to detect CVEs and classify vulnerabilities by severity</li>
  <li>Validated remediation by upgrading insecure base images (e.g., older NGINX) and rebuilding/pushing rescanned images</li>
  <li>Reviewed and tightened Lambda execution roles to enforce least privilege and remove unnecessary wildcard permissions</li>
  <li>Implemented secure secrets retrieval using AWS Secrets Manager (no plaintext secrets in environment variables)</li>
  <li>Scoped Lambda access to secrets using least-privilege IAM permissions (GetSecretValue on a specific secret ARN)</li>
  <li>Implemented Pod Security Standards (PSS) in EKS using namespace-level enforcement (restricted for production, baseline for staging)</li>
  <li>Validated PSS by blocking privileged workloads in production while allowing compliant workloads in staging</li>
  <li>Implemented Kubernetes RBAC using service accounts, Roles, and RoleBindings to restrict workload permissions</li>
  <li>Verified authorization behavior (allowed read-only pod access, denied destructive actions and secret access)</li>
</ul>

<hr/>

<h2>Tools &amp; Technologies</h2>
<ul>
  <li>Amazon ECR</li>
  <li>Amazon Inspector</li>
  <li>Amazon EKS</li>
  <li>Kubernetes Pod Security Standards (PSS)</li>
  <li>Kubernetes RBAC (ServiceAccounts, Roles, RoleBindings)</li>
  <li>AWS Lambda</li>
  <li>AWS IAM</li>
  <li>AWS Secrets Manager</li>
  <li>Amazon CloudWatch Logs</li>
</ul>

<hr/>

<h2>Impact</h2>
<ul>
  <li>Reduced risk of deploying vulnerable container images through continuous scanning and rebuild-based remediation</li>
  <li>Prevented insecure Kubernetes workloads from running in production using enforced runtime security policies</li>
  <li>Minimized blast radius of serverless workloads by enforcing least-privilege IAM permissions</li>
  <li>Reduced secrets leakage risk by using Secrets Manager and scoped access controls</li>
  <li>Improved overall workload security posture across containers, Kubernetes, and serverless services</li>
</ul>

<hr/>

<h2>Author</h2>
<p>
  <strong>Adedayo</strong><br/>
  AWS Cloud Architect | Cloud Security Specialist
</p>

<hr/>

<h2>Disclaimer</h2>
<p>
  All documentation is anonymized and does not contain confidential or proprietary information.
</p>
