# modul-06-cloud-security-dasar

Dasar cloud computing dan keamanan untuk pemula.  
Fokus pada konsep lintas vendor.  
Gunakan lab aman untuk eksperimen.

> [!TIP]
> Pahami Shared Responsibility Model terlebih dahulu.  
> Tanpa itu, kontrol sering salah tempat.

## Daftar Isi
- [Tujuan belajar](#tujuan-belajar)
- [Prasyarat](#prasyarat)
- [Model layanan dan deployment](#model-layanan-dan-deployment)
- [Shared Responsibility Model](#shared-responsibility-model)
- [Identitas dan IAM](#identitas-dan-iam)
- [Jaringan cloud](#jaringan-cloud)
- [Penyimpanan dan data protection](#penyimpanan-dan-data-protection)
- [Compute security](#compute-security)
- [Kubernetes security dasar](#kubernetes-security-dasar)
- [Serverless security](#serverless-security)
- [Enkripsi dan KMS](#enkripsi-dan-kms)
- [Logging dan monitoring](#logging-dan-monitoring)
- [Posture management dan guardrails](#posture-management-dan-guardrails)
- [DevSecOps dan IaC](#devsecops-dan-iac)
- [Ancaman umum di cloud](#ancaman-umum-di-cloud)
- [Incident response di cloud](#incident-response-di-cloud)
- [Latihan cepat](#latihan-cepat)
- [Cheat sheet perintah](#cheat-sheet-perintah)
- [Checklist ringkas](#checklist-ringkas)
- [Glosarium mini](#glosarium-mini)
- [Referensi lanjutan](#referensi-lanjutan)
- [Kontribusi](#kontribusi)

---

## Tujuan belajar
- Memahami konsep cloud lintas penyedia.  
- Menetapkan kontrol keamanan prioritas.  
- Menggunakan identitas dengan prinsip least privilege.  
- Menangani insiden dasar pada lingkungan cloud.

## Prasyarat
- Menguasai jaringan dan Linux dasar.  
- Punya akun cloud latihan atau sandbox.  
- Terbiasa dengan terminal dan Git.

---

## Model layanan dan deployment
- Layanan: **IaaS**, **PaaS**, **SaaS**.  
- Deployment: **Public**, **Private**, **Hybrid**, **Multi-cloud**.  
- Keamanan mengikuti model layanan terpilih.  
- Tanggung jawab berubah sesuai model.

---

## Shared Responsibility Model
- Vendor mengamankan **cloud**.  
- Pelanggan mengamankan **di atas cloud**.  
- Batas tanggung jawab berbeda per layanan.  
- Dokumentasikan asumsi dan gap kontrol.

**Referensi**
- [AWS Shared Responsibility](https://aws.amazon.com/compliance/shared-responsibility-model/)  
- [Azure Shared Responsibility](https://learn.microsoft.com/azure/security/fundamentals/shared-responsibility)  
- [Google Cloud Shared Responsibility](https://cloud.google.com/security/shared-responsibility)

---

## Identitas dan IAM
- Identitas adalah perimeter baru.  
- Gunakan **MFA** untuk semua akun penting.  
- Terapkan **least privilege** pada role dan policy.  
- Gunakan group, bukan izin per user.  
- Rotasi kredensial dan nonaktifkan yang tak terpakai.  
- Audit akses secara berkala.

**Contoh policy minimal (AWS)**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {"Effect":"Allow","Action":["s3:GetObject"],"Resource":["arn:aws:s3:::example/*"]}
  ]
}
````

**Referensi**

* [AWS IAM](https://docs.aws.amazon.com/iam/)
* [Azure AD / Entra ID](https://learn.microsoft.com/azure/active-directory/fundamentals/)
* [Cloud IAM GCP](https://cloud.google.com/iam/docs)

---

## Jaringan cloud

* Bangun jaringan dengan **VPC** atau **VNet**.
* Bagi subnet: public dan private sesuai kebutuhan.
* Gunakan **Security Group** atau **NSG** ketat.
* Gunakan **NACL** untuk stateless kontrol jaringan.
* Akses privat memakai **Private Endpoint**.
* Minimalkan IP publik pada beban kerja.

**Referensi**

* [AWS VPC](https://docs.aws.amazon.com/vpc/)
* [Azure Virtual Network](https://learn.microsoft.com/azure/virtual-network/)
* [VPC on GCP](https://cloud.google.com/vpc/docs)

---

## Penyimpanan dan data protection

* Aktifkan **encryption at rest** secara default.
* Gunakan bucket policy yang ketat.
* Blok akses publik yang tidak perlu.
* Gunakan versioning untuk pemulihan.
* Terapkan **object lock** saat perlu.
* Audit akses data dengan log bawaan.

**Referensi**

* [Amazon S3 Security](https://docs.aws.amazon.com/AmazonS3/latest/userguide/security-best-practices.html)
* [Azure Storage Security](https://learn.microsoft.com/azure/storage/common/security-guide)
* [Cloud Storage Security](https://cloud.google.com/storage/docs/security)

---

## Compute security

* Gunakan **managed identities** untuk VM.
* Nonaktifkan kredensial hardcoded.
* Patch rutin dan otomatis bila memungkinkan.
* Batasi metadata access sesuai rekomendasi.
* Gunakan **golden image** yang terstandar.
* Pisahkan lingkungan dev, test, dan prod.

---

## Kubernetes security dasar

* Gunakan **managed Kubernetes** bila memungkinkan.
* Terapkan **RBAC** ketat di cluster.
* Aktifkan **NetworkPolicy** untuk isolasi pod.
* Gunakan **Pod Security** atau admission policy.
* Scan images sebelum deploy.
* Pantau runtime untuk anomali.

**Referensi**

* [Kubernetes Security](https://kubernetes.io/docs/concepts/security/overview/)
* [CIS Kubernetes Benchmark](https://www.cisecurity.org/benchmark/kubernetes)

---

## Serverless security

* Fungsikan **least privilege** pada setiap fungsi.
* Validasi input dengan ketat.
* Hindari menyimpan secret di environment.
* Gunakan **secret manager** terpusat.
* Batasi egress melalui VPC integration.

---

## Enkripsi dan KMS

* Gunakan **KMS** untuk manajemen kunci.
* Pisahkan kunci per aplikasi atau domain.
* Rotasi kunci sesuai kebijakan.
* Batasi akses **encrypt/decrypt** per identitas.
* Audit pemakaian kunci di log.

**Referensi**

* [AWS KMS](https://docs.aws.amazon.com/kms/)
* [Azure Key Vault](https://learn.microsoft.com/azure/key-vault/general/)
* [Cloud KMS GCP](https://cloud.google.com/kms/docs)

---

## Logging dan monitoring

* Aktifkan audit log untuk semua layanan.
* Contoh: **CloudTrail**, **Activity Log**, **Audit Logs**.
* Kirim log ke penyimpanan terpusat.
* Buat alert pada pola berbahaya.
* Visualisasikan metrik untuk respons cepat.

**Referensi**

* [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)
* [Azure Monitor](https://learn.microsoft.com/azure/azure-monitor/)
* [Cloud Logging](https://cloud.google.com/logging/docs)

---

## Posture management dan guardrails

* Gunakan **CSPM** untuk mendeteksi misconfig.
* Terapkan **policy-as-code** untuk guardrails.
* Nonaktifkan layanan tidak terpakai.
* Otomatiskan remediasi bila aman.
* Audit posture secara berkala.

**Referensi**

* [Azure Policy](https://learn.microsoft.com/azure/governance/policy/overview)
* [GCP Organization Policy](https://cloud.google.com/resource-manager/docs/organization-policy/org-policy-constraints)
* [AWS Config](https://docs.aws.amazon.com/config/)

---

## DevSecOps dan IaC

* Gunakan **IaC** seperti Terraform.
* Review PR untuk perubahan infrastruktur.
* Scan IaC memakai **tfsec** atau **Checkov**.
* Simpan secret di **secret manager**.
* Tambah kontrol di pipeline **CI/CD**.

**Contoh Terraform deny publik S3**

```hcl
resource "aws_s3_bucket_public_access_block" "this" {
  bucket                  = aws_s3_bucket.this.id
  block_public_acls       = true
  block_public_policy     = true
  ignore_public_acls      = true
  restrict_public_buckets = true
}
```

**Referensi**

* [Terraform Docs](https://developer.hashicorp.com/terraform/docs)
* [tfsec](https://aquasecurity.github.io/tfsec/)
* [Checkov](https://www.checkov.io/)

---

## Ancaman umum di cloud

* Kredensial bocor di repository publik.
* Bucket publik tanpa alasan jelas.
* Security group terlalu longgar.
* IAM policy terlalu luas.
* Enkripsi tidak diaktifkan.
* Logging audit tidak menyala.

---

## Incident response di cloud

* Dokumentasikan kontak dan eskalasi.
* Isolasi resource dengan cepat.
* Kumpulkan log dan snapshot forensik.
* Rotasi kredensial yang terdampak.
* Pulihkan dari backup tepercaya.
* Lakukan **lessons learned** terstruktur.

---

## Latihan cepat

* Buat VPC dengan subnet publik dan privat.
* Terapkan Security Group yang ketat.
* Nyalakan logging audit untuk akun lab.
* Buat bucket dengan block public access.
* Enkripsi bucket dengan KMS terkelola.
* Deploy fungsi serverless dengan least privilege.
* Tambahkan policy deny pada guardrails.

---

## Cheat sheet perintah

```bash
# AWS CLI
aws sts get-caller-identity
aws s3api get-bucket-policy-status --bucket my-bucket
aws ec2 describe-security-groups --query "SecurityGroups[*].GroupName"
aws kms list-keys

# Azure CLI
az account show
az storage account list --query "[].name"
az network nsg list --query "[].name"
az keyvault list

# gcloud CLI
gcloud auth list
gcloud storage buckets list
gcloud compute firewall-rules list
gcloud kms keyrings list

# kubectl
kubectl get ns
kubectl get networkpolicy -A
kubectl auth can-i get secrets --as system:serviceaccount:ns:sa
```

> [!WARNING]
> Uji hanya pada lingkungan milik Anda.
> Atau lingkungan berizin tertulis.

---

## Checklist ringkas

* [ ] MFA aktif untuk semua akun penting.
* [ ] IAM memakai least privilege.
* [ ] VPC dipisah public dan private.
* [ ] Security Group ketat dan terukur.
* [ ] Enkripsi at rest dan in transit aktif.
* [ ] Bucket blok akses publik.
* [ ] Logging audit menyala dan terpusat.
* [ ] KMS dikelola dengan rotasi.
* [ ] IaC terscan sebelum deploy.
* [ ] Guardrails policy-as-code berjalan.

---

## Glosarium mini

* VPC: jaringan virtual terisolasi.
* Security Group: firewall stateful instance.
* NACL: filter stateless antar subnet.
* IAM: manajemen identitas dan akses.
* KMS: layanan manajemen kunci.
* CSPM: pemantau posture konfigurasi cloud.
* IaC: infrastruktur sebagai kode.
* RBAC: kontrol akses berbasis peran.
* NetworkPolicy: aturan lalu lintas antar pod.
* Secret Manager: penyimpanan rahasia terpusat.

---

## Referensi lanjutan

**Konsep dan standar**

* [Cloud Security Alliance CCM](https://cloudsecurityalliance.org/research/cloud-controls-matrix)
* [CIS Benchmarks](https://www.cisecurity.org/cis-benchmarks)

**AWS**

* [Well-Architected Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/)
* [AWS Security Hub](https://docs.aws.amazon.com/securityhub/)

**Azure**

* [Azure Security Benchmark](https://learn.microsoft.com/security/benchmark/azure/)
* [Microsoft Defender for Cloud](https://learn.microsoft.com/azure/defender-for-cloud/)

**Google Cloud**

* [Security Foundations Guide](https://cloud.google.com/architecture/security-foundations)
* [Security Command Center](https://cloud.google.com/security-command-center)

**Kubernetes dan container**

* [Kubernetes Hardening Guide](https://www.cisa.gov/resources-tools/resources/kubernetes-hardening-guidance)
* [OWASP Kubernetes Top 10](https://owasp.org/www-project-kubernetes-top-ten/)

**DevSecOps dan policy**

* [Open Policy Agent](https://www.openpolicyagent.org/)
* [Kyverno](https://kyverno.io/)

---

## Kontribusi

* Fork repository ini.
* Buat branch fitur terpisah.
* Gunakan commit message yang jelas.
* Ajukan pull request ringkas.

---

[⬆️ Kembali ke atas](#modul-06-cloud-security-dasar)


