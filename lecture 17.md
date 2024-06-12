Fuzzing

“Fuzzing” technique to test the security and vulnerabilities of crypto libraries in Android applications.
The tools used for fuzzing in this lecture include
OSS-Fuzz: Continuous Fuzzing Service for Open Source Software
ClusterFuzz: Scalable Fuzzing Infrastructure
FuzzBench: Fuzzer benchmarking as a service


which are automated processes used by Google for open-source projects.
Fuzzing involves testing the behaviour and vulnerabilities of functions by manipulating inputs, such as strings or images.
These are all common fuzzing tools, but we will be discussing the CDF (crypto differential fuzzing) tool.
CDF (crypto differential fuzzing)
CDF is a tool to automatically test the correctness and security of cryptographic software. CDF can detect implementation errors, compliance failures, side-channel leaks, and so on. CDF implements a combination of unit tests with "differential fuzzing", an approach that compares the behaviour of different implementations of the same primitives when fed edge cases and values maximizing the code coverage.
Unlike general-purpose fuzzers and testing software, CDF is:
Smart: CDF knows what kind of algorithm it's testing and adapts to the tested functions.
Fast: CDF tests only what needs to be tested and parallelizes its tests as much as possible.
Polyvalent: CDF isn't specific to any language or API, but supports arbitrary executable programs or scripts.
Portable: CDF will run on any Unix or Windows platform, since it is written in Go without any platform-specific dependencies.
Installation
The purpose of CDF is to provide more efficient testing tool to developers and security researchers, being more effective than test vectors and cheaper than manual audit of formal verification.


![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/afa40761-9aa1-45ed-bab0-3add0e62cf0b)

Then enter the command in the terminal:
git clone https://github.com/kudelskisecurity/cdf.git

![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/affb24e5-d461-42d5-a3b2-1ac18d1865f8)

First build the cdf binary.

<img width="246" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/29ccb0d9-a619-49e8-a3a2-61b42fcd9979">


<img width="246" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/02e656bc-5128-4b67-bf02-7dcd24a34cd9">

Command: make examples-all will build all the examples.

While make examples-go will only build the Go examples.


<img width="244" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/609fcb01-fbb0-45b5-a7c3-6fea3bf7c53d">

<img width="413" alt="image" src="https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/b510c6ec-56f9-4096-afd4-8c7edc1329f2">


make test will run unit tests (of CDF).

We may want to view usage info by running cdf -h

We may then try an example such as the rsaenc interface against the RSA OAEP Go and CryptoPP examples.

Viewing CryptoPP as our reference, you can test the Go implementation by doing:
cdf rsaenc /examples/oaep_rsa2048_go /examples/oaep_rsa2048_cryptopp

This command will perform various tests specific to the rsaenc interface.


![image](https://github.com/SantoshKumarP1412/Android-Security/assets/140537888/ebbb575a-d192-442a-9eb6-a6f4bdbf3c62)



In this example, CDF should complain about the maximum public exponent size the Go implementation support.
If we check its code we can see the public exponent is being stored as a normal integer, whereas in CryptoPP (and most other implementations), it is stored as a big integer.
This is however by design and will likely not be changed.
