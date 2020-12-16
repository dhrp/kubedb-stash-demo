pg_version=10.6-v3
stash_postgres_version=10.14.0-v3

install-stash-postgres2:	
	helm install stash-postgres-$(stash_postgres_version) appscode/stash-postgres --version=$(stash_postgres_version) --namespace=kube-system


# install the Postgres Database

postgres:
	kubectl apply -f postgres.yaml


# Make backupconfiguration
backupconfiguration:
	kubectl apply -f backupConfiguration-tardigrade.yaml


minio-secret:
	kubectl create secret generic minio-secret \
		--from-file=./RESTIC_PASSWORD \
		--from-file=./AWS_ACCESS_KEY_ID \
		--from-file=./AWS_SECRET_ACCESS_KEY \

tardigrade-repository:
	kubectl apply -f repository-with-tardigrade.yaml


# Make repository
pvc:
	kubectl apply -f pvc.yaml

local-secret:
	kubectl create secret generic local-secret --from-file=./RESTIC_PASSWORD

local-repository:
	kubectl apply -f repository-with-pvc.yaml


# Install pgadmin
pgadmin:
	kubectl apply -f pgadmin.yaml
