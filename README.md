````
    Install openLDAP and phpldapadmin with persistent to kubernetes.
    Detail: https://www.cnblogs.com/dukuan/p/9983899.html
    持久化安装openLDAP和phpldapadmin到k8s
    部署文档:https://www.cnblogs.com/dukuan/p/9983899.html
````

安装文档：
https://www.cnblogs.com/dukuan/p/9983899.html

[root@k8s-master01 openldap]# kubectl apply -f .
deployment.extensions/ldap created
persistentvolumeclaim/openldap-data created
secret/ldap-secret created
service/ldap-service created
deployment.extensions/phpldapadmin created
service/phpldapadmin created



==============
若要修改dn、admin密码————修改environment中my-env.startup.yaml文件对应内容，执行脚本 bash file-tobash64.sh my-env.startup.yaml生成的内容替换ldap-secret.yaml

