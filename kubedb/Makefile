# Install KubeDB

repository:
	helm repo add appscode https://charts.appscode.com/stable/

update:
	helm repo update

install-community:
	helm install kubedb-community appscode/kubedb \
		--version v0.15.1 \
		--namespace kube-system \
		--set-file license=./kubedb-enterprise-license.txt

install-enterprise:
	helm install kubedb-enterprise appscode/kubedb-enterprise  \
		--version v0.2.1                  \
		--namespace kube-system                                    \
		--set-file license=kubedb-enterprise-license.txt

install-catalog:
	helm install kubedb-catalog appscode/kubedb-catalog   \
	--version v0.15.2              \
	--namespace kube-system


# install stash
upgrade-stash-enterprise:
	helm upgrade stash-enterprise appscode/stash-enterprise  \
	--version v0.11.7                  \
	--namespace kube-system                       \
	--set-file license=stash-enterprise-license.txt

# install stash-postgres-addon
stash-postgres-addon:
	curl -fsSL https://github.com/stashed/catalog/raw/v2020.11.17/deploy/helm3.sh | bash -s -- --catalog=stash-postgres
