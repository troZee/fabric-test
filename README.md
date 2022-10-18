# RN New Arch Performance Benchmarks

This repo aims to provide different scenarios to benchmark performance difference between the new RN architecture and the old one.

## Scenario 1: Just display 10k views

- [Code](./FabricEnabled/thousand-views/App.tsx)
- [Results](https://rn-new-arch-perf.netlify.app/a10s/manyviews/report)

### Run performance test

1. In one terminal, run `npx appium`
2. In another run `NEW_ARCH=false npx ts-node performance/manyviews.ts`
3. Then run `NEW_ARCH=true npx ts-node performance/manyviews.ts`
4. Compare results with `npx @perf-profiler/web-reporter results_*`

More details on https://github.com/bamlab/android-performance-profiler

### Build APKs

```shell
# Copy code
cp -R FabricEnabled/index.js FabricDisabled
cp -R FabricEnabled/thousand-views FabricDisabled

# Run builds
cd FabricEnabled/android && ./gradlew assembleRelease
cd FabricDisabled/android && ./gradlew assembleRelease
```
