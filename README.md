## Local runs

1. Start sample API server

```bash
cd sample-api
npm install
npm start &
```

Sample API server will be available at `http://localhost:6060`.

2. Run tests

```bash
jmeter -n -t jmeter-files/test-plan.jmx \
-Jdomain=localhost -Jport=6060 -Jnum_threads=3000 \
-e -f -l reports/result.jtl -o reports
```

3. Upload JMeter result to [Latency Lingo](https://latencylingo.com/dashboard)

```bash
JTL_RESULT_FILE=result.jtl LATENCY_LINGO_API_KEY=$LATENCY_LINGO_API_KEY \
./scripts/publish_to_latency_lingo.sh
```

Get the `LATENCY_LINGO_API_KEY` from [API Access](https://latencylingo.com/account/api-access) and export to environment.
