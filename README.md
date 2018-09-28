# ansible-roles

#### docker + multi gitlab runner
`ansible-playbook -i hosts play.yml`

#### example playbook gitlab-runner & docker
```
---
- hosts: all
  vars:
    # concurent = 4
    gitlab_multirunner:
      runners:
        - name: gitlab-runner-shell
          state: present
          ci_server: https://gitlab.com/
          token: FDLbvyxq1Qvn-23jzZxN
          executor: shell
          tags:
            - exe_shell

        - name: gitlab-runner-docker
          state: present
          ci_server: https://gitlab.com/
          token: FDLbvyxq1Qvn-23jzZxN
          executor: docker
          docker_image: ubuntu:16.04
          tags:
            - exe_docker

  roles:
   - docker-install
   - gitlab-runner

```

#### roles
docker-install - https://github.com/nickjj/ansible-docker  
gitlab-runner - https://github.com/gtrafimenkov/ansible-role-gitlab-ci-multi-runner  
bind - https://github.com/bertvv/ansible-role-bind

ansible-role-nvidia-driver - https://github.com/uchida/ansible-role-nvidia-driver  
dependencies: ansible-role-nvidia-repo - https://github.com/uchida/ansible-role-nvidia-repo


#### TODO
