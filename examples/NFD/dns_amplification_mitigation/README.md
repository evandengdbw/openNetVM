DNSAmplificationMitigation
==
DNS Amplification Mitigation developed by the NFD framework


NFD is a NF developing framework, consisting two parts, NFD language and NFD compiler. NFD compiler translate <br>
the NF model file wiiten in NFD language, a table-form language, into standard runtime environment(such as C++).<br><br>


DNS Amplification Mitigation is translated from the `DNSAmplificationMitigationModel.txt` to C++ environment. <br>
 
 
 <br>
An attacker uses a spoofed server IP to request many DNS queries that result in large answers to that DoS the server with the spoofed IP. Mitigation is by tracking if the server actually committed this request. In this program, we use a map to track all the real DNS requests from the server with the spoofed IP and pass the real DNS responses while block the responces due to attacker. 


Compilation and Executionthe 
--

To run this NF, you should use either clang++ or g++ to compile this NF developed by C++.

```
cd heavy_hitter_detection
make

```

Then, you can run this code.

```
./go.sh CORELIST SERVICE_ID DST [PRINT_DELAY]

OR

./go.sh -F CONFIG_FILE -- -- -d DST [-p PRINT_DELAY]

OR

sudo ./build/stateful_firewall -l CORELIST -n 3 --proc-type=secondary -- -r SERVICE_ID -- -d DST [-p PRINT_DELAY]
```

App Specific Arguments
--
  - `-d <dst>`: destination service ID to foward to
  - `-p <print_delay>`: number of packets between each print, e.g. `-p 1` prints every packets.

Config File Support
--
This NF supports the NF generating arguments from a config file. For additional reading, see [Examples.md](../../docs/Examples.md)

See `../example_config.json` for all possible options that can be set.
