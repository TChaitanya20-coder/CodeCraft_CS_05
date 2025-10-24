# CodeCraft_CS_05
This Python script demonstrates a simulated packet sniffer suitable for online compilers where live packet capture is not allowed. Traditional packet sniffing requires raw socket access, which online environments restrict. Therefore, we simulate packets to showcase packet analysis.
Introduction: This Python script demonstrates a simulated packet sniffer suitable for online compilers where live packet capture is not allowed. Traditional packet sniffing requires raw socket access, which online environments restrict. Therefore, we simulate packets to showcase packet analysis.

Components of the Script:

Packet Class:

class Packet:
    def __init__(self, ip_src, ip_dst, protocol, sport=None, dport=None, payload=""):
        self.ip_src = ip_src
        self.ip_dst = ip_dst
        self.protocol = protocol
        self.sport = sport
        self.dport = dport
        self.payload = payload

Represents a network packet with source/destination IP, protocol (TCP/UDP), source/destination ports, and payload.

Enables simulation of network traffic in environments without raw socket access.

analyze_packet Function:

def analyze_packet(packet):
    print("=" * 60)
    print("Time:", datetime.now().strftime("%Y-%m-%d %H:%M:%S"))
    print(f"IP: {packet.ip_src} → {packet.ip_dst}")
    print(f"{packet.protocol}: {packet.sport} → {packet.dport}")
    preview = packet.payload[:50]
    print("Payload:", preview)

Takes a Packet object and prints its details.

Prints timestamp, IP addresses, protocol info, and first 50 characters of payload.

main Function:

def main():
    print("Simulating packet capture...\n")


    packets = [
        Packet("192.168.1.2", "8.8.8.8", "TCP", 12345, 80, "GET / HTTP/1.1\r\nHost: example.com"),
        Packet("10.0.0.5", "10.0.0.1", "UDP", 54321, 53, "DNS Query for google.com"),
        Packet("172.16.0.2", "172.16.0.1", "TCP", 4444, 22, "SSH Connection Initiation"),
    ]


    for pkt in packets:
        analyze_packet(pkt)

Prints a message indicating simulated packet capture.

Creates a list of simulated Packet objects.

Loops through each packet and calls analyze_packet.

Execution:

if __name__ == "__main__":
    main()

Ensures the main() function runs when the script is executed.

Key Points:

Works in any online Python compiler.

Demonstrates packet capture and analysis logic without requiring raw network access.

Can be extended by adding more simulated packets or user input.

Maintains the same output format as a real packet sniffer for learning purposes.

Conclusion: This script serves as a learning tool for understanding packet sniffing in Python. While it does not capture real network traffic, it effectively demonstrates how to analyze packet information such as IP addresses, protocol, ports, and payloads.
