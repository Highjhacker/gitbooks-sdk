---
id: getting-started
title: Getting Started
description: C++ Client Library For Communicating With Core Server Public REST API
---

# Client

## Development

1. Fork the [package](https://github.com/ARKEcosystem/cpp-client).
2. Clone the newly forked repository.

   ```bash
   git clone https://github.com/<githubusername>/cpp-client
   ```

3. Next, we move into the cloned directory.

   ```bash
   cd cpp-client
   ```

4. Build the package using CMake.

   ```bash
   mkdir build && cd build
   cmake -DUNIT_TEST=ON ..
   cmake --build .
   ```

5. Now we can run the tests to see if everything is running as it should.

   ```bash
   ./test/ARK-Cpp-Client-tests
   ```

### ESP8266 \(PlatformIO\)

```bash
pio run -e esp8266 -t upload
```

### ESP32 \(PlatformIO\)

```bash
pio run -e esp32 -t upload
```

