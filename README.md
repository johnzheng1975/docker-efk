# docker-efk

## Purpose
An example show how search guard intergrate with fluentd + elastic search + kibana.

## How to run
Run below, to start all containers
```
docker-compose up
```

Run below, make user/role/mapping take effective
```
docker-compose exec -T elasticsearch bin/init_sg.sh
```

Run below, to view elastic search status:
```
curl -k https://localhost:9200/_cat -u user1:user1pwd
```

Run below, to trigger logs:
```
for i in {1..10}; do curl http://localhost:80/; done
```

Verify below steps in kibana -- localhost:5601.
```
Log in with user1 / user1pwd;
Create "newf1*" from Management => Index Patterns => Create index pattern 
Log out;

Log in with user2 / user2pwd;
Create "newf2*" from Management => Index Patterns => Create index pattern 
Log out;

Now, in kibana Discover, 
For user log in with user1, he can only access "newf1*" filter successfully.
For user log in with user2, he can only access "newf2*" filter successfully.
```

You can find search guard integration successfully!

 