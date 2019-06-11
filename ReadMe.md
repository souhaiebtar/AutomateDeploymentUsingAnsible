#### Rquirements 

ansible

#### How to run

```ansible
ansible-playbook -i hosts playbook01.yml
```

or

```ansible
ansible-playbook -i hosts playbook01.yml --flush-cache
```

> N.B: when updating service
> let say change the image used by `thingsboard_tb` service
> use `docker service update --image m2mgroupe/thingsboard:2.2.0 thingsboard_tb`, change the name of image acording to your which
> or you can modify the `docker-production.yml` file or `tb.env` in the `thingsboard` folder on the manager node, than
> `docker service rm thingsboard_tb` 
> `cd ~/thingsboard`
> `docker stack deploy -c docker-production.yml thingsboard`
> after that it seem that nginx need to be reloaded again ( or it will not work )
> than to do so
> `docker service rm nginx`
> `cd ~/nginx-production`
> `docker stack deploy -c production-stack.yml nginx`