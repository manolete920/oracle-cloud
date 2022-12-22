# Access cluster

```bash
oci ce cluster create-kubeconfig --cluster-id ocid1.cluster.oc1.iad.aaaaaaaazfli7nnhq7qwjks43fehq2ycoynpvfik64hm5kbsecq5zfvo2bfq --file $HOME/.kube/config --region us-ashburn-1 --token-version 2.0.0  --kube-endpoint PUBLIC_ENDPOINT
```

# Checar pods

```bash
kubectl get pods --all-namespaces
```

output

```bash
mgarciar@cloudshell:~ (us-ashburn-1)$ kubectl get pods --all-namespaces
NAMESPACE          NAME                                                     READY   STATUS    RESTARTS     AGE
kube-system        coredns-746957c9c6-v8zxw                                 1/1     Running   0            2d
kube-system        csi-oci-node-g745z                                       1/1     Running   1 (2d ago)   2d
kube-system        kube-dns-autoscaler-6f789cfb88-vhlfh                     1/1     Running   0            2d
kube-system        kube-flannel-ds-tc7z6                                    1/1     Running   1 (2d ago)   2d
kube-system        kube-proxy-klmmh                                         1/1     Running   0            2d
kube-system        proxymux-client-w9h7l                                    1/1     Running   0            2d
mushop-utilities   cert-manager-646c67487-ggfqd                             1/1     Running   0            2d
mushop-utilities   cert-manager-cainjector-7cb8669d6b-cpwbm                 1/1     Running   0            2d
mushop-utilities   cert-manager-webhook-84f57d75bc-sxgqp                    1/1     Running   0            2d
mushop-utilities   metrics-server-84bdc86799-2n8bw                          1/1     Running   1 (2d ago)   2d
mushop-utilities   mushop-utils-grafana-6b9c54c9b5-pk7gf                    3/3     Running   0            2d
mushop-utilities   mushop-utils-ingress-nginx-controller-7d5df594cb-m5jm6   1/1     Running   0            2d
mushop-utilities   prometheus-alertmanager-556687cb9b-wrv6f                 2/2     Running   0            2d
mushop-utilities   prometheus-kube-state-metrics-69cd9698b6-8lq8d           1/1     Running   0            2d
mushop-utilities   prometheus-node-exporter-2sdn4                           1/1     Running   0            2d
mushop-utilities   prometheus-pushgateway-84669ffc6d-nvv8p                  1/1     Running   0            2d
mushop-utilities   prometheus-server-89dcbcd9-n7kd6                         2/2     Running   0            2d
mushop             mushop-api-99f4cd58b-fh6mh                               1/1     Running   0            2d
mushop             mushop-assets-7dddf887d5-p8rmp                           1/1     Running   0            2d
mushop             mushop-edge-7674d5484d-g2z9x                             1/1     Running   0            2d
mushop             mushop-fulfillment-6d568c7fb5-mngt6                      1/1     Running   0            2d
mushop             mushop-nats-8678987b7c-nwhfm                             2/2     Running   0            2d
mushop             mushop-payment-65f68f8dff-xzmpg                          1/1     Running   0            2d
mushop             mushop-session-6484c5d995-nftr9                          1/1     Running   0            2d
mushop             mushop-storefront-5c4d8d4844-n68qr                       1/1     Running   0            2d
```

# Ver la ip del balanceador

```bash
kubectl get svc --all-namespaces
```

outlook

```bash
mgarciar@cloudshell:~ (us-ashburn-1)$ kubectl get svc --all-namespaces
NAMESPACE          NAME                                              TYPE           CLUSTER-IP      EXTERNAL-IP                             PORT(S)                      AGE
default            kubernetes                                        ClusterIP      10.96.0.1       <none>                                  443/TCP,12250/TCP            2d
kube-system        kube-dns                                          ClusterIP      10.96.5.5       <none>                                  53/UDP,53/TCP,9153/TCP       2d
mushop-utilities   cert-manager                                      ClusterIP      10.96.50.168    <none>                                  9402/TCP                     2d
mushop-utilities   cert-manager-webhook                              ClusterIP      10.96.12.104    <none>                                  443/TCP                      2d
mushop-utilities   metrics-server                                    ClusterIP      10.96.119.40    <none>                                  443/TCP                      2d
mushop-utilities   mushop-utils-grafana                              ClusterIP      10.96.240.128   <none>                                  80/TCP                       2d
mushop-utilities   mushop-utils-ingress-nginx-controller             LoadBalancer   10.96.220.206   193.122.176.82                          80:31093/TCP,443:32423/TCP   2d
mushop-utilities   mushop-utils-ingress-nginx-controller-admission   ClusterIP      10.96.87.189    <none>                                  443/TCP                      2d
mushop-utilities   mushop-utils-ingress-nginx-controller-metrics     ClusterIP      10.96.148.29    <none>                                  10254/TCP                    2d
mushop-utilities   prometheus-alertmanager                           ClusterIP      10.96.100.237   <none>                                  80/TCP                       2d
mushop-utilities   prometheus-kube-state-metrics                     ClusterIP      10.96.225.52    <none>                                  8080/TCP                     2d
mushop-utilities   prometheus-node-exporter                          ClusterIP      None            <none>                                  9100/TCP                     2d
mushop-utilities   prometheus-pushgateway                            ClusterIP      10.96.144.120   <none>                                  9091/TCP                     2d
mushop-utilities   prometheus-server                                 ClusterIP      10.96.108.79    <none>                                  80/TCP                       2d
mushop             edge                                              ClusterIP      10.96.8.188     <none>                                  80/TCP                       2d
mushop             fulfillment                                       ClusterIP      10.96.145.230   <none>                                  80/TCP                       2d
mushop             mushop-api                                        ClusterIP      10.96.212.203   <none>                                  80/TCP                       2d
mushop             mushop-assets                                     ClusterIP      10.96.124.69    <none>                                  80/TCP                       2d
mushop             mushop-grafana-ingress                            ExternalName   <none>          mushop-utils-grafana.mushop-utilities   <none>                       2d
mushop             mushop-nats                                       ClusterIP      10.96.56.192    <none>                                  4222/TCP,6222/TCP,8222/TCP   2d
mushop             mushop-session                                    ClusterIP      10.96.157.130   <none>                                  6379/TCP                     2d
mushop             mushop-storefront                                 ClusterIP      10.96.218.138   <none>                                  80/TCP                       2d
mushop             payment                                           ClusterIP      10.96.13.120    <none>                                  80/TCP                       2d
```

external: 193.122.176.82

# Probar en el navegador

```
http://193.122.176.82/
```

# Probar grafana

```bash
http://193.122.176.82/grafana/login
```

Usuario: admin

Obtner la clave desde la consola usando:

```bash
kubectl get secret -n mushop-utilities mushop-utils-grafana \
-o jsonpath="{.data.admin-password}" | base64 --decode ; echo
```

output

```bash
mgarciar@cloudshell:~ (us-ashburn-1)$ kubectl get secret -n mushop-utilities mushop-utils-grafana \
> -o jsonpath="{.data.admin-password}" | base64 --decode ; echo
qFAHPGDxLlpVY2RX6tEERXmIBcZxjneEFHzQq0ku
```

# Hace watch

```bash
kubectl get deployment mushop-payment -n mushop --watch
```

output

```bash
mgarciar@cloudshell:~ (us-ashburn-1)$ kubectl get deployment mushop-payment -n mushop --watch
NAME             READY   UP-TO-DATE   AVAILABLE   AGE
mushop-payment   1/1     1            1           2d
```

ctr-c

# Escalar servicio de mushop

```bash
 kubectl scale deployment mushop-payment -n mushop --replicas=100
```

# ver los nodos

```bash
mgarciar@cloudshell:~ (us-ashburn-1)$ kubectl get nodes
NAME           STATUS   ROLES   AGE   VERSION
10.20.10.111   Ready    node    2d    v1.24.1
```

# Ver progreso de los deployments

```bash
kubectl get deployment mushop-payment -n mushop --watch
```

no funciona:

```bash
https://docs.oracle.com/en-us/iaas/Content/ContEng/Tasks/contengusingclusterautoscaler.htm
```

1. Colocar permisos de IAM
2. Lanzar un archivo YAML con las configuraciones
   1. Cuantos es la cantidad de workers
   2. OCIID del cluster
   3. 

# Eliminar

* Developer Sevice -> Stack 

* Selecciona el stak

* Click en destroy

  ```
  Getting providers from hashicorp registry and/or custom terraform providers
  Initializing provider plugins...
  - Reusing previous version of hashicorp/local from the dependency lock file
  - Reusing previous version of hashicorp/random from the dependency lock file
  - Reusing previous version of hashicorp/oci from the dependency lock file
  - Reusing previous version of hashicorp/kubernetes from the dependency lock file
  - Reusing previous version of hashicorp/helm from the dependency lock file
  - Reusing previous version of hashicorp/tls from the dependency lock file
  - Installing hashicorp/helm v2.1.0...
  - Installed hashicorp/helm v2.1.0 (signed by HashiCorp)
  - Installing hashicorp/tls v3.1.0...
  - Installed hashicorp/tls v3.1.0 (signed by HashiCorp)
  - Installing hashicorp/local v2.1.0...
  - Installed hashicorp/local v2.1.0 (signed by HashiCorp)
  - Installing hashicorp/random v3.1.0...
  - Installed hashicorp/random v3.1.0 (signed by HashiCorp)
  - Installing hashicorp/oci v4.102.0...
  - Installed hashicorp/oci v4.102.0 (unauthenticated)
  - Installing hashicorp/kubernetes v2.2.0...
  - Installed hashicorp/kubernetes v2.2.0 (signed by HashiCorp)
  Terraform has been successfully initialized!
  You may now begin working with Terraform. Try running "terraform plan" to see
  any changes that are required for your infrastructure. All Terraform commands
  should now work.
  If you ever set or change modules or backend configuration for Terraform,
  rerun this command to reinitialize your working directory. If you forget, other
  commands will detect it and remind you to do so if necessary.
  tls_private_key.oke_worker_node_ssh_key: Refreshing state... [id=dcdea827b6839f84197ecde953be3ef5c80de4da]
  random_string.autonomous_database_wallet_password: Refreshing state... [id=fw^B829}<5N3Oicn]
  random_string.autonomous_database_admin_password: Refreshing state... [id=8Z[^9dH07s%wRY<K]
  random_string.deploy_id: Refreshing state... [id=C1ZZ]
  oci_core_virtual_network.oke_vcn[0]: Refreshing state... [id=ocid1.vcn.oc1.iad.amaaaaaaj6ty54aakc3xdrhizuqgxkvd2kuwl2mlkjod3abs73iq3wvoyh7q]
  oci_core_service_gateway.oke_service_gateway[0]: Refreshing state... [id=ocid1.servicegateway.oc1.iad.aaaaaaaa2wnzyto5islvhb53aq3v2frul5wne6ggsarg3qzkfuz7pomehmaq]
  oci_core_security_list.apigw_fn_security_list[0]: Refreshing state... [id=ocid1.securitylist.oc1.iad.aaaaaaaapl6dtsw2yklgccjlzo5elkkp6nj3wt5khf3xjq3coinjshbv6uxq]
  oci_core_security_list.oke_lb_security_list[0]: Refreshing state... [id=ocid1.securitylist.oc1.iad.aaaaaaaa2pg5txdyqw3uuxycakhg5utju7fwmc7xix3cmssqvk6yjh662kda]
  oci_core_internet_gateway.oke_internet_gateway[0]: Refreshing state... [id=ocid1.internetgateway.oc1.iad.aaaaaaaae65bdkuwqbrtmj2ybhkpryhwmeerytygympwdncdr5eb2gzg4x7q]
  oci_core_nat_gateway.oke_nat_gateway[0]: Refreshing state... [id=ocid1.natgateway.oc1.iad.aaaaaaaazhrc62ivvqw7ks47o7pzjk2yxvticqwicl2fn5hef7ksy2vw3fpq]
  oci_core_security_list.oke_endpoint_security_list[0]: Refreshing state... [id=ocid1.securitylist.oc1.iad.aaaaaaaarvpyw7xiqequcrr6v2g3luy3gh42m2xsf742wsyt7nnngsn3urbq]
  oci_core_security_list.oke_nodes_security_list[0]: Refreshing state... [id=ocid1.securitylist.oc1.iad.aaaaaaaamhva2yimlgzhmw3urq2hxc2sqyjwzl5gg36raqf5hsgt5e7imfsa]
  oci_core_route_table.oke_private_route_table[0]: Refreshing state... [id=ocid1.routetable.oc1.iad.aaaaaaaaiikhrkudtfgpvheoitpnup4zzwarv754x4rgiksuzdrtdjghgscq]
  oci_identity_dynamic_group.app_dynamic_group[0]: Refreshing state... [id=ocid1.dynamicgroup.oc1..aaaaaaaayaj3poakebaflbeve7zhonek44m7wfdyd6xmfmxpmblx7mrtzbgq]
  oci_core_route_table.oke_public_route_table[0]: Refreshing state... [id=ocid1.routetable.oc1.iad.aaaaaaaaupgfzwpzzscphiktm34ncyi2epf66rnzm57usjtatq3rxsik4l7a]
  oci_core_route_table.apigw_fn_route_table[0]: Refreshing state... [id=ocid1.routetable.oc1.iad.aaaaaaaabjji67gcdshlsyzgwio7lxcls5l2xzklve2kryzcdgc76hrcv4wa]
  oci_core_subnet.apigw_fn_subnet[0]: Refreshing state... [id=ocid1.subnet.oc1.iad.aaaaaaaa6e6px6g3jfomddmxbrb3cccouci6capddbix77kilygmzb3sdb5q]
  oci_identity_policy.app_compartment_policies[0]: Refreshing state... [id=ocid1.policy.oc1..aaaaaaaa57tiaadimxyykyruq4bckwbqwxqgfatdeaksvr2bdpxhf42zksda]
  oci_core_subnet.oke_lb_subnet[0]: Refreshing state... [id=ocid1.subnet.oc1.iad.aaaaaaaabt5ulj33jhff7bhxhw4hdisvvihnxu4dk3moxbpwivpyygcmas2a]
  oci_core_subnet.oke_nodes_subnet[0]: Refreshing state... [id=ocid1.subnet.oc1.iad.aaaaaaaashnzco2k632pb3zap2v7icmbtxsmnmn5bhuic4f5v2st6mv4xbfq]
  oci_core_subnet.oke_k8s_endpoint_subnet[0]: Refreshing state... [id=ocid1.subnet.oc1.iad.aaaaaaaarprrhs3aahew44277ertmoovtlylrpki4pyferudgvu2teqrtfbq]
  oci_containerengine_cluster.oke_cluster[0]: Refreshing state... [id=ocid1.cluster.oc1.iad.aaaaaaaazfli7nnhq7qwjks43fehq2ycoynpvfik64hm5kbsecq5zfvo2bfq]
  oci_containerengine_node_pool.oke_node_pool[0]: Refreshing state... [id=ocid1.nodepool.oc1.iad.aaaaaaaaq7bdrgpifh235as6iasouvsjox36kjgpxwpdv756anz3aerr2ixa]
  local_file.oke_kubeconfig: Refreshing state... [id=b5d8c5678f6b822412a3dd23626d1cd081764328]
  kubernetes_namespace.mushop_namespace: Refreshing state... [id=mushop]
  kubernetes_namespace.cluster_utilities_namespace: Refreshing state... [id=mushop-utilities]
  Error: Get "http://localhost/api/v1/namespaces/mushop-utilities": dial tcp [::1]:80: connect: connection refused
    with kubernetes_namespace.cluster_utilities_namespace,
    on mushop-utilities.tf line 6, in resource "kubernetes_namespace" "cluster_utilities_namespace" 
     6: resource "kubernetes_namespace" "cluster_utilities_namespace" {
  Error: Get "http://localhost/api/v1/namespaces/mushop": dial tcp [::1]:80: connect: connection refused
    with kubernetes_namespace.mushop_namespace,
    on mushop.tf line 6, in resource "kubernetes_namespace" "mushop_namespace" 
     6: resource "kubernetes_namespace" "mushop_namespace" {
   
  ```

  

* Eliminar el balanceador

* OKE
  * Node pool, scale 0 y luego eliminar
  * Checar si la instancia se esta borrando.
* Eliminar OKE
* Eliminar VCN

