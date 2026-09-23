# final-isa









kind: ClusterRole
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  name: notification-app-support

rules:

  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - ''
    resources:
      - configmaps
      - endpoints
      - persistentvolumeclaims
      - persistentvolumeclaims/status
      - pods
      - pods/log
      - pods/status
      - replicationcontrollers
      - replicationcontrollers/scale
      - replicationcontrollers/status
      - serviceaccounts
      - services
      - services/status
      - bindings
      - events
      - limitranges
      - namespaces
      - namespaces/status
      - resourcequotas
      - resourcequotas/status
      - resourcequotausages

  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - discovery.k8s.io
    resources:
      - endpointslices

  
  - verbs:
      - delete
      - deletecollection
      - patch
      - update
    apiGroups:
      - ''
    resources:
      - pods
      - configmaps
      - endpoints
      - events
      - persistentvolumeclaims
      - replicationcontrollers
      - replicationcontrollers/scale
      - services
      - services/proxy
      - pods/proxy

 
  - verbs:
      - impersonate
    apiGroups:
      - ''
    resources:
      - serviceaccounts


  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - apps
    resources:
      - controllerrevisions
      - daemonsets
      - daemonsets/status
      - deployments
      - deployments/scale
      - deployments/status
      - replicasets
      - replicasets/scale
      - replicasets/status
      - statefulsets
      - statefulsets/scale
      - statefulsets/status

  
  - verbs:
      - delete
      - deletecollection
      - patch
      - update
    apiGroups:
      - apps
    resources:
      - daemonsets
      - deployments
      - deployments/rollback
      - deployments/scale
      - replicasets
      - replicasets/scale
      - statefulsets
      - statefulsets/scale

 
  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - batch
    resources:
      - cronjobs
      - cronjobs/status
      - jobs
      - jobs/status

  
  - verbs:
      - delete
      - deletecollection
      - patch
      - update
    apiGroups:
      - batch
    resources:
      - cronjobs
      - jobs

 
  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - autoscaling
    resources:
      - horizontalpodautoscalers
      - horizontalpodautoscalers/status

  - verbs:
      - delete
      - deletecollection
      - patch
      - update
    apiGroups:
      - autoscaling
    resources:
      - horizontalpodautoscalers

  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - policy
    resources:
      - poddisruptionbudgets
      - poddisruptionbudgets/status

  - verbs:
      - delete
      - deletecollection
      - patch
      - update
    apiGroups:
      - policy
    resources:
      - poddisruptionbudgets

  
  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - extensions
    resources:
      - daemonsets
      - daemonsets/status
      - deployments
      - deployments/scale
      - deployments/status
      - ingresses
      - ingresses/status
      - networkpolicies
      - replicasets
      - replicasets/scale
      - replicasets/status
      - replicationcontrollers/scale

  - verbs:
      - delete
      - deletecollection
      - patch
      - update
    apiGroups:
      - extensions
    resources:
      - daemonsets
      - deployments
      - deployments/rollback
      - deployments/scale
      - ingresses
      - networkpolicies
      - replicasets
      - replicasets/scale
      - replicationcontrollers/scale


  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - ''
      - route.openshift.io
    resources:
      - routes
      - routes/status

  - verbs:
      - delete
      - deletecollection
      - patch
      - update
    apiGroups:
      - ''
      - route.openshift.io
    resources:
      - routes

  - verbs:
      - update
    apiGroups:
      - ''
      - route.openshift.io
    resources:
      - routes/status


  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - networking.k8s.io
    resources:
      - ingresses
      - ingresses/status
      - networkpolicies

  - verbs:
      - delete
      - deletecollection
      - patch
      - update
    apiGroups:
      - networking.k8s.io
    resources:
      - ingresses
      - networkpolicies

  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - k8s.cni.cncf.io
    resources:
      - network-attachment-definitions

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - k8s.ovn.org
    resources:
      - userdefinednetworks


  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
      - deletecollection
    apiGroups:
      - snapshot.storage.k8s.io
    resources:
      - volumesnapshots


  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - metrics.k8s.io
    resources:
      - pods
      - nodes


  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
      - deletecollection
    apiGroups:
      - coordination.k8s.io
    resources:
      - leases


  # ---------------------------------------------------------------------------
  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
      - deletecollection
    apiGroups:
      - ''
      - image.openshift.io
    resources:
      - imagestreamimages
      - imagestreammappings
      - imagestreams
      - imagestreams/secrets
      - imagestreamtags
      - imagetags

  - verbs:
      - get
      - update
    apiGroups:
      - ''
      - image.openshift.io
    resources:
      - imagestreams/layers

  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - ''
      - image.openshift.io
    resources:
      - imagestreams/status


  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
      - deletecollection
    apiGroups:
      - ''
      - build.openshift.io
    resources:
      - buildconfigs
      - buildconfigs/webhooks
      - builds
      - buildlogs

  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - ''
      - build.openshift.io
    resources:
      - builds/log

  - verbs:
      - update
    apiGroups:
      - ''
      - build.openshift.io
    resources:
      - builds/details

  - verbs:
      - admin
      - edit
      - view
    apiGroups:
      - build.openshift.io
    resources:
      - jenkins


  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
      - deletecollection
    apiGroups:
      - ''
      - apps.openshift.io
    resources:
      - deploymentconfigs
      - deploymentconfigs/scale

  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - ''
      - apps.openshift.io
    resources:
      - deploymentconfigs/log
      - deploymentconfigs/status

  # ---------------------------------------------------------------------------
  # Templates (create removed)
  # ---------------------------------------------------------------------------
  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
      - deletecollection
    apiGroups:
      - ''
      - template.openshift.io
    resources:
      - processedtemplates
      - templateconfigs
      - templateinstances
      - templates

  # ---------------------------------------------------------------------------
  # Quota visibility
  # ---------------------------------------------------------------------------
  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - ''
      - quota.openshift.io
    resources:
      - appliedclusterresourcequotas

  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - ''
      - authorization.openshift.io
    resources:
      - rolebindingrestrictions


  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
      - deletecollection
    apiGroups:
      - ''
      - authorization.openshift.io
      - rbac.authorization.k8s.io
    resources:
      - rolebindings
      - roles


  - verbs:
      - get
      - delete
      - patch
      - update
    apiGroups:
      - ''
      - project.openshift.io
    resources:
      - projects


  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - helm.openshift.io
    resources:
      - projecthelmchartrepositories


  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - operators.coreos.com
    resources:
      - clusterserviceversions
      - catalogsources
      - installplans
      - subscriptions
      - operatorgroups

  - verbs:
      - update
      - patch
      - delete
    apiGroups:
      - operators.coreos.com
    resources:
      - subscriptions
      - clusterserviceversions
      - catalogsources
      - installplans

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - packages.operators.coreos.com
    resources:
      - packagemanifests
      - packagemanifests/icon


  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
      - deletecollection
    apiGroups:
      - apps.open-cluster-management.io
    resources:
      - subscriptions

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - operator.open-cluster-management.io
    resources:
      - klusterlets


  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - appconnect.ibm.com
    resources:
      - configurations
      - dashboards
      - designerauthorings
      - integrationflows
      - integrationruntimes
      - integrationservers
      - switchservers
      - traces

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - apiconnect.ibm.com
    resources:
      - apis
      - products

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - mq.ibm.com
    resources:
      - queuemanagers

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - integration.ibm.com
    resources:
      - integrationassemblies
      - integrationbindings
      - messagingchannels
      - messagingqueues
      - messagingservers
      - messagingusers
      - platformnavigators

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - core.automation.ibm.com
    resources:
      - automationuiconfigs
      - cartridges

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - cp4i.ibm.com
    resources:
      - cp4iservicesbindings

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - keycloak.integration.ibm.com
    resources:
      - integrationkeycloakclients
      - integrationkeycloakusers

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - k8s.keycloak.org
    resources:
      - keycloaks
      - keycloakrealmimports

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - operator.ibm.com
    resources:
      - authentications
      - certmanagers
      - commonservices
      - grafanas
      - ibmlicensingdefinitions
      - ibmlicensingmetadatas
      - ibmlicensingquerysources
      - ibmlicensings
      - managementingresses
      - mongodbs
      - namespacescopes
      - nginxingresses
      - oidcclientwatchers
      - operandbindinfos
      - operandconfigs
      - operandregistries
      - operandrequests
      - operatorconfigs
      - paps
      - platformapis
      - policycontrollers
      - policydecisions
      - secretwatchers
      - securityonboardings

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - operators.ibm.com
    resources:
      - commonwebuis
      - switcheritems

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - foundation.ibm.com
    resources:
      - navconfigurations

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - monitoringcontroller.cloud.ibm.com
    resources:
      - monitoringdashboards

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - zen.cpd.ibm.com
    resources:
      - zenextensions
      - zenservices





  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - csiaddons.openshift.io
    resources:
      - csiaddonsnodes
      - encryptionkeyrotationcronjobs
      - encryptionkeyrotationjobs
      - networkfenceclasses
      - networkfences
      - reclaimspacecronjobs
      - reclaimspacejobs



  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - ramendr.openshift.io
    resources:
      - recipes


  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - postgresql.k8s.enterprisedb.io
    resources:
      - backups
      - clusterimagecatalogs
      - clusters
      - databases
      - imagecatalogs
      - poolers
      - publications
      - scheduledbackups
      - subscriptions


  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - certmanager.k8s.io
    resources:
      - certificaterequests
      - certificates
      - challenges
      - clusterissuers
      - issuers
      - orders


  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - logging.openshift.io
    resources:
      - clusterlogforwarders
      - clusterloggings
      - elasticsearches
      - kibanas
      - logfilemetricexporters

  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - observability.openshift.io
    resources:
      - clusterlogforwarders


  - verbs:
      - get
      - list
      - watch
      - update
      - patch
      - delete
    apiGroups:
      - compliance.openshift.io
    resources:
      - compliancecheckresults
      - complianceremediations
      - compliancescans
      - compliancesuites
      - customrules
      - profilebundles
      - profiles
      - rules
      - scansettingbindings
      - scansettings
      - tailoredprofiles
      - variables





  - verbs:
      - get
      - list
      - watch
    apiGroups:
      - apiextensions.k8s.io
    resources:
      - customresourcedefinitions



# =============================================================================
kind: RoleBinding
apiVersion: rbac.authorization.k8s.io/v1
metadata:
  name: notification-app-support
  namespace: prod-notifications
subjects:
  - kind: Group
    apiGroup: rbac.authorization.k8s.io
    name: Notification-App-Support-PROD      # confirm exact AD group name
roleRef:
  kind: ClusterRole
  apiGroup: rbac.authorization.k8s.io
  name: notification-app-support

