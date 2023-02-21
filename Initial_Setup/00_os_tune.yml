- hosts : ${ansible_hostgroup}
  become: yes
  become_user: root
  become_method: su

  tasks :
  - name: sysctl_file config upload
    copy:
        src: ${PATH}/sysctl.conf
        dest: /etc/sysctl.conf
        owner: root
        group: root
        mode: 0755
        backup: no

  - name: sysctl apply
    command: /bin/sysctl -p

  - name : rc_local upload
    copy:
     src: ${PATH}/rc.local
     dest: /etc/rc.d/rc.local
     owner: root
     group: root
     mode: 0644
     backup: no
     
  - name : limits file upload
    copy:
     src: ${PATH}/limits.conf
     dest: /etc/security/limits.conf
     owner: root
     group: root
     mode: 0644
     backup: no

  - name : 20limits file upload
    copy:
     src: ${PATH}/20-nproc.conf
     dest: /etc/security/limits.d/20-nproc.conf
     owner: root
     group: root
     mode: 0644
     backup: no
