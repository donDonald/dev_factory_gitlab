# gitlab - Web UI for git



### Use-cases
- I'm a developer and need quckly to setup git and frontend. No SSL yet.



### Details
It's a docker-compose file containing only service:
```
$ docker-compose ps
       Name               Command          State                                          Ports                                    
-----------------------------------------------------------------------------------------------------------------------------------
gitlab_gitlab_1   /assets/wrapper   Up (health: starting)   0.0.0.0:32786->1342/tcp, 22/tcp, 0.0.0.0:443->443/tcp, 0.0.0.0:11121->80/tcp
```



### Cridentials
Here are no predefined cridentials as such\
Once you navigate to gitlab page simly register you user and that user has all priveleges, you can add ssh keys and so on.



### To launch
```
$ docker-compose up -d --build
```



### Append gitlab to /etc/hosts
```
$ echo "$(docker exec -it gitlab_gitlab_1 bash -c "hostname -i" | head -c-2) $(docker exec -it gitlab_gitlab_1 bash -c "hostname" | head -c-2)" >> /etc/hosts
```



### To shutdown
```
$ docker-compose down
```



### To cleanup volumes
```
$ docker volume rm gitlab_gitlab-etc gitlab_gitlab-log gitlab_gitlab-opt
```



### Web services
- [gitlab](http://gitlab)
- [localhost](http://localhost:11121)



### Links
- [Configuration](https://docs.gitlab.com/omnibus/settings/configuration.html)
- [Https setup](https://docs.gitlab.com/omnibus/settings/nginx.html#manually-configuring-https)

