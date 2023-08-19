```
naabu -list <fileName> -top-ports 1000 -execlude-ports 80,443,21,22,25 -o ports.txt
```

```
naabu -list <fileName> -p- 1000 -execlude-ports 80,443,21,22,25 -o ports.txt
```
