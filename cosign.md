cosign generate-key-pair
podman login quay.apps.cluster-x9fsz.x9fsz.sandbox2753.opentlc.com
podman pull quay.apps.cluster-x9fsz.x9fsz.sandbox2753.opentlc.com/quayadmin/globex-ui:app-mod-workshop
podman images
podman tag quay.apps.cluster-x9fsz.x9fsz.sandbox2753.opentlc.com/quayadmin/globex-ui:app-mod-workshop quay.apps.cluster-x9fsz.x9fsz.sandbox2753.opentlc.com/quayadmin/globex-ui:cosign-test
podman push quay.apps.cluster-x9fsz.x9fsz.sandbox2753.opentlc.com/quayadmin/globex-ui:cosign-test
podman images --digests
cosign sign --key cosign.key quay.apps.cluster-x9fsz.x9fsz.sandbox2753.opentlc.com/quayadmin/globex-ui@sha256:cfe2dde5481af1252def9fd416d088227b5bd7a52d28245405248a65a1347057
cosign verify --key cosign.pub quay.apps.cluster-x9fsz.x9fsz.sandbox2753.opentlc.com/quayadmin/globex-ui@sha256:cfe2dde5481af1252def9fd416d088227b5bd7a52d28245405248a65a1347057

cosign sign --key cosign.key quay.apps.cluster-x9fsz.x9fsz.sandbox2753.opentlc.com/quayadmin/globex-ui@sha256:cfe2dde5481af1252def9fd416d088227b5bd7a52d28245405248a65a1347057 -a team=pixdev
cosign verify --key cosign.pub quay.apps.cluster-x9fsz.x9fsz.sandbox2753.opentlc.com/quayadmin/globex-ui@sha256:cfe2dde5481af1252def9fd416d088227b5bd7a52d28245405248a65a1347057
