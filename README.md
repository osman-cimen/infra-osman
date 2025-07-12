# infra-osman

1-Terraform, Ansible, Vagrant ve Kubespray kullanarak Kubernetes cluster'ını kurmak ve ingress ile dışa açmak ilk adım olacak. 
2-Ardından, PVC'ler için NFS altyapısını kurarak devam edeceğiz. 
3-Hashicorp Vault kurulumu da Kubernetes ile güvenli bağlantıyı sağlamak için kritik bir adım olacak.
4-CI/CD süreci için ise uygulamanın kodunun depolanması ve yönetilmesi için Git reposu ve CI aracı olarak Jenkins kullanılması planlanmış. CD süreci için ArgoCD veya Flux gibi araçlarla otomatik deployment sağlanacak. 
5- Dev ve prod ortamlarının ayrılması, ortam spesifik konfigürasyonların Kustomize veya benzeri araçlarla yönetilmesi de oldukça önemli.
6-Son olarak, Observability kısmında Prometheus&Grafana ile metrik, log ve izleme değerlerinin takibi ve Grafana üzerinde dashboard'ların oluşturulması planlanıyor. 7-Alarm üretimi için Alert Manager gibi araçlarla Slack gibi platformlara bildirimler gönderilecek.

.
Kubernetes Cluster yapısı için;

Ubuntu 22.04

Kaynak Planlaması:
Node Tipi	Adet CPU	RAM	       Disk
Master	     3	  2	   2-4 GB	  20 GB
Worker	     3	  2	   2-4 GB	  20 GB
Toplam	     6	 12	   12-24 GB	  120 GB+

Dosya yapısı:

infra-osman/
├── vagrant/
│   └── Vagrantfile     
├── ansible/
│   ├── inventory.ini  
│   └── playbooks/
│       └── prepare.yml 
├── kubespray/          
│   └── inventory/mycluster/ 
└── README.md

