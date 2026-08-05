# <u>**My Dare.io AI DevOps Journey — Environment Setup & Tooling**</u>

> This note documents a practical DevOps workstation setup for learning, automation, cloud operations, and infrastructure management.

## <u>**Table of Contents**</u>

1. Prepare Host Environment - Installation of Ubuntu 24 Linux.

2. Establish Version Control - Git and Visual Studio Code

3. Integrate AI Capabilities - Copilot.

4. Install Containerization Tools - Docker and Docker Compose.

5. Setting Up Kubernetes Tooling - Minikube, kubectl and Helm.

6. Configuring Cloud and Language Runtimes - AWS CLI, Azure CLI, Node.js and jq.

7. Deploying Infrastructure & Configuration Tools - Terraform and Ansible.

8. DevOps Environment Verification and Security Check


## <u>**1. Prepare Host Environment - Installation of Ubuntu 24 Linux**</u>

**What is it?**
The host environment is the computer or virtual machine where DevOps tools, applications, containers, and automation scripts will run.

**Minimum requirements**
- RAM: 4 GB minimum (16 GB recommended)
- Disk: 10 GB minimum (256 GB SSD recommended)
- Operating system: Linux, macOS, or Windows with WSL2
- Updated OS and packages

**Why it matters**
A DevOps engineer needs a stable environment to install and run tools such as Docker, Kubernetes, Terraform, Ansible, Git, and cloud CLI tools.

**Steps**
1. Check RAM, processor speed, and disk space.
2. Confirm the operating system version.
3. Ensure virtualization support is enabled if required.

**Useful commands**
```powershell
# Windows
msinfo32
systeminfo
dxdiag
```

```bash
# Linux/macOS
uname -a
free -h
df -h
```

**Common challenges**
- Incorrect VM disk/image configuration
- Virtualization disabled in BIOS/UEFI
- Insufficient disk space

**Resolution**
Reinstall the VM if necessary and ensure the ISO is attached correctly to the virtual disk controller.

**Result**
The host environment was successfully prepared for the installation of DevOps tools.

![Attached image](file:///C:/Users/USER/image.png)

---

## <u>**2. Establish Version Control - Git and Visual Studio Code**</u>

**What is Git?**
Git is a distributed version-control system used to track changes in source code, configuration files, infrastructure code, and automation scripts.

**Why it matters**
Git supports source-code management, collaboration, version history, branching and merging, CI/CD pipelines, infrastructure as code, and configuration management.

**Steps**
1. Install Git.
2. Verify the installation.
3. Configure your username and email.
4. Create or clone a repository.
5. Connect the repository to GitHub or GitLab.
6. Install Visual Studio Code.
7. Configure VS Code for DevOps work.

**Installation commands**
```powershell
# Windows (PowerShell)
winget install --id Git.Git -e
winget install --id Microsoft.VisualStudioCode -e
```

```bash
# Linux
sudo apt update
sudo apt install -y git
```

```bash
# Configure Git
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git --version
code --version
```

**Official links**
- Git: https://git-scm.com/downloads
- VS Code: https://code.visualstudio.com/
- GitHub: https://github.com/
- GitLab: https://about.gitlab.com/

**Common challenges**
- Git configuration problems
- Authentication issues when connecting to remote repositories
- Incorrect repository configuration

**Resolution**
Verify the repository URL, authentication method, and Git configuration before pushing or pulling changes.

**Result**
Git and Visual Studio Code were successfully configured for DevOps development.

![VS Code image](file:///C:/Users/USER/image%20vscode.png)

![Git image](file:///C:/Users/USER/image%20git.png)

---

## <u>**3. Integrate AI Capabilities - Copilot**</u>

**What is it?**
AI-assisted DevOps tools help engineers write code, troubleshoot errors, generate commands, and automate tasks.

**Examples**
- GitHub Copilot
- Amazon Q
- Gemini CLI
- Codex CLI
- LocalStack

**Why it matters**
AI can improve productivity in script generation, troubleshooting, infrastructure code, Docker configuration, Kubernetes manifests, Terraform, documentation, and automation.

**Example setup**
```bash
# Example: install Node.js first, then a CLI-based AI tool
sudo apt update
sudo apt install -y nodejs npm
npm install -g @githubnext/github-copilot-cli
```

**Official links**
- GitHub Copilot: https://github.com/features/copilot
- Amazon Q: https://aws.amazon.com/q/
- Gemini CLI: https://ai.google.dev/
- Codex CLI: https://openai.com/codex/
- LocalStack: https://localstack.cloud/

**Common challenges**
- Authentication or CLI configuration issues
- AI-generated commands needing manual correction
- Trust and validation concerns

**Resolution**
Always verify AI-generated commands before executing them in a live environment.

**Result**
AI tools were introduced as productivity assistants within the DevOps workflow.

![AI image](file:///C:/Users/USER/image%20AI.png)

---

## <u>**4. Install Containerization Tools - Docker and Docker Compose**</u>

**What is Docker?**
Docker is a containerization platform that packages applications and their dependencies into portable containers.

**What is Docker Compose?**
Docker Compose allows multiple containers and their configurations to be defined and managed together.

**Why it matters**
Containers provide consistency, portability, isolation, faster deployment, easier testing, and strong support for microservices and CI/CD workflows.

**Installation commands**
```powershell
# Windows
winget install --id Docker.DockerDesktop -e
```

```bash
# Linux
sudo apt update
sudo apt install -y docker.io docker-compose-plugin
sudo systemctl enable docker
sudo systemctl start docker
sudo usermod -aG docker $USER
```

```bash
# Verify installation
docker --version
docker compose version
docker run hello-world
```

**Official links**
- Docker: https://docs.docker.com/get-docker/
- Docker Compose: https://docs.docker.com/compose/

**Common challenges**
- Docker service inactive
- Package installation issues
- Docker daemon connectivity problems

**Resolution**
Check service status, verify permissions, and test with a simple container.

**Result**
Docker and Docker Compose were successfully installed and tested.

![Docker image](file:///C:/Users/USER/image%20DOCKER.png)

---

## <u>**5. Setting Up Kubernetes Tooling - Minikube, kubectl and Helm**</u>

**What is Kubernetes?**
Kubernetes is a container orchestration platform used to deploy, manage, scale, and maintain containerized applications.

**What are Minikube, kubectl, and Helm?**
- Minikube: a lightweight local Kubernetes cluster for learning and testing
- kubectl: the command-line tool for managing Kubernetes clusters
- Helm: a package manager for Kubernetes applications

**Why it matters**
These tools allow a DevOps engineer to deploy applications, manage workloads, troubleshoot clusters, and automate deployments.

**Installation commands**
```bash
# Linux
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
```

```bash
# Start and verify Minikube
minikube start
kubectl cluster-info
kubectl get namespaces
helm version
```

**Official links**
- Minikube: https://minikube.sigs.k8s.io/docs/start/
- kubectl: https://kubernetes.io/docs/tasks/tools/
- Helm: https://helm.sh/docs/intro/install/

**Common challenges**
- Repository setup issues
- Cluster startup problems
- Networking or driver-related concerns

**Resolution**
Confirm the installation, correct repository issues, and verify the cluster with kubectl.

**Result**
Minikube, kubectl, and Helm were successfully installed and configured for local Kubernetes work.

![Minikube image](file:///C:/Users/USER/image%20MINIKUBE%20AND%20KUBECTL.png)

![Kubectl image](file:///C:/Users/USER/image%20KUBECTL.png)

![Helm image](file:///C:/Users/USER/image%20HELM.png)

---

## <u>**6. Configuring Cloud and Language Runtimes - AWS CLI, Azure CLI, Node.js and jq**</u>

**What are they?**
- AWS CLI: manage Amazon Web Services resources from the terminal
- Azure CLI: manage Microsoft Azure resources from the terminal
- Node.js: JavaScript runtime used by many DevOps tools
- jq: command-line JSON processor

**Why it matters**
Cloud CLIs support automation and infrastructure management, while Node.js and jq assist with scripting and data processing.

**Installation commands**
```bash
# AWS CLI (Linux)
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

```bash
# Azure CLI (Linux)
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
```

```bash
# Node.js and jq
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs jq
```

```bash
# Verify installation
aws --version
az version
node --version
npm --version
jq --version
```

**Official links**
- AWS CLI: https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
- Azure CLI: https://learn.microsoft.com/cli/azure/install-azure-cli
- Node.js: https://nodejs.org/
- jq: https://jqlang.github.io/jq/download/

**Common challenges**
- Package installation problems
- CLI authentication issues
- Version compatibility concerns

**Resolution**
Verify package sources, installation versions, and authentication settings before using each tool.

**Result**
AWS, Azure, Node.js, npm, and jq were successfully installed and verified.

![AWS image](file:///C:/Users/USER/image%20AWS.png)

![Azure image](file:///C:/Users/USER/image%20AZURE.png)

![Node.js and jq image](file:///C:/Users/USER/image%20NODE%20JS%20AND%20JQ.png)

---

## <u>**7. Deploying Infrastructure & Configuration Tools - Terraform and Ansible**</u>

**What is Terraform?**
Terraform is an Infrastructure as Code tool used to define and provision infrastructure using configuration files.

**What is Ansible?**
Ansible is an automation and configuration-management tool used to configure systems, deploy applications, and automate repetitive administrative tasks.

**Why it matters**
Terraform helps create infrastructure consistently, while Ansible configures and manages systems after provisioning.

**Installation commands**
```bash
# Terraform (Ubuntu/Debian)
wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install -y terraform
```

```bash
# Ansible
sudo apt update
sudo apt install -y ansible
```

```bash
# Verify installation
terraform version
ansible --version
```

**Official links**
- Terraform: https://developer.hashicorp.com/terraform/install
- Ansible: https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

**Common challenges**
- Terraform repository not detected initially
- Ansible inventory or connectivity issues

**Resolution**
Correct the repository configuration, verify the installation, and then test a simple Terraform and Ansible workflow.

**Result**
Terraform and Ansible were successfully installed and prepared for infrastructure automation and configuration management.

![Terraform image](file:///C:/Users/USER/image%20TERRAFORM.png)

![Ansible image](file:///C:/Users/USER/image%20ANSIBLE.png)

---

## <u>**8. DevOps Environment Verification and Security Check**</u>

**What is verification?**
Verification is the process of checking that all installed tools are working correctly and that the environment has appropriate permissions and security settings.

**Why it matters**
DevOps environments contain infrastructure, applications, credentials, and automation systems. Proper verification helps reduce failures and security risks.

**Verification commands**
```bash
git --version
docker --version
docker compose version
kubectl version --client
minikube version
helm version
aws --version
az version
node --version
npm --version
jq --version
terraform version
ansible --version
```

**Security checklist**
- Review permissions and group memberships
- Protect credentials and secrets
- Keep tools updated
- Use least-privilege access

**Common challenges**
- Version errors
- Service or permission issues
- Authentication or repository errors

**Resolution**
Investigate each issue individually, review logs and configuration files, and rerun the verification commands.

**Result**
The DevOps workstation/server was verified and prepared for practical DevOps projects.


