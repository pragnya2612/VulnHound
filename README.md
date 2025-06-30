# VulnHound
import socket

# Target IP
target = input("Enter target IP address: ")

# Port range
start_port = 1
end_port = 1024

print(f"Scanning {target} for open ports from {start_port} to {end_port}...\n")

# Scan each port in range
for port in range(start_port, end_port + 1):
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    s.settimeout(0.5)
    result = s.connect_ex((target, port))
    if result == 0:
        print(f"Port {port} is OPEN")
    s.close()

print("\nScan complete.")
