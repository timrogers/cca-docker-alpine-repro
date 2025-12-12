# Docker Build Output

```
#0 building with "default" instance using docker driver

#1 [internal] load build definition from Dockerfile
#1 transferring dockerfile: 83B done
#1 DONE 0.0s

#2 [internal] load metadata for docker.io/library/node:22-alpine
#2 ...

#3 [auth] library/node:pull token for registry-1.docker.io
#3 DONE 0.0s

#2 [internal] load metadata for docker.io/library/node:22-alpine
#2 DONE 1.5s

#4 [internal] load .dockerignore
#4 transferring context: 2B done
#4 DONE 0.0s

#5 [1/2] FROM docker.io/library/node:22-alpine@sha256:9632533eda8061fc1e9960cfb3f8762781c07a00ee7317f5dc0e13c05e15166f
#5 resolve docker.io/library/node:22-alpine@sha256:9632533eda8061fc1e9960cfb3f8762781c07a00ee7317f5dc0e13c05e15166f done
#5 sha256:4745102427f1b0f32bbb42b1342f3aec192e0a029641fec018ff18aa1bd8177f 0B / 1.26MB 0.1s
#5 sha256:9632533eda8061fc1e9960cfb3f8762781c07a00ee7317f5dc0e13c05e15166f 6.41kB / 6.41kB done
#5 sha256:3404205afbfa99ffb663ec5ac28be64bd789541816885c75939c7d24dce06fa2 1.72kB / 1.72kB done
#5 sha256:38925ee9872d372937cb288c928672b2481fef11e525889c0b9e2556466d2339 6.52kB / 6.52kB done
#5 sha256:014e56e613968f73cce0858124ca5fbc601d7888099969a4eea69f31dcd71a53 0B / 3.86MB 0.1s
#5 sha256:2e4fafc9c573e8168a7430607ae67549589fb2387ba7cd514a4e9c266c1a9760 0B / 51.60MB 0.1s
#5 sha256:014e56e613968f73cce0858124ca5fbc601d7888099969a4eea69f31dcd71a53 3.86MB / 3.86MB 0.1s done
#5 sha256:2e4fafc9c573e8168a7430607ae67549589fb2387ba7cd514a4e9c266c1a9760 10.49MB / 51.60MB 0.2s
#5 extracting sha256:014e56e613968f73cce0858124ca5fbc601d7888099969a4eea69f31dcd71a53
#5 sha256:b9b992ae23a0421147ed82b168cabeb8aae5a9b2773a11d9bb440975d64d8da6 0B / 446B 0.2s
#5 sha256:4745102427f1b0f32bbb42b1342f3aec192e0a029641fec018ff18aa1bd8177f 1.26MB / 1.26MB 0.3s done
#5 sha256:2e4fafc9c573e8168a7430607ae67549589fb2387ba7cd514a4e9c266c1a9760 51.60MB / 51.60MB 0.4s done
#5 extracting sha256:014e56e613968f73cce0858124ca5fbc601d7888099969a4eea69f31dcd71a53 0.1s done
#5 sha256:b9b992ae23a0421147ed82b168cabeb8aae5a9b2773a11d9bb440975d64d8da6 446B / 446B 0.3s done
#5 extracting sha256:2e4fafc9c573e8168a7430607ae67549589fb2387ba7cd514a4e9c266c1a9760 0.1s
#5 extracting sha256:2e4fafc9c573e8168a7430607ae67549589fb2387ba7cd514a4e9c266c1a9760 1.2s done
#5 extracting sha256:4745102427f1b0f32bbb42b1342f3aec192e0a029641fec018ff18aa1bd8177f
#5 extracting sha256:4745102427f1b0f32bbb42b1342f3aec192e0a029641fec018ff18aa1bd8177f 0.0s done
#5 extracting sha256:b9b992ae23a0421147ed82b168cabeb8aae5a9b2773a11d9bb440975d64d8da6 done
#5 DONE 1.9s

#6 [2/2] RUN apk update --no-cache
#6 60.16 WARNING: fetching https://dl-cdn.alpinelinux.org/alpine/v3.23/main/x86_64/APKINDEX.tar.gz: TLS: unspecified error
#6 120.2 WARNING: fetching https://dl-cdn.alpinelinux.org/alpine/v3.23/community/x86_64/APKINDEX.tar.gz: TLS: unspecified error
#6 120.2 2 unavailable, 0 stale; 18 distinct packages available
#6 ERROR: process "/bin/sh -c apk update --no-cache" did not complete successfully: exit code: 2
------
 > [2/2] RUN apk update --no-cache:
60.16 WARNING: fetching https://dl-cdn.alpinelinux.org/alpine/v3.23/main/x86_64/APKINDEX.tar.gz: TLS: unspecified error
120.2 WARNING: fetching https://dl-cdn.alpinelinux.org/alpine/v3.23/community/x86_64/APKINDEX.tar.gz: TLS: unspecified error
120.2 2 unavailable, 0 stale; 18 distinct packages available
------
Dockerfile:2
--------------------
   1 |     FROM node:22-alpine
   2 | >>> RUN apk update --no-cache
   3 |     
--------------------
ERROR: failed to build: failed to solve: process "/bin/sh -c apk update --no-cache" did not complete successfully: exit code: 2
```
