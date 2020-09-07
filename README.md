# Kubernetes FAQ

#### Flashcards

This repository features flashcards that can be used with any application that supports the `.apkg` deck format (such as [Anki](https://ankiweb.net)). Download the latest deck from the [Releases](https://github.com/devsplit/kubernetes/releases/) page and import the file inside your app.

## Configuration 

<details>
<summary>_____ allow you to create your own custom Kubernetes objects, to store any data you wish.&nbsp;</summary>
Custom Resource Definitions (CRDs)
<br></details><details>
<summary>The resource for storing sensitive information in Kubernetes.</summary>
Secrets
<br></details><details>
<summary>What Are Labels?</summary>
Key/value pairs that are attached to objects, such as pods.
<br></details><details>
<summary>One cpu, in Kubernetes request/limit terms, is equivalent to&nbsp;<strong>1 _____</strong>&nbsp;on bare-metal Intel processors.</summary>
<strong>hyperthread</strong>&nbsp;
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">The scheduler ensures that, for each resource type, the sum of the resource requests of the scheduled Containers is _____ than the capacity of the node.</span></summary>
<span style="color: rgb(34, 34, 34);">less</span>
<br></details><details>
<summary>Suppose you have several clusters, and your users and components authenticate in a variety of ways. For example:<ul><li>A running kubelet might authenticate using certificates.</li><li>A user might authenticate using tokens.</li><li>Administrators might have sets of certificates that they provide to individual users.</li></ul>With _____ files, you can organize your clusters, users, contexts, and namespaces.</summary>
kubeconfig
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Each context has three parameters:&nbsp;</span></summary>
<span style="color: rgb(34, 34, 34);">cluster, namespace, and user.&nbsp;</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">There is a concern that one Pod or Container could monopolize all available resources. A _____ is a policy to constrain resource allocations (to Pods or Containers) in a namespace.</span></summary>
<span style="color: rgb(34, 34, 34);">LimitRange</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A </span><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">provides constraints that limit aggregate resource consumption per namespace. It can limit the quantity of objects that can be created in a namespace by type, as well as the total amount of compute resources that may be consumed by resources in that project.</span></summary>
<code>ResourceQuota</code>
<br></details><details>
<summary>Do containers run with unbounded compute resources on a Kubernetes cluster?</summary>
By default - yes. Limits and ResourceQuotas are recommended.
<br></details><details>
<summary>You can enforce minimum and maximum compute resources usage per Pod or Container in a namespace using a...</summary>
LimitRange
<br></details><details>
<summary>You can&nbsp;<span style="background-color: rgb(255, 255, 255);">enforce minimum and maximum storage request per PersistentVolumeClaim in a namespace using a...</span></summary>
LimitRange
<br></details><details>
<summary>You can enforce a ratio between request and limit for a resource in a namespace using a...</summary>
LimitRange
<br></details><details>
<summary>You can set default request/limit for compute resources in a namespace and automatically inject them to Containers at runtime using a...</summary>
LimitRange
<br></details><details>
<summary>When you run a Pod on a Node, the Pod itself takes an amount of system resources. These resources are additional to the resources needed to run the container(s) inside the Pod.&nbsp;<i>_____&nbsp;</i>is a feature for accounting for the resources consumed by the Pod infrastructure on top of the container requests &amp; limits.</summary>
Pod Overhead
<br></details><details>
<summary>The _____ is the primary object for storing configuration data in Kubernetes. 
You can supply that data to an application either by creating a file in the Pod, or by injecting it into the Pod�s environment.</summary>
ConfigMap
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">The Kubernetes alpha feature </span><i>_____</i><span style="color: rgb(34, 34, 34);">&nbsp;provides an option to set individual Secrets and ConfigMaps as immutable. For clusters that extensively use ConfigMaps (at least tens of thousands of unique ConfigMap to Pod mounts)</span></summary>
Immutable Secrets and ConfigMaps
<br></details><details>
<summary>You can significantly reduce load on kube-apiserver and improve cluster performance by closing watches for secrets or config maps and, setting them as _____.</summary>
immutable
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">If the node where a Pod is running has enough of a resource available, it's allowed for a container to use more resources than defined in its resource&nbsp;</span><font face="monospace">_____</font><span style="color: rgb(34, 34, 34);">. However, a container is not allowed to use more than its resource&nbsp;</span><font face="monospace">_____</font><span style="color: rgb(34, 34, 34);">.</span></summary>
request
limit
<br></details><details>
<summary>A file that is used to configure access to clusters is called a _____ file</summary>
kubeconfig
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A </span><i>_____&nbsp;</i><span style="color: rgb(34, 34, 34);">element in a kubeconfig file is used to group access parameters under a convenient name.</span></summary>
context
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">default kubeconfig filepath</span></summary>
$HOME/.kube/config
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">The administrator creates one LimitRange per _____.</span></summary>
namespace
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">The <font face="monospace">_____&nbsp;</font></span>admission&nbsp;<span style="color: rgb(34, 34, 34);">controller enforces defaults and limits for all Pods and Containers that do not set compute resource requirements and tracks usage to ensure it does not exceed resource minimum, maximum and ratio defined in any LimitRange present in the namespace.</span></summary>
<code>LimitRanger</code><span style="color: rgb(34, 34, 34);">&nbsp;</span>
<br></details><details>
<summary>To&nbsp;define default CPU limit and request to 150m and memory default request to 300Mi for Containers started with no cpu and memory requests in their specs, you could use...</summary>
LimitRange
<br></details><details>
<summary>In a cluster with a capacity of 32 GiB RAM, and 16 cores, let team A use 20 GiB and 10 cores, let B use 10GiB and 4 cores, and hold 2GiB and 2 cores in reserve for future allocation.
You could create this policy via...</summary>
ResourceQuota
<br></details><details>
<summary>Pod Overhead is set at _____&nbsp;time according to the overhead associated with the Pod's _____. When enabled, it is considered in addition to the sum of container resource requests when scheduling a Pod. Similarly, Kubelet will include the Pod overhead when sizing the Pod cgroup, and when carrying out Pod eviction ranking.</summary>
admission
RuntimeClass
<br></details><details>
<summary>One cpu, in Kubernetes request/limit terms, is equivalent to&nbsp;<strong>1 _____</strong>&nbsp;for cloud providers.</summary>
core
<br></details><details>
<summary>What is Custom resource in Kubernetes?</summary>
A&nbsp;<em>custom resource</em>&nbsp;is an extension of the Kubernetes API. Many core Kubernetes functions are now built using custom resources, making Kubernetes more modular.
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">When a config map currently consumed in a volume is updated, are projected keys inside the Pods eventually updated as well?</span></summary>
Yes
<span style="color: rgb(34, 34, 34);">The kubelet checks whether the mounted config map is fresh on every periodic sync. However, the kubelet also uses its local configurable cache for getting the current value of the ConfigMap.&nbsp;</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">T</span><span style="color: rgb(34, 34, 34);">o pass a secret that contains a Docker (or other) image registry password to the kubelet, you can use...</span></summary>
<code>imagePullSecrets</code><span style="color: rgb(34, 34, 34);">&nbsp;</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">When a process in the container tries to consume more than the allowed amount of memory, the system kernel _____ the process that attempted the allocation, with an _____ error</span></summary>
<span style="color: rgb(34, 34, 34);">terminates</span>

OOM (Out of Memory)
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">When several users or teams share a cluster with a fixed number of nodes, there is a concern that one team could use more than its fair share of resources. _____&nbsp;</span><span style="color: rgb(34, 34, 34);">is a tool to address this concern.</span></summary>
ResorceQuota
<br></details><details>
<summary>_____ are key-value pairs that identify resources, and can be used with _____ to match a specified group of resources.</summary>
Labels
Selectors
<br></details><details>
<summary>If the data you want to store are confidential, use a _____ rather than a ConfigMap</summary>
Secret
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A _____ is an API object used to store non-confidential data in key-value pairs.&nbsp;</span><a href="https://kubernetes.io/docs/concepts/workloads/pods/pod-overview/">Pods<span style="background-color: rgb(85, 85, 85); color: rgb(255, 255, 255);"></span></a><span style="color: rgb(34, 34, 34);">&nbsp;can consume them as environment variables, command-line arguments, or as configuration files in a&nbsp;</span><a href="https://kubernetes.io/docs/concepts/storage/volumes/">volume<span style="background-color: rgb(85, 85, 85); color: rgb(255, 255, 255);"></span></a><span style="color: rgb(34, 34, 34);">.</span></summary>
<span style="color: rgb(34, 34, 34);">ConfigMap</span>
<br></details><details>
<summary>Mounting ConfigMaps in a Pod is done in its .spec._____</summary>
volumes
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">The&nbsp;</span><code>KUBECONFIG</code><span style="color: rgb(34, 34, 34);">&nbsp;environment variable holds...</span></summary>
A list of kubeconfig files
<br></details>

## Control_Plane 

<details>
<summary>Pods that wish to securely connect to the apiserver can automatically inject the public root certificate and valid bearer token into themselves. This is done by using a...</summary>
service account
<br></details><details>
<summary>apiserver to kubelet connection can be verified by adding the apiserver flag _____ or via _____</summary>
<b>--kubelet-certificate-authority</b>
<b>
</b>SSH tunneling
<br></details><details>
<summary>By decoupling the interoperability logic between Kubernetes and the underlying cloud infrastructure, _____ enables cloud providers to release features at a different pace compared to the main Kubernetes project.</summary>
cloud-controller-manager
<br></details><details>
<summary>the apiserver is configured to listen for remote connections on a secure _____ port with one or more forms of client _____ enabled</summary>
HTTPS
authentication
<br></details><details>
<summary>Are <b>apiserver</b>&nbsp;connections to <b>nodes, pods and services</b>&nbsp;authenticated or encrypted?</summary>
They can run over HTTPS but will NOT validate the certificate :(
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">The _____ is a daemon that embeds the core control loops shipped with Kubernetes.&nbsp;</span></summary>
<span style="color: rgb(34, 34, 34);">kube-controller-manager</span>
<br></details><details>
<summary>The Kubernetes Master is a collection of three processes that run on a single node in your cluster. These processes are...</summary>
apiserver, scheduler, controller-manager
<br></details><details>
<summary>Nodes should be provisioned with _____ for the cluster such that they can connect securely to the apiserver along with valid client credentials</summary>
public root certificate
<br></details><details>
<summary>The <b>kubernetes </b>service is configured in all namespaces&nbsp;with virtual IP address that is redirected via _____ to the apiserver.</summary>
kube-proxy
<br></details><details>
<summary>apiserver to kubelet connections terminate at</summary>
the kubelet's HTTPS endpoint
<br></details><details>
<summary>Does the <b>apiserver</b> verify the <b>kubelet's</b> serving certificate by default?</summary>
No. The connection is subject to MITM attacks by default.
<br></details><details>
<summary>The component that creates, annotates, destroys nodes and gets their information (like hostname, address or health) is called the...</summary>
Node controller
<br></details><details>
<summary>The three main control plane components are...</summary>
kubelets, master, etcd
<br></details><details>
<summary>All API usage from nodes and pods terminate at the following control plane components:</summary>
apiserver only.
<br></details>

## Jobs 

<details>
<summary><span style="color: rgb(34, 34, 34);">Suppose a CronJob is set to schedule a new Job every one minute beginning at&nbsp;</span><code>08:30</code><span style="color: rgb(34, 34, 34);">, and its&nbsp;</span><code>startingDeadlineSeconds</code><span style="color: rgb(34, 34, 34);">&nbsp;field is not set. If the CronJob controller happens to be down from&nbsp;</span><code>08:29</code><span style="color: rgb(34, 34, 34);">&nbsp;to&nbsp;</span><code>10:21</code><span style="color: rgb(34, 34, 34);">, what happens to the job?</span></summary>
<span style="color: rgb(34, 34, 34);">The job will not start.&nbsp;</span><span style="color: rgb(34, 34, 34);">The number of missed jobs which missed their schedule is greater than 100.</span>
<br></details><details>
<summary>Suppose a CronJob is set to schedule a new Job every one minute beginning at&nbsp;<code>08:30</code>, and its&nbsp;<code>startingDeadlineSeconds</code>&nbsp;is set to 200 seconds. If the CronJob controller happens to be down between&nbsp;<code>08:29</code>&nbsp;to&nbsp;<code>10:21,</code>&nbsp;the Job will still start at _____.&nbsp;</summary>
10:22
This happens as the controller checks how many missed schedules happened in the last 200 seconds (ie, 3 missed schedules).
<br></details><details>
<summary>Jobs on a repeating schedule are called...</summary>
CronJobs
<br></details><details>
<summary>One CronJob object is like one line of a _____ file. It runs a job periodically on a given schedule, written in Cron format.</summary>
crontab
<br></details><details>
<summary>Can CronJobs be used for running backups?</summary>
Yes
<br></details><details>
<summary>Because it is not guaranteed only one job will launch per execution time of its schedule, Jobs should be&nbsp;<i>_____&nbsp;</i></summary>
idempotent
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A CronJob is counted as missed if it...</span></summary>
<span style="color: rgb(34, 34, 34);">has failed to be created at its scheduled time.</span>
<br></details><details>
<summary>A job's default parallelism value is 1.<span style="color: rgb(34, 34, 34);">&nbsp;If it is specified as 0, then the Job...</span></summary>
<span style="color: rgb(34, 34, 34);">Is paused until it is increased.</span>
<br></details><details>
<summary>A job's parallelism is...</summary>
<span style="color: rgb(34, 34, 34);">The number of Job pods running at any instant.</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">The _____ provides a TTL (time to live) mechanism to limit the lifetime of resource objects that have finished execution.</span></summary>
<span style="color: rgb(34, 34, 34);">TTL controller</span>
<br></details><details>
<summary>The&nbsp;<span style="color: rgb(34, 34, 34);">TTL controller handles what resource?</span></summary>
Jobs
<br></details><details>
<summary>All CronJob schedules are based on the timezone of _____</summary>
the <b>kube-controller-manager</b>.
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">If a CronJob's&nbsp;</span><code>concurrencyPolicy</code><span style="color: rgb(34, 34, 34);">&nbsp;is set to&nbsp;</span><code>Forbid,</code><span style="color: rgb(34, 34, 34);">&nbsp;and it attempted to be scheduled when there was a previous schedule still running, then it would count as _____.</span></summary>
missed
<br></details><details>
<summary>Can CronJobs be used for sending e-mails?</summary>
Yes
<br></details><details>
<summary>The Job Controller counts how many jobs had missed in the last X seconds, but only if a CronJob's _____ field<b>&nbsp;</b>is set.</summary>
startingDeadlineSeconds&nbsp;
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A _____ creates one or more Pods and ensures that a specified number of them successfully terminate.&nbsp;</span><span style="color: rgb(34, 34, 34);">As pods successfully complete, it tracks the successful completions until a certain number of successful completions is reached.</span></summary>
<span style="color: rgb(34, 34, 34);">Job</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">For </span>a&nbsp;fixed completion count<span style="color: rgb(34, 34, 34);">&nbsp;Job, you should set its .spec._____ field</span></summary>
completions
<br></details><details>
<summary>_____ run a Pod a specified number of times before completing. _____ run a Pod periodically at specified times.</summary>
Jobs
CronJobs
<br></details>

## Network 

<details>
<summary>A Kubernetes resource that exposes deployments.</summary>
Services
<br></details><details>
<summary>Which <b>type </b>of Service makes it only reachable from within the cluster?</summary>
<b>ClusterIP </b>(default ServiceType)
<br></details><details>
<summary>Can you set up a DNS service for your Kubernetes cluster?</summary>
You almost always should. Ex.: CoreDNS
<br></details><details>
<summary>The _____ is the only way to access ExternalName Services.</summary>
Kubernetes&nbsp;DNS server
<br></details><details>
<summary>The service type that&nbsp;<span style="color: rgb(34, 34, 34);">exposes a Service on a cluster-internal IP, making it only reachable from within the cluster is _____</span></summary>
ClusterIP
<br></details><details>
<summary>The _____ service type&nbsp;maps the Service to the contents of the _____ field (e.g. foo.bar.example.com), by returning a CNAME record.</summary>
ExternalName
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">In order to allow you to choose a port number for your Services, we must ensure that no two Services can collide. Kubernetes does that by allocating each Service its own _____</span></summary>
<span style="color: rgb(34, 34, 34);">IP address.</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">_____ exposes HTTP and HTTPS routes from outside the cluster to services</span><span style="color: rgb(34, 34, 34);">&nbsp;within the cluster. Traffic routing is controlled by rules defined on the _____ resource.</span></summary>
Ingress
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">In some cases, multiple paths within an Ingress will match a request. In those cases precedence will be given first to the _____.&nbsp;</span></summary>
<span style="color: rgb(34, 34, 34);">longest matching path</span>
<br></details><details>
<summary>Ingresses can be implemented by different controllers, often with different configuration. Each Ingress should reference an _____ that contains additional configuration including the name of the controller that should implement it.</summary>
IngressClass&nbsp;
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">You may deploy any number of Ingress controllers</span><span style="color: rgb(34, 34, 34);">&nbsp;within a cluster. When you create an ingress, you should annotate each ingress with the appropriate _____&nbsp;</span><span style="color: rgb(34, 34, 34);">to indicate which ingress controller should be used if more than one exists within your cluster.</span></summary>
ingressClass
<br></details><details>
<summary>Can NetworkPolicies conflict each other?</summary>
No - they are additive.&nbsp;<span style="color: rgb(34, 34, 34);">&nbsp;If any policy or policies select a pod, the pod is restricted to what is allowed by the union of those policies' ingress/egress rules.</span>
<br></details><details>
<summary>By default, a Pod's hosts file includes...</summary>
localhost, hostname and IPv4/IPv6 boilerplates.
<br></details><details>
<summary>Can a Pod have a single IPv4 and IPv6 address assigned?</summary>
Yes - via enabling IPv4/IPv6 dual-stack.
<br></details><details>
<summary>A node's _____ tell an incoming packet where in the node to go.</summary>
iptables
<br></details><details>
<summary>The _____ service type exposes the Service externally using a cloud provider�s load balancer.</summary>
LoadBalancer
<br></details><details>
<summary>The .spec.____ field is a preference-order list of Node labels, which will be used to sort endpoints when accessing this Service. Traffic will be directed to a Node whose value for the first label matches the originating Node's value for that label. If there is no backend for the Service on a matching Node, then the second label will be considered, and so forth, until no labels remain.</summary>
topologyKeys
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">In an Ingress, if two paths are still equally matched by a request, precedence will be given to paths with the _____ path type over _____ path type.</span></summary>
exact
prefix
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">.spec._____&nbsp;</span><span style="color: rgb(34, 34, 34);">adds entries to a Pod's </span>/etc/hosts&nbsp;<span style="color: rgb(34, 34, 34);">file, overriding its hostname resolution when DNS and other options are not applicable.&nbsp;</span></summary>
<span style="color: rgb(34, 34, 34);">HostAliases</span>
<br></details><details>
<summary>What is a Kubernetes Service?</summary>
It's an network connection abstraction which defines a logical set of Pods and a policy to access them.
<br></details><details>
<summary>List possible ServiceTypes for Kubernetes Service</summary>
ClusterIP (default)
NodePort
LoadBalancer
ExternalName
Headless
<br></details><details>
<summary>The LoadBalancer Service creates an external IP address, but itself does not know any Pod IP's. Instead,&nbsp;it chooses a _____ to send packets to.</summary>
Node
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">An EndpointSlice is full</span><span style="color: rgb(34, 34, 34);">&nbsp;once it reaches _____ endpoints (by default), at which point additional EndpointSlices will be created.</span></summary>
<span style="color: rgb(34, 34, 34);">100</span>
<br></details><details>
<summary>Each of a Service's ports can specify the application protocol to use via the _____ field.</summary>
AppProtocol
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">For some Services, you need to expose more than one port. Kubernetes lets you configure multiple port definitions on a Service object. When using multiple ports for a Service, you must give all of your ports _____ so that these are unambiguous.</span></summary>
<span style="color: rgb(34, 34, 34);">names</span>
<br></details><details>
<summary>Inside a Kubernetes cluster, you might wish to reuse an existing DNS entry, or have legacy systems that are configured for a specific IP address and difficult to re-configure. A Service can specify its own cluster IP address by setting the .spec._____ field.</summary>
clusterIP
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Kubernetes supports 2 primary modes of finding a Service. These are...</span></summary>
<span style="color: rgb(34, 34, 34);">DNS and environment variables.</span>
<br></details><details>
<summary>Headless services are created by setting the Service's .spec._____ field to _____</summary>
clusterIP

"None"
<br></details><details>
<summary>To ensure each Service receives a unique IP, an internal allocator atomically updates a global allocation map in _____ prior to creating each Service.</summary>
etcd
<br></details><details>
<summary>_____ enables a service to route traffic based upon the Node topology of the cluster.&nbsp;</summary>
Service Topology
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">An _____&nbsp;</span><span style="color: rgb(34, 34, 34);">is responsible for fulfilling the Ingress, usually with a load balancer, though it may also configure your edge router or additional frontends to help handle the traffic.</span></summary>
Ingress controller
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">An _____ may be configured to give Services externally-reachable URLs, load balance traffic, terminate SSL / TLS, and offer name based virtual hosting.</span></summary>
<span style="color: rgb(34, 34, 34);">Ingress</span>
<br></details><details>
<summary>An Ingress with no rules sends all traffic to a single _____, which is typically a configuration option of the Ingress Controller&nbsp;and is not specified in your Ingress resources. If none of the hosts or paths match the HTTP request in the Ingress objects, the traffic is routed to it.</summary>
default backend
<br></details><details>
<summary>A _____ uses _____ to specify how groups of pods&nbsp;are allowed to communicate with each other and other network endpoints.</summary>
NetworkPolicy&nbsp;
labels
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Once there is any _____ in a namespace selecting a particular pod, that pod will reject any connections that are not allowed by it.</span></summary>
<span style="color: rgb(34, 34, 34);">NetworkPolicy</span>
<br></details><details>
<summary>The kubelet manages the _____ file for each container of a Pod to prevent Docker from modifying it.</summary>
hosts
<br></details><details>
<summary>The Kubernetes LoadBalancer service works on OSI Layer _____</summary>
4
<br></details><details>
<summary>In a LoadBalancer service, the _____ annotation removes the double-hop problem by allowing users to define their own balancing.</summary>
OnlyLocal
<br></details><details>
<summary>Does a Service load balance traffic across multiple Pods?</summary>
Yes
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A Service can specify that traffic be preferentially routed to endpoints that are on the same Node as the client, or in the same availability zone by using _____</span></summary>
Service Topology
<br></details><details>
<summary>Containers within a single pod share network resources - _____ and _____</summary>
IP address and port space
<br></details><details>
<summary>The _____ service type exposes the Service on each Node�s IP at a static port. A ClusterIP Service, to which the it routes, is automatically created.&nbsp;</summary>
NodePort
<br></details><details>
<summary>A _____ is an abstract way to expose on the network an application running on a set of Pods.</summary>
service
<br></details><details>
<summary>A <b>Service </b>can map any incoming port to a _____. By default and for convenience, it has the same value as the port field.</summary>
targetPort
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">_____</span><span style="color: rgb(34, 34, 34);">&nbsp;provide a more scalable alternative to Endpoints, distributing network endpoints across multiple resources.</span></summary>
EndpointSlices
<br></details><details>
<summary>Every node in a Kubernetes cluster runs a _____, responsible for implementing a form of virtual IP for Services of type other than ExternalName.</summary>
kube-proxy
<br></details><details>
<summary>When you don't need load-balancing and a single Service IP, you can create _____</summary>
headless services
<br></details><details>
<summary>A Service for with no ClusterIP, proxying, load-balancing, nor handled by kube-proxy is called _____</summary>
headless
<br></details><details>
<summary>The _____ service type exposes a Service on each Node's IP at a static port.</summary>
NodePort
<br></details><details>
<summary>The _____ service type&nbsp;exposes the Service externally using a cloud provider's load balancer.</summary>
LoadBalancer
<br></details><details>
<summary>You can control Service traffic routing by specifying the .spec._____&nbsp;field.&nbsp;</summary>
topologyKeys&nbsp;
<br></details><details>
<summary>EndpointSlices support three address types:</summary>
IPv4, IPv6, FQDN (Fully Qualified Domain Name)
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">An EndpointSlice's Endpoints can contain labels about its topology information, such as...</span></summary>
Node - kubernetes.io/hostnameZone - topology.kubernetes.io/zoneRegion - topology.kubernetes.io/region
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">You can secure an Ingress by specifying a</span><span style="color: rgb(34, 34, 34);">&nbsp;Secret&nbsp;</span><span style="color: rgb(34, 34, 34);">that contains a TLS _____ and _____.</span></summary>
<span style="color: rgb(34, 34, 34);">private key and certificate</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">An Ingress TLS secret must contain keys named&nbsp;</span><font face="monospace">_____</font><span style="color: rgb(34, 34, 34);">&nbsp;that contain the certificate and private key to use for TLS.</span></summary>
<code>tls.crt</code><span style="color: rgb(34, 34, 34);">&nbsp;and&nbsp;</span><code>tls.key</code>
<br></details><details>
<summary>Are Pods network-isolated?</summary>
<span style="color: rgb(34, 34, 34);">Pods can become isolated by having a <b>NetworkPolicy </b>that selects them. By default, they accept traffic from any source.</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">For TLS, the Ingress object currently only supports the port 443, and assumes TLS _____.&nbsp;</span></summary>
termination
<br></details><details>
<summary>_____ resources route requests to different services, depending on a set of rules, for example, matching parts of the request URL. They can also terminate TLS connections for your application.</summary>
Ingress
<br></details><details>
<summary>The NodePort type is an extension of the _____ type. So a NodePort service also has a _____ address.</summary>
ClusterIP
<br></details><details>
<summary>The LoadBalancer service type is an extension of the _____ type. A LoadBalancer Service has a clusterIP address and one or more _____ values.</summary>
NodePort
<br></details>

## Nodes 

<details>
<summary>_____ allow a node to repel a set of Pods, based on certain properties of the node.</summary>
Taints
<br></details><details>
<summary>A Kubernetes cluster consists of two types of resources...</summary>
Master and Nodes
<br></details><details>
<summary>A _____ is a worker machine in Kubernetes and may be either a virtual or a physical machine, depending on the cluster.&nbsp;</summary>
Node
<br></details><details>
<summary>Is it possible to run DaemonSet pods on only some nodes?</summary>
Yes - with taints and affinities
<br></details><details>
<summary>To prevent a kubelet from self-registering the node in the control-plane, you could pass the _____ flag.</summary>
--register-node=false
<br></details><details>
<summary>A node's <b>DiskPressure </b>is True when...</summary>
The node's disk capacity is low
<br></details><details>
<summary>A Node's <b>MemoryPressure </b>is True when...</summary>
The node's memory is low
<br></details><details>
<summary>A Node's <b>PIDPressure</b>&nbsp;is True when...</summary>
There are too many processes running
<br></details><details>
<summary>A Node's <b>NetworkUnavailable</b>&nbsp;is True when...</summary>
The Node's network is not correctly configured
<br></details><details>
<summary>Node heartbeats are sent by...</summary>
kubelet
<br></details><details>
<summary>A Node's "Ready" status is False when...</summary>
It's unhealthy and not accepting pods
<br></details><details>
<summary>A _____ is a VM or a physical computer that serves as a worker machine in a Kubernetes cluster.</summary>
Node
<br></details><details>
<summary>A node's status contains four domains of information.These are...</summary>
Addresses
Conditions
Capacity and Allocatable
Info
<br></details><details>
<summary>Addresses in a node's status include...</summary>
HostName, InternalIP, ExternalIP
<br></details><details>
<summary>Capacity fields describe the total amount of _____ that a Node has</summary>
resources
<br></details><details>
<summary>The Kubernetes control plane component that manages various aspects of nodes is the...</summary>
Node controller
<br></details><details>
<summary>The three roles of the <b>Node Controller </b>in a Node's life</summary>
CIDR block assignment

Synchronize internal list of nodes
Node health monitoring
<br></details><details>
<summary>Two types of node Heartbeats</summary>
NodeStatus updates
Lease Object
<br></details><details>
<summary>Node <b>Info</b>&nbsp;status field describes general information about a node, such as:</summary>
operating system
node component versions
<br></details><details>
<summary>A Node's "Ready" status is Unknown when...</summary>
40 seconds have passed since the Node Controller has heard from the node
<br></details><details>
<summary>In terms of network, the Node Controller assigns a _____ to a Node upon its registration.</summary>
CIDR block
<br></details><details>
<summary>A Pod always runs on a...</summary>
Node
<br></details><details>
<summary>Each Kubernetes Node is managed by the....</summary>
Master
<br></details><details>
<summary>When a node self-registers to the control plane, which component is responsible?</summary>
kubelet
<br></details><details>
<summary>A node is reachable by the <b>API server </b>but its&nbsp;<b>Ready</b> condition has remained&nbsp;<b>False</b> or <b>Unknown</b> for longer than the <b>kube-controller-manager</b>'s&nbsp;<b>pod-eviction-timeout</b>
What happens to the Pods on the node?</summary>
All Pods on the node are scheduled for deletion by the node controller
<br></details><details>
<summary>Allocatable describes the amount of the Node's resources that are _____</summary>
available to be consumed by Pods
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Topology spread constraints rely on _____ to&nbsp;</span><span style="color: rgb(34, 34, 34);">identify the topology domain(s) that each Node is in.</span></summary>
node labels
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">If an incoming Pod has&nbsp;</span><code>spec.nodeSelector</code><span style="color: rgb(34, 34, 34);">&nbsp;or&nbsp;</span><code>spec.affinity.nodeAffinity</code><span style="color: rgb(34, 34, 34);">&nbsp;defined, nodes not matching them will be...</span></summary>
bypassed
<br></details><details>
<summary>A Node's "Ready" status is True when...</summary>
It's healthy and accepts pods
<br></details><details>
<summary>_____ are a way of tagging nodes with specific information; usually, about node problems or failures. By default, Pods won�t be scheduled on nodes with them.</summary>
Taints
<br></details><details>
<summary>The kubernetes components inside a worker node are...</summary>
kubelet, kube-proxy, container runtime
<br></details><details>
<summary>_____ allow a Pod to be scheduled on nodes with a specific taint. You can use this mechanism to run certain Pods only on dedicated nodes.</summary>
Tolerations
<br></details><details>
<summary>Pod _____ express a preference for Pods to be scheduled on the same node as other Pods, when they benefit from it.</summary>
affinities
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">If two Nodes are labelled with one&nbsp;<b>topologyKey&nbsp;</b>and have identical values for that label, the scheduler&nbsp;</span><span style="color: rgb(34, 34, 34);">tries to place a _____ number of Pods into each topology domain</span></summary>
balanced
<br></details><details>
<summary><strong>topologyKey</strong><span style="color: rgb(34, 34, 34);">&nbsp;is...</span></summary>
<span style="color: rgb(34, 34, 34);">The key of node labels.&nbsp;</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">If two Nodes are labelled with one&nbsp;<b>topologyKey&nbsp;</b>and have identical values for that label, the scheduler treats both Nodes as being in the same _____&nbsp;</span></summary>
<span style="color: rgb(34, 34, 34);">topology&nbsp;</span>
<br></details><details>
<summary>_____ attract or repel Pods to or from nodes with specified attributes. For example, you can specify that a Pod can only run on a node in a specified availability zone.</summary>
Node affinities
<br></details><details>
<summary>While _____ can block a Pod from running on a node, _____ are more like suggestions to the scheduler. You can combine multiple, with different weights.</summary>
hard node affinities
soft node affinities
<br></details>

## Pods 

<details>
<summary>The three available ImagePullPolicies of a container, are...</summary>
Always, Never, IfNotPresent (default)
<br></details><details>
<summary>What is DaemonSet?</summary>
A Kubernetes&nbsp;<b>Controller&nbsp;</b>which ensures that all (or some)&nbsp;<b>Nodes run a copy of a Pod.
</b>
<br></details><details>
<summary>What will happen to ReplicaSet pods inside a node when that node gets deleted?</summary>
These pods will be replaced on another node, or nodes.
<br></details><details>
<summary>Like a Deployment, a StatefulSet manages Pods that are based on an identical container spec. Unlike a Deployment, a StatefulSet maintains a _____ for each of their Pods</summary>
sticky identity
<br></details><details>
<summary>An application requires several of the following:<ul><li>Stable, unique network identifiers.</li><li>Stable, persistent storage.</li><li>Ordered, graceful deployment and scaling.</li><li>Ordered, automated rolling updates.</li></ul>Which workload object could work best?</summary>
StatefulSet
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Will deleting or scaling a StatefulSet down also delete&nbsp;</span><span style="color: rgb(34, 34, 34);">the volumes associated with it?</span></summary>
No
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A ReplicaSet is linked to its Pods via their _____ field.</span><span style="color: rgb(34, 34, 34);">&nbsp;It's through this link that the ReplicaSet knows of the state of the Pods it is maintaining and plans accordingly.</span></summary>
metadata.ownerReferences
<br></details><details>
<summary>_____&nbsp;<span style="color: rgb(34, 34, 34);">is an object which can own ReplicaSets and update them and their Pods via declarative, server-side rolling updates.</span></summary>
Deployment
<br></details><details>
<summary>Is running a logs collection daemon on every node a valid DaemonSet use case?</summary>
Yes
<br></details><details>
<summary>Can you perform a rolling update on a DaemonSet?</summary>
Yes
<br></details><details>
<summary>The _____ ensures a specific number of pod replicas are running at any one time across nodes</summary>
replication controller
<br></details><details>
<summary>A Kubernetes concept that represents the smallest unit of deployment.</summary>
Pod
<br></details><details>
<summary>Can a Pod can opt out of being modified by PodPresets altogether?</summary>
Yes - via the exclude annotation <b>podpreset.admission.kubernetes.io/exclude: "true"</b>
<br></details><details>
<summary>Containers within a single pod share ____ and _____ resources.</summary>
storage and network
<br></details><details>
<summary>The number of old ReplicaSets to retain for rollback is defined in a deployment's .spec._____</summary>
revisionHistoryLimit
<br></details><details>
<summary>Ready, ContainerReady, lastProbeTime, reason. These are the types of latest variable observations of an object's state called _____, used when the details of an observation are not known apriori, or would not apply to all instances of a given Kind.</summary>
Conditions
<br></details><details>
<summary>StatefulSet manages the deployment and scaling of a set of Pods,&nbsp;and provides guarantees about the _____ and _____of these Pods</summary>
ordering and uniqueness
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">If an application doesn't require any stable identifiers or ordered deployment, deletion, or scaling, you should deploy your application using...</span></summary>
<b>Deployments&nbsp;</b>or<b> Replicasets </b>-<span style="color: rgb(34, 34, 34);">&nbsp;workload objects that provide a set of stateless replicas.</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A ReplicaSet identifies new Pods to acquire by using its _____.&nbsp;</span><span style="color: rgb(34, 34, 34);">&nbsp;If there is a Pod that has no OwnerReference or the Ow</span>nerReference is not a&nbsp;<a href="https://kubernetes.io/docs/concepts/architecture/controller/">Controller</a>&nbsp;an<span style="color: rgb(34, 34, 34);">d the _____ matches, it will be immediately acquired by said ReplicaSet.</span></summary>
selector
<br></details><details>
<summary>Is running a cluster storage daemon on every node a valid DaemonSet use case?</summary>
Yes
<br></details><details>
<summary>Pods waiting to be scheduled are usually created in <b>Pending </b>state. Are DaemonSet pods created in <b>Pending </b>state?</summary>
No - it is an inconsistency due to being scheduled by the DaemonSet controller.
<br></details><details>
<summary>When <b>Pod preemption</b> is enabled, does the DaemonSet controller consider <b>pod priority</b> and <b>preemption </b>when making scheduling decisions?</summary>
No - <b>Pod preemption</b> is handled by the <b>default scheduler</b>, DaemonSet pods are scheduled by the <b>DaemonSet controller</b>.
<br></details><details>
<summary>If node labels are changed, the DaemonSet will _____ Pods to newly matching nodes.</summary>
Add
<br></details><details>
<summary>If node labels are changed, the DaemonSet will _____ Pods from newly not-matching nodes.</summary>
Delete
<br></details><details>
<summary>The role of the Kubernetes garbage collector is to delete certain objects that once had _____, but no longer have one.</summary>
an owner
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">When you delete an object, you can specify whether the object's dependents are also deleted automatically. Deleting dependents automatically is called a&nbsp;<i>_____ </i>deletion.</span></summary>
cascading
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">If you create a DaemonSet with the same selector as Pods that belonged to a matching DaemonSet, what will the new DaemonSet do with the Pods?</span></summary>
adopt them
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A </span><i>_____&nbsp;</i><span style="color: rgb(34, 34, 34);">ensures that all (or some) Nodes run a copy of a Pod.</span></summary>
DaemonSet
<br></details><details>
<summary>A _____ is an API resource for injecting additional runtime requirements into a label-selected Pod at creation time.</summary>
Pod Preset
<br></details><details>
<summary>What�s a <b>Pod</b></summary>
A logical group of containers with shared network and storage, and a specification for how to run.
<br></details><details>
<summary>What will happen (by default) to DaemonSet pods inside a node when that node gets deleted?</summary>
These pods will be garbage collected
<br></details><details>
<summary>Are containers in a Pod automatically co-located and co-scheduled on the same node?</summary>
Yes
<br></details><details>
<summary>Can a pod's containers share resources, dependencies, communicate with each other and coordinate their lifecycle?</summary>
Yes
<br></details><details>
<summary>The <b>phase </b>of a pod is...</summary>
A high-level summary of where the pod is in its lifecycle
<br></details><details>
<summary><table><tbody><tr><td>The Pod has been bound to a node, and all of the Containers have been created. At least one Container is still running, or is in the process of starting or restarting. This is the _____ phase of a Pod's lifecycle.</td></tr></tbody></table></summary>
Running
<br></details><details>
<summary>List all 5 Pod <b>phases</b></summary>
Pending
Running
Succeeded
Failed
Unknown
<br></details><details>
<summary>List all six fields in a <b>PodCondition</b></summary>
reason
status
message
type
lastProbeTime
lastTransitionTime
<br></details><details>
<summary>The <b>reason&nbsp;</b>condition field provides...</summary>
a unique, one-word reason for the condition's last transition.
<br></details><details>
<summary>The four possible values of the&nbsp;<b>type</b>&nbsp;condition field are...</summary>
<b>PodScheduled</b>
<b>Ready</b>
<b>Initialized</b>
<b>ContainersReady</b>
<br></details><details>
<summary>If the readinessProbe fails, what happens?</summary>
The Pod's IP address&nbsp;is removed from the endpoints of all <b>Services </b>that match the Pod.
<br></details><details>
<summary>If the startupProbe fails, the container...</summary>
is killed by the kubelet, then subjected to the container's <b>restart policy</b>.
<br></details><details>
<summary>A container should be killed or restarted if a probe fails. What can be done to achieve this?</summary>
1. Specify a <b>livenessProbe&nbsp;</b>
2. Add a <b>restartPolicy </b>of <b>Always </b>or <b>OnFailure</b>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A Container should be able to take itself down for maintenance. What can achieve this?</span></summary>
A <b>readinessProbe </b>that checks an endpoints specific to readiness that is different from the liveness probe.
<br></details><details>
<summary>The three possible states of containers are...</summary>
Waiting
Running
Terminated
<br></details><details>
<summary>To find out why a container is in&nbsp;<b>Waiting </b>state, you can check its state's <b>_____&nbsp;</b>field</summary>
Reason
<br></details><details>
<summary>The _____ hook is executed prior to a container entering its <b>Running </b>state.</summary>
postStart
<br></details><details>
<summary>Once bound to a node, will a Pod ever rebound to another node?</summary>
No
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">You use _____</span><span style="color: rgb(34, 34, 34);">&nbsp;to specify the Pods to which a given PodPreset applies.</span></summary>
label selectors
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">When a pod creation request occurs, the system does the following:</span></summary>
<ol><li>Retrieve all&nbsp;<code>PodPresets</code>&nbsp;available for use.</li><li>Check if the label selectors of any&nbsp;<code>PodPreset</code>&nbsp;matches the labels on the pod being created.</li><li>Attempt to merge the various resources defined by the&nbsp;<code>PodPreset</code>&nbsp;into the Pod being created.</li><li>On error, throw an event documenting the merge error on the pod, and create the pod&nbsp;<em>without</em>&nbsp;any injected resources from the&nbsp;<code>PodPreset</code>.</li><li>Annotate the resulting modified Pod spec to indicate that it has been modified by a&nbsp;<code>PodPreset</code>. The annotation is of the form&nbsp;<code>podpreset.admission.kubernetes.io/podpreset-&lt;pod-preset name&gt;: "&lt;resource version&gt;"</code>.</li></ol>
<br></details><details>
<summary>The annotation to&nbsp;disable PodPreset for a Specific Pod is...</summary>
podpreset.admission.kubernetes.io/exclude: "true"
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">If set, a cluster's default topology spread constraints are applied to a Pod if, and only if:</span></summary>
<ul><li>It doesn't define any constraints in its&nbsp;<code>.spec.topologySpreadConstraints</code>.</li><li>It belongs to a service, replication controller, replica set or stateful set.</li></ul>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A _____ limits the number of pods of a replicated application that are down simultaneously from voluntary disruptions.</span></summary>
PodDisruptionBudget
<br></details><details>
<summary>Do ephemeral containers guarantee execution?</summary>
No
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">If you want to use <b>storage volumes</b> to provide persistence for your workload, you can use a _____. Although its Pods are susceptible to failure, the persistent <b>Pod identifiers</b> make it easier to <b>match existing volumes</b> to the new Pods that replace any that have failed.</span></summary>
<span style="color: rgb(34, 34, 34);">StatefulSet&nbsp;</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">StatefulSets currently require manually creating a _____</span><span style="color: rgb(34, 34, 34);">&nbsp;to be responsible for the network identity of the Pods.</span></summary>
headless service
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">StatefulSets do not provide any guarantees on the termination of pods when a StatefulSet is deleted.&nbsp;</span><span style="color: rgb(34, 34, 34);">
</span><span style="color: rgb(34, 34, 34);">To achieve ordered and graceful termination of the pods in the StatefulSet, it is possible to...</span></summary>
<span style="color: rgb(34, 34, 34);">scale the StatefulSet down to 0 prior to deletion</span>
<br></details><details>
<summary>Is running a node monitoring daemon on every node a valid DaemonSet use case?</summary>
Yes
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Normally, the node that a Pod runs on is selected by the Kubernetes scheduler. However, DaemonSet pods are created and scheduled by _____ instead.</span></summary>
<span style="color: rgb(34, 34, 34);">the DaemonSet controller</span>
<br></details><details>
<summary>DaemonSets are similar to Deployments in that they both...</summary>
<span style="color: rgb(34, 34, 34);">create Pods, with processes which are not expected to terminate (web servers, storage servers etc).</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Every dependent (i.e. owned) object has a metadata.</span><font face="monospace">_____</font><span style="color: rgb(34, 34, 34);">&nbsp;field that points to the owning object. The owning object is usually a&nbsp;</span><span style="color: rgb(34, 34, 34);">Job, CronJob,&nbsp;</span><span style="color: rgb(34, 34, 34);">Deployment, DaemonSet,&nbsp;</span><span style="color: rgb(34, 34, 34);">StatefulSet,</span><span style="color: rgb(34, 34, 34);">&nbsp;ReplicationController, ReplicaSet.</span></summary>
ownerReferences
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">You can specify relationships between an owner and dependents by manually setting their .metadata._____ field</span></summary>
ownerReference
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">In _____</span><span style="color: rgb(34, 34, 34);">, Kubernetes deletes the owner object immediately and the garbage collector then deletes the dependents in the background.</span></summary>
background cascading deletion
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">In </span><i>_____</i><span style="color: rgb(34, 34, 34);">, the root object first enters a "deletion in progress" state.&nbsp;</span>Once the "deletion in progress" state is set, the garbage collector deletes the object's dependents. Once the garbage collector has deleted all dependents,&nbsp;it deletes the owner object.</summary>
foreground cascading deletion
<br></details><details>
<summary>To control the cascading deletion policy, set the <font face="monospace">_____&nbsp;</font>field on the <font face="monospace">_____&nbsp;</font>argument when deleting an Object.&nbsp;</summary>
<code>propagationPolicy</code>&nbsp;
<code>deleteOptions</code>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">If a Pod cannot be scheduled, the scheduler tries to preempt (evict) lower _____ Pods to make scheduling of the pending Pod possible.</span></summary>
<span style="color: rgb(34, 34, 34);">priority</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A _____ is a non-namespaced object that defines a mapping from a priority class name to the integer value of the priority.</span></summary>
<span style="color: rgb(34, 34, 34);">PriorityClass</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A</span><span style="color: rgb(34, 34, 34);">&nbsp;data science workload</span><span style="color: rgb(34, 34, 34);">&nbsp;may need to be prioritized above others, though without discarding existing work via pre-emption. To ensure this job begins once cluster resources become free, you could set...</span></summary>
PreemptionPolicy: Never
<br></details><details>
<summary>Identical Pods in a deployment are referred to as...</summary>
Replicas
<br></details><details>
<summary>_____ optimize a given metric (e.g. CPU utilization) across a set of Pods. They increase or decrease the number of replicas to achieve it.</summary>
Horizontal Pod Autoscalers (HPA)
<br></details><details>
<summary>A pod's only container exits with&nbsp;<b>success</b>. What happens if the&nbsp;<b>restartPolicy&nbsp;</b>is&nbsp;<b>Always?</b></summary>
Restart Container; Pod&nbsp;<code>phase</code>&nbsp;stays <b>Running</b>.
<br></details><details>
<summary>A pod's only container exits with&nbsp;<b>failure</b>. What happens if the&nbsp;<b>restartPolicy&nbsp;</b>is&nbsp;<b>Always</b>?</summary>
Restart Container; Pod&nbsp;<code>phase</code>&nbsp;stays Running.
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A _____ allows pod template authors to not have to explicitly provide all information for every pod.&nbsp;</span></summary>
<span style="color: rgb(34, 34, 34);">PodPreset</span>
<br></details><details>
<summary>From one container, how could you view processes in other containers?</summary>
Enable process namespace sharing
<br></details><details>
<summary>_____ restrict the scheduler�s freedom, trading off one application against another.&nbsp;</summary>
Pod affinities
<br></details><details>
<summary>Do pods run a single container each?</summary>
Not necessarily. They can run multiple containers.
<br></details><details>
<summary>Do Pods each have a unique IP address?</summary>
Yes, for each address family
<br></details><details>
<summary><b>Failed </b>phase</summary>
<table><tbody><tr><td>All Containers in the Pod have terminated, and at least one Container has terminated in failure. That is, the Container either exited with non-zero status or was terminated by the system.</td></tr><tr></tr></tbody></table>
<br></details><details>
<summary><b>Unknown </b>phase</summary>
For some reason the state of the Pod could not be obtained, typically due to an error in communicating with the host of the Pod.
<br></details><details>
<summary>The&nbsp;<b>lastTransitionTime</b>&nbsp;condition field provides...</summary>
a timestamp for when the Pod last transitioned from one status to another.
<br></details><details>
<summary>The three possible values for the&nbsp;<b>status</b>&nbsp;Pod condition field are...</summary>
<b>"True"</b>
<b>
</b><b>"False"</b><b>
</b>"<b>Unknown"</b>
<br></details><details>
<summary>A probe can have one of three results:</summary>
<b>Success</b>The Container passed the diagnostic
<b>
</b><b>Failure</b>The Container failed the diagnostic<b>
</b><b>Unknown</b>The diagnostic failed, so no action should be taken
<br></details><details>
<summary>If a livenessProbe fails, the container...</summary>
is killed by the kubelet, then subjected to the container's <b>restart policy</b>.
<br></details><details>
<summary>A container does not provide a livenessProbe, a readinessProbe nor a startupProbe
What will be the state of each probe of the container?</summary>
<b>Success </b>on all of them
<br></details><details>
<summary>readinessProbe indicates whether...</summary>
a container is ready to service requests.
<br></details><details>
<summary>A container's default readiness state before the initial delay is...</summary>
Failure
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A process in your Container is able to crash on its own whenever it encounters an issue or becomes unhealthy.&nbsp;</span><span style="color: rgb(34, 34, 34);">
</span><span style="color: rgb(34, 34, 34);">Do you still need a livenessProbe?</span></summary>
Not necessarily.&nbsp;
<span style="color: rgb(34, 34, 34);">The kubelet will automatically perform the correct action in accordance with the Pod's&nbsp;</span><code>restartPolicy</code><span style="color: rgb(34, 34, 34);">.</span>
<br></details><details>
<summary>A container is in the <b>_____&nbsp;</b>state when it has successfully or unsuccessfully completed execution.</summary>
Terminated
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Inject extra feedback or signals into PodStatus via...</span></summary>
<b>Pod readiness</b>
<br></details><details>
<summary>Default restartPolicy is...</summary>
Always
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Exited Containers that are restarted by the kubelet are restarted with an _____ delay capped at 5 minutes, and is reset after ten minutes of successful execution.</span></summary>
exponential back-off
<br></details><details>
<summary>A pod's only container exits with&nbsp;<b>failure</b>. What happens if the&nbsp;<b>restartPolicy </b>is <b>Never</b>?</summary>
Pod phase becomes Failed.
<br></details><details>
<summary>What applies Pod Presets to incoming pod creation requests?</summary>
PodPreset admission controller
<br></details><details>
<summary>The degree to which Pods may be unevenly distributed, i.e. t<span style="color: rgb(34, 34, 34);">he maximum permitted difference between the number of matching Pods in any two topology domains of a given topology type is called...</span></summary>
<strong>maxSkew</strong>
<br></details><details>
<summary><b>whenUnsatisfiable </b>possible values:</summary>
<b><code>DoNotSchedule</code><span style="color: rgb(34, 34, 34);">&nbsp;</span><span style="color: rgb(34, 34, 34);">
</span></b><span style="color: rgb(34, 34, 34);">tells the scheduler not to schedule it.</span><span style="color: rgb(34, 34, 34);">
</span><span style="color: rgb(34, 34, 34);">
</span><b><code>ScheduleAnyway</code><span style="color: rgb(34, 34, 34);">&nbsp;</span></b><span style="color: rgb(34, 34, 34);">
</span><span style="color: rgb(34, 34, 34);">tells the scheduler to still schedule it while prioritizing nodes that minimize the skew</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A Deployment&nbsp;</span><span style="color: rgb(34, 34, 34);">is supposed to have 5 pods at any given time, with</span><span style="color: rgb(34, 34, 34);">&nbsp;</span><code>.spec.replicas: 5.&nbsp;</code><span style="color: rgb(34, 34, 34);">If a PodDisruptionBudget allows for there to be 4 at a time, then how many pods at a time are allowed to be voluntarily disrupted by the Eviction API?</span></summary>
<span style="color: rgb(34, 34, 34);">One</span>
<br></details><details>
<summary>PodDisruptionBudgets cannot prevent involuntary disruptions from occurring. Do involuntary disruptions count against the budget?</summary>
No
<br></details><details>
<summary>Are controllers (like deployment or statefulset) limited by PDBs when doing rolling updates?</summary>
<b>No!&nbsp;</b><span style="color: rgb(34, 34, 34);">The handling of failures during application updates is configured in the controller spec.</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">When a pod is evicted using the eviction API, is it gracefully terminated?</span></summary>
Yes
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A temporary ephemeral container is ran in an existing Pod&nbsp;</span><span style="color: rgb(34, 34, 34);">to accomplish user-initiated actions such as..</span></summary>
Troubleshooting and inspecting services
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">To troubleshoot a hard-to-reproduce bug, you might need to inspect the state of an existing Pod and its containers, or run some arbitrary commands. In these cases you can run _____&nbsp;</span><span style="color: rgb(34, 34, 34);">inside an existing Pod.</span></summary>
<span style="color: rgb(34, 34, 34);">an ephemeral container</span>
<br></details><details>
<summary>Do ephemeral containers have guaranteed resources?</summary>
No
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">When using ephemeral containers, it's helpful to enable _____&nbsp;</span>so you can view processes in other containers.</summary>
process namespace sharing
<br></details><details>
<summary>When deleting a DaemonSet with kubectl, you can specify the flag _____, then the Pods will remain on the nodes.&nbsp;</summary>
--cascade=false
<br></details><details>
<summary>Given that you can start daemon processes on a node directly via systemd, why use a DaemonSet?</summary>
<ul><li>Ability to monitor and manage logs for daemons in the same way as applications.</li><li>Same config language and tools (e.g. Pod templates,&nbsp;<code>kubectl</code>) for daemons and applications.</li><li>Running daemons in containers with resource limits increases isolation between daemons from app containers. However, this can also be accomplished by running the daemons in a container but not in a Pod (e.g. start directly via Docker).</li></ul>
<br></details><details>
<summary>If you delete an object without deleting its dependents automatically, the dependents are said to become&nbsp;<i>_____</i></summary>
orphaned
<br></details><details>
<summary>Cascading deletion types</summary>
"Orphan", "Foreground", or "Background"
<br></details><details>
<summary>PodPresets cannot be used to override a Pod�s own configuration, only to fill in settings which the Pod itself _____</summary>
&nbsp;hasn't specified.
<br></details><details>
<summary>_____ allow you to schedule one copy of a Pod on every node (for example, a logging agent).</summary>
DaemonSets
<br></details><details>
<summary>_____ can inject bits of common configuration into all selected Pods at creation time. For example, you could use it to mount a particular Volume on all matching Pods.</summary>
PodPresets&nbsp;
<br></details><details>
<summary>_____ start and stop Pod replicas in a specific numbered sequence, allowing you to address each by a predictable DNS name. This is ideal for clustered applications, such as databases.</summary>
StatefulSets&nbsp;
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A quorum-based application must ensure that the number of running replicas is never brought below the minimum required for a quorum. This can be achieved with a _____</span></summary>
PodDisruptionBudget
<br></details><details>
<summary>A pod represents _____ running in your cluster.</summary>
Processes
<br></details><details>
<summary>In terms of Docker constructs, a Pod is modelled as a group of Docker containers with shared _____ and shared _____</summary>
namespaces
filesystem volumes
<br></details><details>
<summary>A container can be set to run in privileged mode to allow Linux capabilities inside the container, such as...</summary>
device accessvolume plugin developmentnetwork plugin development and stack manipulation
<br></details><details>
<summary><table><tbody><tr><td>A Pod has been accepted by the Kubernetes system, but one or more of the Container images has not been created, either still being scheduled or download images. This describes a Pod's _____ phase.</td></tr></tbody></table></summary>
Pending
<br></details><details>
<summary><b>Succeeded </b>phase</summary>
<table><tbody><tr><td>All Containers in the Pod have terminated in success, and will not be restarted.</td></tr><tr></tr></tbody></table>
<br></details><details>
<summary>The <b>lastProbeTime</b>&nbsp;condition field provides...</summary>
A timestamp for when the Pod condition was last probed.
<br></details><details>
<summary>The <b>message&nbsp;</b>condition field provides...</summary>
a human-readable message indicating details about the transition from one status to another.
<br></details><details>
<summary>A livenessProbe indicates whether a container is...</summary>
running
<br></details><details>
<summary>startupProbe indicates whether...</summary>
the application in the container has started.
<br></details><details>
<summary>All other probes are disabled until _____ succeeds.</summary>
startupProbe
<br></details><details>
<summary>A Pod should only be sent traffic when a probe succeeds. What can achieve this?</summary>
readinessProbe
<br></details><details>
<summary>A container is <b>_____&nbsp;</b>when it is neither&nbsp;<b>Running&nbsp;</b>or&nbsp;<b>Terminated</b>. It is likely pulling images, applying secrets etc.</summary>
Waiting
<br></details><details>
<summary>A container is in the <b>_____&nbsp;</b>state when it is executing without issues.</summary>
Running
<br></details><details>
<summary>To tell why a container is in <b>Terminated </b>state, check its state's&nbsp;<b>_____&nbsp;</b>and&nbsp;<b>_____&nbsp;</b>fields.</summary>
Reason and Exit Code
<br></details><details>
<summary>The _____ hook is executed before a container enters Terminated state.</summary>
preStop
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Readiness gates are determined by the current state of the .status._____ fields for the Pod.&nbsp;</span>If such a field isn't found, the status of the condition defaults to&nbsp;<b>"False"</b></summary>
conditions
<br></details><details>
<summary><b>restartPolicy </b>possible values are...</summary>
Always
Never
OnFailure
<br></details><details>
<summary>Does a Pod's <b>restartPolicy </b>apply to all its containers?</summary>
Yes
<br></details><details>
<summary>Does<code> restartPolicy</code><span style="color: rgb(34, 34, 34);">&nbsp;only refer to restarts of the Containers by the kubelet on the same node?</span></summary>
Yes
<br></details><details>
<summary>A pod's only container exits with <b>success</b>. What happens if the&nbsp;<b>restartPolicy </b>is <b>Never?</b></summary>
Pod&nbsp;<code>phase</code>&nbsp;becomes&nbsp;<b>Succeeded</b>.
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">PodPresets are objects for injecting&nbsp;</span><span style="color: rgb(34, 34, 34);">additional runtime requirements&nbsp;</span><span style="color: rgb(34, 34, 34);">into pods at _____</span></summary>
creation time
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">&nbsp;When a&nbsp;</span><code>PodPreset</code><span style="color: rgb(34, 34, 34);">&nbsp;is applied to one or more Pods, Kubernetes modifies their _____</span></summary>
<span style="color: rgb(34, 34, 34);">PodSpec</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">For changes to&nbsp;</span><code>Env</code><span style="color: rgb(34, 34, 34);">,&nbsp;</span><code>EnvFrom</code><span style="color: rgb(34, 34, 34);">, and&nbsp;</span><code>VolumeMounts</code><span style="color: rgb(34, 34, 34);">, Kubernetes modifies _____</span></summary>
<span style="color: rgb(34, 34, 34);">The pod's individual container specs</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">You can use </span><i>_____</i><span style="color: rgb(34, 34, 34);">&nbsp;to control&nbsp;</span><span style="color: rgb(34, 34, 34);">how Pods</span><span style="color: rgb(34, 34, 34);">&nbsp;are spread across your cluster among failure-domains&nbsp;</span><span style="color: rgb(34, 34, 34);">(regions, zones, nodes or user-defined domains).</span></summary>
topology spread constraints
<br></details><details>
<summary>You have a 4-node cluster with the following labels:<pre><code>NAME    STATUS   ROLES    AGE     VERSION   LABELS
node1   Ready    &lt;none&gt;   4m26s   v1.16.0   node=node1,zone=zoneA
node2   Ready    &lt;none&gt;   3m58s   v1.16.0   node=node2,zone=zoneA
node3   Ready    &lt;none&gt;   3m17s   v1.16.0   node=node3,zone=zoneB
node4   Ready    &lt;none&gt;   2m43s   v1.16.0   node=node4,zone=zoneB</code></pre>What would the cluster logically look like?</summary>
<pre><code>+---------------+---------------+
|     zoneA     |     zoneB     |
+-------+-------+-------+-------+
| node1 | node2 | node3 | node4 |
+-------+-------+-------+-------+</code></pre>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">How to deal with a Pod if it doesn't satisfy the topology spread constraint is indicated in the _____ field.</span></summary>
<strong>whenUnsatisfiable</strong>
<br></details><details>
<summary>Does deleting deployments or pods bypass PodDisruptionBudgets?</summary>
Yes
<br></details><details>
<summary>A PodDisruptionBudget&nbsp;<span style="color: rgb(34, 34, 34);">specifies the number of _____ that an application can tolerate having, relative to how many it is intended to have.</span></summary>
replicas
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Do Pods which are deleted or unavailable due to a rolling upgrade to an application count against the disruption budget?</span></summary>
Yes
<br></details><details>
<summary>Will an ephemeral container ever be automatically restarted?</summary>
No
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">_____ indicates the importance of a Pod relative to other Pods.</span></summary>
<span style="color: rgb(34, 34, 34);">Priority</span>
<br></details><details>
<summary>A malicious user could create Pods at the highest possible priorities, causing other Pods to be evicted/not get scheduled. An administrator can use _____ to prevent users from creating pods at high priorities.</summary>
ResourceQuota
<br></details><details>
<summary>Critical pods rely on scheduler _____ to be scheduled when a cluster is under resource pressure.</summary>
preemption
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">The </span><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">field indicates that the value of this PriorityClass should be used for Pods without a&nbsp;</span><code>priorityClassName</code><span style="color: rgb(34, 34, 34);">.&nbsp;</span><span style="color: rgb(34, 34, 34);">Only one such PriorityClass </span><span style="color: rgb(34, 34, 34);">can exist in the system.</span></summary>
<code>globalDefault</code>
<br></details><details>
<summary>Pods with PreemptionPolicy:<font face="monospace">_____</font>&nbsp;will be placed in the scheduling queue ahead of lower-priority pods, but they cannot preempt other pods. It will stay in the scheduling queue, until sufficient resources are free.&nbsp;</summary>
Never
<br></details><details>
<summary><code>PreemptionPolicy</code><span style="color: rgb(34, 34, 34);">&nbsp;defaults to&nbsp;</span><font face="monospace">_____</font><span style="color: rgb(34, 34, 34);">, which will allow pods of that PriorityClass to preempt lower-priority pods (as is existing default behavior).&nbsp;</span></summary>
PreemptLowerPriority
<br></details><details>
<summary>_____ repel other Pods instead of attracting. Ex.: One to replicas of the same Pod can help spread your replicas evenly across the cluster.</summary>
anti-affinity
<br></details><details>
<summary>A pod's only container exits with&nbsp;<b>success</b>. What happens if the&nbsp;<b>restartPolicy&nbsp;</b>is&nbsp;<b>OnFailure?</b></summary>
Pod&nbsp;<code>phase</code>&nbsp;becomes Succeeded.
<br></details><details>
<summary>A pod's only container exits with&nbsp;<b>failure</b>. What happens if the&nbsp;<b>restartPolicy&nbsp;</b>is&nbsp;<b>OnFailure</b>?</summary>
Restart Container; Pod&nbsp;<code>phase</code>&nbsp;stays Running.
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A web front end might want to ensure that the number of replicas serving load never falls below a certain percentage of the total. This can be achieved via a _____</span></summary>
PodDisruptionBudget
<br></details><details>
<summary>If non-preempting pods cannot be scheduled at a given time, they will be retried with lower frequency, allowing other pods with lower priority to be scheduled before them. This is because non-preempting pods are subject to scheduler...</summary>
back-off
<br></details>

## Security 

<details>
<summary>A _____ contains a set of additive RBAC permissions</summary>
Role / Clusterrole
<br></details><details>
<summary>List some ways to improve Kubernetes security</summary>
Log everything in prod
Alert and apply new CVE fixes
Restrict access to nodes, etcd, sudo
Network segmentation
Resource quotas and policy rules&nbsp;
Secrets as volumes
Containers should be non-root, with read-only filesystems
<br></details><details>
<summary>How can any container in a pod enable privileged mode?</summary>
Using the <b>privileged</b>&nbsp;flag in the security context of the container spec.
<br></details><details>
<summary>The 4C's of Cloud Native security are...</summary>
Cloud, Clusters, Containers, Code
<br></details><details>
<summary>The three PodSecurityPolicy types are:</summary>
Privileged, Restricted, Default
<br></details><details>
<summary>Is there currently an API standard for whether a Pod is considered sandboxed?</summary>
No -&nbsp;<span style="color: rgb(34, 34, 34);">Sandbox Pods may be identified by the use of a sandboxed runtime (such as gVisor or Kata Containers), but there is no standard definition of what a sandboxed runtime is.</span>
<br></details><details>
<summary><i>S</i><span style="color: rgb(34, 34, 34);">ecurity sensitive aspects of pod specification, such as c</span><span style="color: rgb(34, 34, 34);">onditions that a pod must run with in order to be accepted into the system, as well as defaults for the related fields can be stored inside cluster-level resources called _____</span></summary>
PodSecurityPolicy
<br></details><details>
<summary>Some security tools with which clusters can be further protected, are...</summary>
Snyk, Aqua, kata containers
gVisor, AppArmor, seccomp, SELinux
<br></details><details>
<summary>Areas of Concern for Workload Security</summary>
Authentication
RBAC API authorization&nbsp;
Secret and encryption management
Pod security policies
Network policies
TLS
<br></details><details>
<summary>Do security contexts replace Pod Security Policy?</summary>
<span style="color: rgb(34, 34, 34);">Debatable. Numerous means of policy enforcement have arisen that augment or replace the use of PodSecurityPolicy.</span>
<br></details><details>
<summary>What are some tools with which clusters can be audited?</summary>
Sonobuoy
<br></details><details>
<summary>Area of Concern for Container Security</summary>
OS and dependency scanning
Image signing and enforcement
Minimalising user privilege
<br></details><details>
<summary>Security settings for Pods are typically applied by using _____, which<span style="color: rgb(34, 34, 34);">&nbsp;allow for the definition of privilege and access controls on a per-Pod basis.</span></summary>
security contexts
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A </span><i>_____</i><span style="color: rgb(34, 34, 34);">&nbsp;is a cluster-level resource that controls security sensitive aspects of the Pod specification.</span></summary>
Pod Security Policy
<br></details>

## Storage 

<details>
<summary>Is a Volume preserved after its Pod's deletion?</summary>
No
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">To use a volume, a Pod specifies what volumes to provide for the Pod in the _____ field,&nbsp;</span><span style="color: rgb(34, 34, 34);">and where to mount those into Containers in the&nbsp;</span><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">field.</span></summary>
.spec.volumes
<code>.spec.containers[*].volumeMounts</code><span style="color: rgb(34, 34, 34);">&nbsp;</span>
<br></details><details>
<summary>Can Volumes have hard links to other Volumes?</summary>
No
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A </span><i>_____&nbsp;</i><span style="color: rgb(34, 34, 34);">is a piece of storage in the cluster that has been provisioned by an administrator or dynamically provisioned using&nbsp;Storage Classes.</span><span style="color: rgb(34, 34, 34);">&nbsp;It is a resource in the cluster just like a node is a cluster resource.&nbsp;</span></summary>
PersistentVolume&nbsp;
<br></details><details>
<summary>A <i>_____&nbsp;</i>is a request for storage by a user.&nbsp;</summary>
PersistentVolumeClaim&nbsp;
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">In _____ provisioning, a cluster administrator creates a number of PVs. They carry the details of the real storage, which is available for use by cluster users. They exist in the Kubernetes API and are available for consumption.</span></summary>
static
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A cluster provisioned with many 50Gi PVs. A PVC requests 100Gi. What happens?</span></summary>
<span style="color: rgb(34, 34, 34);">The claim remains unbound.&nbsp;</span><span style="color: rgb(34, 34, 34);">The PVC can be bound when a 100Gi PV is added to the cluster.</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">If a user deletes a PVC in active use by a Pod, the PVC is...</span></summary>
<span style="color: rgb(34, 34, 34);">not removed immediately.</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">PVC removal is postponed until _____</span></summary>
<span style="color: rgb(34, 34, 34);">the PVC is no longer actively used by any Pods.</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">&nbsp;PV removal is postponed until...</span></summary>
<span style="color: rgb(34, 34, 34);">&nbsp;the PV is no longer bound to a PVC.</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">You can see that a PV or a PVC is protected when its status is </span><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">and the&nbsp;</span><code>Finalizers</code><span style="color: rgb(34, 34, 34);">&nbsp;list includes&nbsp;<font face="monospace">_____</font></span></summary>
<code>Terminating</code><span style="color: rgb(34, 34, 34);">&nbsp;</span><span style="color: rgb(34, 34, 34);">
</span><code>kubernetes.io/pvc-protection</code><span style="color: rgb(34, 34, 34);">
</span>
<br></details><details>
<summary>Generally, a PV will have a specific storage capacity. This is set using the PV's <font face="monospace">_____&nbsp;</font>attribute.</summary>
<code>capacity</code>&nbsp;
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">You can set the value of&nbsp;</span><code>volumeMode</code><span style="color: rgb(34, 34, 34);">&nbsp;to&nbsp;</span><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">to use a volume as a raw block device. Such volume is presented into a Pod as a block device, without any filesystem on it. This mode is useful to provide a Pod the fastest possible way to access a volume, without any filesystem layer between the Pod and the volume. On the other hand, the application running in the Pod must know how to handle a raw block device.</span></summary>
<code>Block</code>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">ReadOnlyMany&nbsp;</span></summary>
<span style="color: rgb(34, 34, 34);">the volume can be mounted read-only by many nodes</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A volume is said to be _____ when the</span>&nbsp;volume has failed its automatic reclamation.</summary>
Failed
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">PersistentVolumes binds are exclusive, and since PersistentVolumeClaims are namespaced objects, mounting claims with "Many" modes (</span><code>ROX</code><span style="color: rgb(34, 34, 34);">,&nbsp;</span><code>RWX</code><span style="color: rgb(34, 34, 34);">) is only possible within _____</span></summary>
<span style="color: rgb(34, 34, 34);">one namespace</span>
<br></details><details>
<summary>A <font face="monospace">_____&nbsp;</font>is a request for snapshot of a volume by a user. It is similar to a PersistentVolumeClaim.</summary>
<code>VolumeSnapshot</code>&nbsp;
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Are&nbsp;</span><code>VolumeSnapshot</code><span style="color: rgb(34, 34, 34);">,&nbsp;</span><code>VolumeSnapshotContent</code><span style="color: rgb(34, 34, 34);">, and&nbsp;</span><code>VolumeSnapshotClass</code><span style="color: rgb(34, 34, 34);">&nbsp;part of the core API?&nbsp;</span></summary>
No - they are CustomResourceDefinitions.
<br></details><details>
<summary>In volume snapshots,<font face="monospace"> _____&nbsp;</font><span style="color: rgb(34, 34, 34);">are resources in the cluster.&nbsp;</span><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">are requests for those resources.&nbsp;</span></summary>
<code>VolumeSnapshotContents</code><span style="color: rgb(34, 34, 34);">&nbsp;</span><span style="color: rgb(34, 34, 34);">
</span><code>VolumeSnapshots</code><span style="color: rgb(34, 34, 34);">&nbsp;</span><span style="color: rgb(34, 34, 34);">
</span>
<br></details><details>
<summary>While a snapshot is being taken of a PersistentVolumeClaim, that PersistentVolumeClaim is in-use. If you delete a PersistentVolumeClaim API object in active use as a snapshot source, the PersistentVolumeClaim object is not removed immediately. Instead, removal of the PersistentVolumeClaim object is postponed until the snapshot is _____</summary>
readyToUse or aborted.
<br></details><details>
<summary><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">is the unique identifier of the volume created on the storage backend and returned by the CSI driver during the volume creation. This field is required for dynamically provisioning a snapshot. It specifies the volume source of the snapshot.</span></summary>
<code>volumeHandle</code><span style="color: rgb(34, 34, 34);">&nbsp;</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">You can provision a new volume, pre-populated with data from a snapshot, by using the </span><i>_____&nbsp;</i><span style="color: rgb(34, 34, 34);">field in the&nbsp;</span><code>PersistentVolumeClaim</code><span style="color: rgb(34, 34, 34);">&nbsp;object.</span></summary>
<em>dataSource</em><span style="color: rgb(34, 34, 34);">&nbsp;</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">PersistentVolumes that are dynamically created by a StorageClass will have the reclaim policy specified in the&nbsp;</span><code>reclaimPolicy</code><span style="color: rgb(34, 34, 34);">&nbsp;field of the class, which can be...</span></summary>
<span style="color: rgb(34, 34, 34);">&nbsp;</span><code>Delete</code><span style="color: rgb(34, 34, 34);">&nbsp;or&nbsp;</span><code>Retain</code>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">To enable dynamic volume provisioning, a cluster administrator needs to pre-create one or more _____ objects for users.</span></summary>
<span style="color: rgb(34, 34, 34);">StorageClass</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">When a Container crashes, kubelet will restart it, but its on-disk files will be...&nbsp;</span></summary>
Lost, unless stored on a Volume
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">If a PV was dynamically provisioned for a new PVC, the loop will always _____ that PV to the PVC.</span></summary>
binds
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A Pod uses a PersistentVolume. This PV has a node affinity towards certain nodes. Where will the Pod be scheduled?</span></summary>
To the node where the PV is available from.
<br></details><details>
<summary>A volume is said to be _____ when it is free and not yet bound to a claim.</summary>
Available
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">When running Containers together in a&nbsp;</span><code>Pod</code><span style="color: rgb(34, 34, 34);">&nbsp;it is often necessary to share files between those Containers. The Kubernetes&nbsp;_____&nbsp;</span><span style="color: rgb(34, 34, 34);">abstraction solves this problem.</span></summary>
Volume&nbsp;
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Is a volume just a directory with data, accessible to the Containers in its enclosing Pod?</span></summary>
Yes
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Can Volumes mount into other volumes?</span></summary>
No
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A control loop in the master watches for new PVCs, finds a matching PV (if possible), and _____ them.&nbsp;</span></summary>
binds
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">You can only expand a PVC if its storage class's </span><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">field is set to true.&nbsp;</span>To request a larger volume for a PVC, edit the PVC object and specify a larger size. This triggers expansion of the volume that backs the underlying PersistentVolume. A new PersistentVolume is never created to satisfy the claim. Instead, an existing volume is resized.</summary>
<code>allowVolumeExpansion</code><span style="color: rgb(34, 34, 34);">&nbsp;</span>
<br></details><details>
<summary>Can you resize an in-use PVC?</summary>
Yes - since Kubernetes 1.15.&nbsp;<span style="color: rgb(136, 136, 136);">The&nbsp;</span><code>ExpandInUsePersistentVolumes</code>&nbsp;feature must be enabled.
<br></details><details>
<summary>Kubernetes supports two&nbsp;<code>volumeModes</code>&nbsp;of PersistentVolumes:&nbsp;</summary>
<code>Filesystem</code>&nbsp;and&nbsp;<code>Block</code>.
<br></details><details>
<summary><code>volumeMode</code>&nbsp;is an optional API parameter.&nbsp;<font face="monospace">_____&nbsp;</font>is the default mode used when&nbsp;<code>volumeMode</code>&nbsp;parameter is omitted.</summary>
<code>Filesystem</code>&nbsp;
<br></details><details>
<summary>A volume with <font face="monospace">_____</font>&nbsp;is&nbsp;<em>mounted</em>&nbsp;into Pods into a directory. If the volume is backed by a block device and the device is empty, Kuberneretes creates a filesystem on the device before mounting it for the first time.</summary>
volumeMode: Filesystem
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">ReadWriteMany&nbsp;</span></summary>
<span style="color: rgb(34, 34, 34);">&nbsp;the volume can be mounted as read-write by many nodes</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A PV can have a class, which is specified by setting the </span><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">attribute to the name of a&nbsp;</span><a href="https://kubernetes.io/docs/concepts/storage/storage-classes/">StorageClass</a><span style="color: rgb(34, 34, 34);">.&nbsp;</span></summary>
<code>storageClassName</code>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A claim can request a particular class by specifying the name of a StorageClass</span><span style="color: rgb(34, 34, 34);">&nbsp;using the attribute&nbsp;</span><font face="monospace">_____</font><span style="color: rgb(34, 34, 34);">.&nbsp;</span></summary>
storageClassName
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Similar to how API resources&nbsp;</span><code>PersistentVolume</code><span style="color: rgb(34, 34, 34);">&nbsp;and&nbsp;</span><code>PersistentVolumeClaim</code><span style="color: rgb(34, 34, 34);">&nbsp;are used to provision volumes for users and administrators,&nbsp;</span><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">and&nbsp;</span><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">API resources are provided to create volume snapshots for users and administrators.</span></summary>
VolumeSnapshot&nbsp;<code>
</code><code>VolumeSnapshotContent</code><span style="color: rgb(34, 34, 34);">&nbsp;</span>
<br></details><details>
<summary><code>VolumeSnapshot</code><span style="color: rgb(34, 34, 34);">&nbsp;support is only available for _____ drivers.</span></summary>
<span style="color: rgb(34, 34, 34);">CSI&nbsp;</span>
<br></details><details>
<summary>The CRDs and snapshot controller installations are the responsibility of _____</summary>
the Kubernetes distribution
<br></details><details>
<summary>The snapshot controller handles the binding of a&nbsp;<code>VolumeSnapshot</code>&nbsp;object with an appropriate&nbsp;<code>VolumeSnapshotContent</code>&nbsp;object, in both pre-provisioned and dynamically provisioned scenarios. The binding is a _____ mapping.&nbsp;
In the case of pre-provisioned binding, the VolumeSnapshot will remain unbound until the requested VolumeSnapshotContent object is created.</summary>
one-to-one
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">An administrator can mark a specific&nbsp;</span><code>StorageClass</code><span style="color: rgb(34, 34, 34);">&nbsp;as default by adding the&nbsp;</span><font face="monospace">_____</font><span style="color: rgb(34, 34, 34);">&nbsp;annotation to it.</span></summary>
storageclass.kubernetes.io/is-default-class
<br></details><details>
<summary>Can you attach as many volumes as you want to a node?</summary>
No - depends on the cloud provider's permitted limit.
<br></details><details>
<summary>A PVC to PV binding is a one-to-one mapping, using a <b>_____&nbsp;</b>which is a bi-directional binding between the PersistentVolume and the PersistentVolumeClaim.&nbsp;</summary>
ClaimRef
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A PV of a particular class can only be bound to PVCs requesting that class. A PV with no&nbsp;</span>_____&nbsp;<span style="color: rgb(34, 34, 34);">has no class and can only be bound to PVCs that request no particular class.</span></summary>
storageClassName
<br></details><details>
<summary>A volume is called _____ when it is bound to a claim.</summary>
Bound
<br></details><details>
<summary>A volume is said to be _____, when the claim has been deleted, but the resource is not yet reclaim by the cluster.</summary>
Released
<br></details><details>
<summary>Mounted directories that are accessible from inside containers.</summary>
Volumes
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A Kubernetes volume has an explicit lifetime - the same as _____</span></summary>
The Pod that encloses it
<br></details><details>
<summary>Is a Volume preserved across Container restarts?</summary>
Yes
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Managing storage is a distinct problem from managing compute instances. The PersistentVolume subsystem provides an API for users and administrators that abstracts details of how storage is provided from how it is consumed. To do this, we introduce two new API resources: _____ and _____.</span></summary>
<span style="color: rgb(34, 34, 34);">PersistentVolume&nbsp;</span><span style="color: rgb(34, 34, 34);">
</span><span style="color: rgb(34, 34, 34);">PersistentVolumeClaim</span><span style="color: rgb(34, 34, 34);">
</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Do PersistentVolumes have a lifecycle dependent on the Pods that use the PV?</span></summary>
No
<br></details><details>
<summary>There are two ways PVs may be provisioned:</summary>
statically or dynamically.
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">When none of the static PVs the administrator created match a user's PersistentVolumeClaim, the cluster may try to _____ provision a volume specially for the PVC. This provisioning is based on StorageClasses: the PVC must request a storage class</span><span style="color: rgb(34, 34, 34);">&nbsp;and the administrator must have created and configured that class for dynamic provisioning to occur.</span></summary>
<span style="color: rgb(34, 34, 34);">dynamically</span>
<br></details><details>
<summary>Once bound, PersistentVolumeClaim binds are _____, regardless of how they were bound.&nbsp;</summary>
exclusive
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Once a user has a claim and that claim is bound, the bound PV belongs to the user for as long as they need it. Users schedule Pods and access their claimed PVs by including a </span><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">section in a Pod's&nbsp;</span><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">block.</span></summary>
<code>persistentVolumeClaim</code><code>
</code><code><code>volumes</code><span style="color: rgb(34, 34, 34);">&nbsp;</span>
</code>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">If an admin deletes a PV that is bound to a PVC, the PV is...</span></summary>
<span style="color: rgb(34, 34, 34);">not removed immediately.</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">When a user is done with their volume, they can delete the PVC objects from the API that allows reclamation of the resource. The reclaim policy for a PersistentVolume tells the cluster what to do with the volume after it has been released of its claim. Currently, volumes can either be _____, _____, _____.</span></summary>
<span style="color: rgb(34, 34, 34);">Retained, Recycled, Deleted.</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">The </span><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">reclaim policy allows for manual reclamation of the resource. When the PersistentVolumeClaim is deleted, the PersistentVolume still exists and the volume is considered "released". But it is not yet available for another claim because the previous claimant's data remains on the volume.</span></summary>
<code>Retain</code>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">For volume plugins that support the </span><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">reclaim policy, deletion removes both the PersistentVolume object from Kubernetes, as well as the associated storage asset in the external cloud infrastructure. Volumes that were dynamically provisioned inherit the&nbsp;</span><a href="https://kubernetes.io/docs/concepts/storage/persistent-volumes/#reclaim-policy">reclaim policy of their StorageClass</a><span style="color: rgb(34, 34, 34);">, which defaults to&nbsp;</span><font face="monospace">_____</font><span style="color: rgb(34, 34, 34);">. The administrator should configure the StorageClass according to users' expectations; otherwise, the PV must be edited or patched after it is created.</span></summary>
<code>Delete</code><span style="color: rgb(34, 34, 34);">&nbsp;</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">ReadWriteOnce&nbsp;</span></summary>
<span style="color: rgb(34, 34, 34);">the volume can be mounted as read-write by a single node</span>
<br></details><details>
<summary>Can a volume be mounted using several access modes at a time?&nbsp;</summary>
No
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A PV can specify _____</span><span style="color: rgb(34, 34, 34);">&nbsp;to define constraints that limit what nodes this volume can be accessed from.&nbsp;</span></summary>
node affinity
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">In Kubernetes, a </span><i>_____&nbsp;</i><span style="color: rgb(34, 34, 34);">represents a snapshot of a volume on a storage system.</span></summary>
<em>VolumeSnapshot</em>
<br></details><details>
<summary>A <font face="monospace">_____&nbsp;</font>is a snapshot taken from a volume in the cluster that has been provisioned by an administrator. It is a resource in the cluster just like a PersistentVolume is a cluster resource.</summary>
<code>VolumeSnapshotContent</code>&nbsp;
<br></details><details>
<summary><font face="monospace">_____&nbsp;</font><span style="color: rgb(34, 34, 34);">allows you to specify different attributes belonging to a&nbsp;</span><code>VolumeSnapshot</code><span style="color: rgb(34, 34, 34);">. These attributes may differ among snapshots taken from the same volume on the storage system and therefore cannot be expressed by using the same&nbsp;</span><code>StorageClass</code><span style="color: rgb(34, 34, 34);">&nbsp;of a&nbsp;</span><code>PersistentVolumeClaim</code><span style="color: rgb(34, 34, 34);">.</span></summary>
<code>VolumeSnapshotClass</code><span style="color: rgb(34, 34, 34);">&nbsp;</span>
<br></details><details>
<summary>There are two ways snapshots may be provisioned:&nbsp;</summary>
pre-provisioned or dynamically provisioned.
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">A cluster administrator creates a number of&nbsp;</span><code>VolumeSnapshotContents</code><span style="color: rgb(34, 34, 34);">. They carry the details of the real volume snapshot on the storage system which is available for use by cluster users. They exist in the Kubernetes API and are available for consumption. This is the description of _____ snapshot provisioning.</span></summary>
pre-provisioned
<br></details><details>
<summary>Instead of using a pre-existing snapshot, you can request that a snapshot to be _____ taken from a PersistentVolumeClaim. The&nbsp;<a href="https://kubernetes.io/docs/concepts/storage/volume-snapshot-classes/">VolumeSnapshotClass</a>&nbsp;specifies storage provider-specific parameters to use when taking a snapshot.</summary>
dynamically
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Users request dynamically provisioned storage by including a _____ in their&nbsp;</span><code>PersistentVolumeClaim</code></summary>
<span style="color: rgb(34, 34, 34);">.spec.storageClassName</span>
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Claims will remain _____ indefinitely if a matching volume does not exist, and will be bound as matching volumes become available.&nbsp;</span></summary>
unbound
<br></details><details>
<summary><span style="color: rgb(34, 34, 34);">Only PVs of the requested class, ones with the same&nbsp;</span>_____&nbsp;<span style="color: rgb(34, 34, 34);">as the PVC, can be bound to the PVC.</span></summary>
StorageClassName
<br></details>
