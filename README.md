# pfSense – Prerequisites and Installation

This tutorial outlines the prerequisites and initial installation of a **pfSense-based network security lab**. This phase focuses on setting up the virtual environment, configuring network adapters, and verifying base connectivity before implementing VLANs and firewall rules.

---

## Environments and Technologies Used

- VirtualBox
- pfSense Firewall
- Kali Linux
- GNS3
- SolarPutty
- Virtual Networking (Internal / Host-Only)

---

## Operating Systems Used

- pfSense
- Kali Linux
- Ubuntu (Client VM)

---

## List of Prerequisites

- **VirtualBox:** Hypervisor used to host all virtual machines.
- **pfSense ISO:** Firewall and routing platform used to control network traffic.
- **Kali Linux ISO:** Attacker machine used for later testing.
- **GNS3:** Network simulation tool for building and visualizing topology.
- **Host-Only & Internal Adapters:** Required for isolated lab communication.

---

## OVERVIEW

1. Configure VirtualBox networking.
2. Set up GNS3 and base network topology.
3. Install and configure pfSense.
4. Configure Kali Linux networking.
5. Verify connectivity between devices.

---

## 1. VirtualBox Network Configuration

- Configure **Host-Only Adapter**:
  - IP Address: `192.168.56.1`
- Configure **Internal Network adapters** for lab isolation.
- Ensure all lab machines connect through pfSense.

---

## 2. GNS3 Setup and Base Topology

- Launch GNS3 and create a new project.
- Use the left-side toolbar to drag network components.
- Enable grid view for alignment.
- Configure Virtual PCs:
  - PC1 IP: `10.1.1.1/24`
  - PC2 IP: `10.1.1.2/24`
- Verify connectivity:
  - Ping between PC1 and PC2.
- Save the topology using the `save` command.

---

## 3. pfSense Initial Setup

- Configure pfSense network adapters:
  - Adapter 1: NAT
  - Adapter 2: Internal Network (`lan0`)
  - Adapter 3: Internal Network (`lan1`)
  - Adapter 4: Internal Network (`lan2`)
- Disable promiscuous mode.
- Complete pfSense setup wizard:
  - Set hostname
  - Change time zone
  - Disable DNS override
  - Allow private networks (RFC1918)

---

## 4. Kali Linux Network Configuration

- Set Kali Linux Adapter 1 to **Internal Network (`lan0`)**.
- Verify Kali receives an IP address.
- Test connectivity:
  - Ping pfSense gateway (`10.0.0.1`).
- Access pfSense web interface via browser.

---

## 5. Verification and Validation

Confirm the following before proceeding to Phase 2:

- pfSense LAN IP is `10.0.0.1/24`
- Kali Linux has an IP in the `10.0.0.0/24` range
- Kali can ping pfSense
- Ubuntu client can access the internet (`8.8.8.8`)

---

## Conclusion

This phase establishes the foundation of the network security lab by configuring the virtual environment, installing pfSense, and verifying basic connectivity. With the base network operational, the lab is ready for **VLAN configuration, firewall rule creation, and network segmentation** in Phase 2.
