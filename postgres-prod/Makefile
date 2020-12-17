pg_version=10.6-v3
stash_postgres_version=10.14.0-v3

# install the Postgres Database

postgres:
	kubectl apply -f postgres.yaml

tardigrade-secret:
	kubectl create secret generic tardigrade-secret \
		--from-file=./RESTIC_PASSWORD \
		--from-file=./AWS_ACCESS_KEY_ID \
		--from-file=./AWS_SECRET_ACCESS_KEY \

tardigrade-repository:
	kubectl apply -f repository-with-tardigrade.yaml



# Make backupconfiguration
backupconfiguration:
	kubectl apply -f backupConfiguration-tardigrade.yaml


# Install pgadmin
pgadmin:
	kubectl apply -f pgadmin.yaml
