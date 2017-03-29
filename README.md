
# Benchmark PHP 5.6 vs PHP 7.1

```
vagrant up
```

```
vagrant ssh bench
```

```
ab -n 1000 -c 5 http://sf56.dev/
```

```
ab -n 1000 -c 5 http://sf71.dev/
```

- -n - number of requests
- -c - number of clients in one time (concurrency)