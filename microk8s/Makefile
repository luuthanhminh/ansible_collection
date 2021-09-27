# load env
env_path=.env
include $(env_path)
export $(shell sed 's/=.*//' $(env_path))

deploy:
	ansible-playbook -v -i inventory -l microk8s_HA --extra-vars \
	"ansible_become_password=$(ansible_become_password) \
	ansible_user=$(ansible_user)" \
	deployment.yaml

test:
	ansible-playbook -v -i inventory -l microk8s_HA --extra-vars \
	"ansible_become_password=$(ansible_become_password) \
	ansible_user=$(ansible_user)" \
	test.yaml