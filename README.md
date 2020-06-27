# myfirstplaybook_apache

---
- hosts: all
  tasks:
    - name: install apache2
      apt: 
         name: apache2 
         state: latest
      become: yes 
      
    - name: index.html
      copy: 
          content: "This is my first playbook"
          dest: /var/www/html/index.html
      become: yes
       
    - name: apache2 restart
      service:
             name: apache2
             state: restarted
      become: yes
