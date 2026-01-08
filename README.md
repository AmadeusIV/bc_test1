# BC Test1 - Dự án Blockchain với React và Truffle

Dự án kết hợp React frontend và Truffle smart contracts để tạo ứng dụng blockchain đơn giản với contract SimpleStorage.

## 📋 Mô tả

Dự án này bao gồm:
- **Frontend**: React application (Create React App)
- **Smart Contracts**: Solidity contracts được quản lý bởi Truffle
- **Contract**: SimpleStorage - Contract đơn giản để lưu trữ và truy xuất dữ liệu

## 🔧 Yêu cầu hệ thống

Trước khi bắt đầu, bạn cần cài đặt:

- **Node.js** (phiên bản 14.x trở lên) - [Download](https://nodejs.org/)
- **npm** hoặc **yarn** (thường đi kèm với Node.js)
- **Truffle** - Framework để phát triển blockchain
- **Ganache** (tùy chọn) - Blockchain local để test

## 🚀 Cài đặt

### 1. Clone repository

```bash
git clone https://github.com/AmadeusIV/bc_test1.git
cd bc_test1
```

### 2. Cài đặt dependencies

```bash
# Cài đặt dependencies cho React app
npm install

# Cài đặt Truffle globally (nếu chưa có)
npm install -g truffle
```

### 3. Cấu hình Ganache (Cho local development)

Nếu bạn chưa có Ganache:
- Download và cài đặt [Ganache](https://trufflesuite.com/ganache/)
- Hoặc cài đặt qua npm: `npm install -g ganache`

Khởi động Ganache:
- Mở Ganache GUI hoặc chạy: `ganache-cli`
- Đảm bảo Ganache chạy trên port **7545** (theo cấu hình trong `truffle-config.js`)

## 📁 Cấu trúc dự án

```
bc_test1/
├── contracts/              # Smart contracts (Solidity)
│   ├── Migrations.sol      # Contract migration
│   └── SimpleStorage.sol   # Contract chính để lưu trữ dữ liệu
├── migrations/             # Scripts để deploy contracts
│   ├── 1_initial_migration.js
│   └── 2_deploy_simple_storage.js
├── build/                  # Compiled contracts (tự động tạo)
├── public/                 # Static files cho React app
├── src/                    # Source code React app
├── test/                   # Test files (chưa có)
├── truffle-config.js       # Cấu hình Truffle
└── package.json            # Dependencies và scripts
```

## 🎯 Sử dụng

### Chạy React App

```bash
npm start
```

Ứng dụng sẽ chạy tại [http://localhost:3000](http://localhost:3000)

### Compile Smart Contracts

```bash
truffle compile
```

Contracts đã compile sẽ được lưu trong thư mục `build/contracts/`

### Deploy Smart Contracts lên Ganache

```bash
# Đảm bảo Ganache đang chạy trước
truffle migrate

# Hoặc deploy lại từ đầu
truffle migrate --reset
```

### Test Smart Contracts

```bash
truffle test
```

### Truffle Console (Tương tác với contracts)

```bash
truffle console
```

Trong console, bạn có thể:
```javascript
// Lấy instance của contract
let instance = await SimpleStorage.deployed();

// Lấy giá trị hiện tại
let value = await instance.get();
console.log(value.toString());

// Set giá trị mới
await instance.set(200);

// Lấy lại giá trị
let newValue = await instance.get();
console.log(newValue.toString());
```

## 📝 Smart Contract - SimpleStorage

### Chức năng

- `get()`: Trả về giá trị hiện tại được lưu trữ
- `set(uint256 _value)`: Đặt giá trị mới
- `storedData`: Biến public để xem giá trị trực tiếp

### Deploy

Contract được deploy với giá trị khởi tạo là **100** (theo `migrations/2_deploy_simple_storage.js`)

## 🤝 Làm việc nhóm với Git

### Lần đầu clone và setup

```bash
git clone https://github.com/AmadeusIV/bc_test1.git
cd bc_test1
npm install
```

### Các lệnh Git thường dùng

```bash
# Kiểm tra trạng thái
git status

# Lấy code mới nhất từ GitHub
git pull origin main

# Thêm file/thay đổi vào staging
git add .

# Commit thay đổi
git commit -m "Mô tả thay đổi"

# Push lên GitHub
git push origin main
```

### Chia sẻ repository với người khác

**Cách 1: Chia sẻ công khai**
- Vào GitHub → Settings → Change visibility → Make public
- Chia sẻ link: `https://github.com/AmadeusIV/bc_test1`

**Cách 2: Thêm Collaborators**
- Vào GitHub → Settings → Collaborators → Add people
- Nhập username GitHub của người cần chia sẻ
- Họ sẽ nhận email mời và có quyền push/pull

## 🔗 Tài liệu tham khảo

- [Truffle Documentation](https://trufflesuite.com/docs/truffle/)
- [React Documentation](https://reactjs.org/)
- [Solidity Documentation](https://docs.soliditylang.org/)
- [Web3.js Documentation](https://web3js.readthedocs.io/)

## 📄 License

MIT

## 👤 Tác giả

- GitHub: [@AmadeusIV](https://github.com/AmadeusIV)

---

**Lưu ý**: Đảm bảo Ganache hoặc blockchain network của bạn đang chạy trước khi deploy contracts!
