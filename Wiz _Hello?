# Wiz CTF — Hello?

**Platform:** Wiz  
**Category:** Kubernetes / Network Traffic Analysis  
**Tools:** Linux, `tcpdump`

## Challenge Overview

The objective was to inspect network traffic in a Kubernetes environment and find a hidden flag transmitted between services.

## Step 1: Identify Network Interfaces

```bash
ip -br addr
```

The output revealed an additional network interface named `ns-9027e3`.

## Step 2: Capture Network Traffic

```bash
tcpdump -i ns-9027e3 -nn -A -c 20
```

**Command explanation:**
- `-i`: Select the network interface.
- `-nn`: Disable name and port resolution.
- `-A`: Display packet payloads as ASCII text when possible.
- `-c 20`: Capture 20 packets before stopping.

## Step 3: Inspect HTTP Traffic

The packet capture revealed an HTTP POST request sent to `reporting-service` on port 80.

The request body contained the challenge flag in readable text.

## Step 4: Flag

```text
wiz_k8s_lan_party{good-crime-comes-with-a-partner-in-a-sidecar}
```

## Key Learnings

- Network interface inspection using `ip`.
- Packet capture and analysis using `tcpdump`.
- Identifying DNS queries and HTTP requests.
- Understanding shared network namespaces and sidecar communication.
- Recognizing the risks of transmitting sensitive information over unencrypted HTTP.

## Conclusion

I successfully completed the challenge by capturing network traffic and inspecting HTTP payloads to identify the hidden flag.

This hands-on exercise strengthened my understanding of network traffic analysis in Kubernetes environments.
