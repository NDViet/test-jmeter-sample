## Local runs

1. Start sample API server

```bash
cd sample-api
npm install
npm start &
```

2. Run tests

```bash
jmeter -n -t jmeter-files/test-plan.jmx -Jdomain=localhost -Jport=6060 -Jnum_threads=3000 -e -f -l reports/result.jtl -o reports
```