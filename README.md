# Script setup WireGuard VPN on ubuntu server 22.04 LTS.
1. **SSH vào server**
2. **Cập nhật hệ thống:**
   - **Command**:
     ```bash
     sudo apt update && sudo apt upgrade -y
     ```
3. **Script cài đặt:**
   - **Command**:
     ```bash
     sudo apt-get install wget -y
     ```
     ```bash
     wget -qO- https://raw.githubusercontent.com/quangtrangvn/WireGuard/main/wireguard-install.sh -O wireguard-install.sh
     ```
      ```bash
     sudo bash wireguard-install.sh
     ```
4. **Để tạo nhiều client một lần thay vì tạo từng client một, có thể tùy chỉnh script WireGuard để tạo nhiều cấu hình client tự động:**
   - Script cài đặt WireGuard và tạo nhiều client
Lưu ý: Đảm bảo rằng đã cài đặt WireGuard trước khi chạy script này.
Tạo file script 
   - **Command**:
     ```bash
     wget -qO- https://raw.githubusercontent.com/quangtrangvn/WireGuard/main/create-multiple-clients.sh -O create-multiple-clients.sh
     ```
   - **Cấp quyền thực thi cho script:**:
     ```bash
     chmod +x create-multiple-clients.sh
     ```
   - **Chạy script:**:
     ```bash
     sudo ./create-multiple-clients.sh
     ```
Chú ý:
- Script sẽ tự động lấy địa chỉ IP công khai của máy chủ và điền vào file cấu hình client.
- Đảm bảo rằng máy chủ của bạn có kết nối Internet để script có thể hoạt động đúng cách.
- File cấu hình client sẽ được tạo tại /etc/wireguard/clients/ Bạn có thể copy file này sang thiết bị client và import vào ứng dụng WireGuard.
