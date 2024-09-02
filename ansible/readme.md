
# How to run playbook

<h4> Run playbook with the following command: </h4>
<p>Note: adds remote system user password as extra variable </p>

* Replace `your_user` with your actual username everywhere
  * If using private keys update `path_to_your_private_key` in `ansible>inventory>k8s_infra.ini`

```shell
ansible-playbook -v roles/k8s/tasks/k8s-dependencies.yml -i inventory/k8s_infra.ini -k --extra-vars "ansible_sudo_pass=yourpassword"
ansible-playbook -v roles/k8s/tasks/k8s-plane.yml -i inventory/k8s_infra.ini -k --extra-vars "ansible_sudo_pass=yourpassword"
ansible-playbook -v roles/k8s/tasks/k8s-worker.yml -i inventory/k8s_infra.ini -k --extra-vars "ansible_sudo_pass=yourpassword"
```