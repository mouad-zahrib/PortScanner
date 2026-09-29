# 🔍 Python Port Scanner

A lightweight command-line TCP port scanner written in Python. It validates user input, scans a range of ports on a target IP address, and reports which ports are open.

Built as part of my cybersecurity learning path to understand how network reconnaissance works at the socket level.

## ✨ Features

- IP address validation using the `ipaddress` module
- Port range validation with regular expressions (format `<start>-<end>`, e.g. `20-28`)
- TCP connect scan using Python's `socket` library
- Configurable timeout (0.5s) for faster scans
- Clear feedback on invalid input, with re-prompt until the input is correct

## 🛠️ Technologies

- Python 3
- Standard library only: `socket`, `ipaddress`, `re` (no external dependencies)

## 🚀 Usage

```bash
python "Port scanner.py"
```

1. Enter the target IP address
2. Enter the port range to scan (e.g. `20-28`)
3. Open ports are listed at the end of the scan

### Example

```
Please enter the ip address that you want to scan: 192.168.100.212
You entered a valid ip address.
Please enter the range of ports you want to scan in format: <int>-<int> (ex would be 60-120)
Enter port range: 20-28
Port 22 is open on 192.168.100.212.
```


## 🧠 How it works

1. The script validates the IP with `ipaddress.ip_address()`.
2. The port range is parsed with a regex and converted to integers.
3. For each port, a TCP connection is attempted with `socket.connect()`.
4. If the connection succeeds, the port is considered open.

## 🔮 Possible improvements

- Multithreading to speed up large scans
- Validate that ports are within 0–65535 and that start ≤ end
- Service/banner identification for open ports
- Support for IPv6 and hostnames
- Command-line arguments (`argparse`) and export of results (CSV/JSON)

## ⚠️ Disclaimer

This tool is for **educational purposes only**. Only scan systems you own or have explicit permission to test. Unauthorized scanning may be illegal.

## 👤 Author

MOUAD ZAHRIB – [LinkedIn](https://linkedin.com/in/mouad-zahrib-5177a6252) · [GitHub](https://github.com/mouad-zahrib)
