
# Benchmark PHP 5.6 vs PHP 7.1 vs Nginx vs Apache + Apache benchmark (5 Virtual Machines)

## Tested only on MacOS Sierra

Install Virtualbox & Vagrant

```
vagrant up
```

```
vagrant ssh bench
```

```
ab -n 1000 -c 5 http://php56_nginx.dev/
```

```
ab -n 1000 -c 5 http://php71_nginx.dev/
```

```
ab -n 1000 -c 5 http://php56_apache.dev/
```

```
ab -n 1000 -c 5 http://php71_apache.dev/
```

- -n - number of requests
- -c - number of clients in one time (concurrency)