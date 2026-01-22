# F5 BIG-IP Cookie Decoder

[繁體中文](#繁體中文) | [English](#english)

---

## <a id="繁體中文"></a>繁體中文

### 簡介
這是一個簡單的網頁工具，用於解碼 F5 BIG-IP 負載平衡器的 Persistence Cookie。透過解碼這些 Cookie，您可以取得後端真實伺服器的 IP 位址與連接埠 (Port)。

### 功能
- **解碼 Cookie**: 將加密的 F5 Cookie 轉換為可讀的 IP 和 Port。
- **格式支援**: 支援直接貼上 Cookie 值 (例如 `1677787402.36895.0000`) 或完整的 Cookie 字串 (例如 `BIGipServerpool=...`)。
- **純前端運作**: 所有計算皆在瀏覽器端使用 JavaScript 完成，資料不會傳送至外部伺服器，安全無虞。

### 如何使用
1. 下載此專案或直接開啟 `index.html` 檔案。
2. 在輸入框中貼上 F5 BIG-IP Cookie。
3. 點擊「解碼」按鈕。
4. 結果將顯示在下方區域。

### 技術原理
F5 BIG-IP 預設將後端 IP 與 Port 編碼為十進位數字。此工具依照 [F5 K6917](https://my.f5.com/manage/s/article/K6917) 文件所述的演算法進行反向解碼：
1. 將十進位轉為十六進位。
2. 進行 Byte-swapping (反轉位元組)。
3. 轉回十進位格式以還原 IP 與 Port。

### 授權
本專案採用 [MIT License](LICENSE) 授權。

---

## <a id="english"></a>English

### Introduction
A simple web-based tool to decode F5 BIG-IP Persistence Cookies. By decoding these cookies, you can reveal the real IP address and port of the backend server.

### Features
- **Decode Cookies**: Converts encoded F5 cookies into readable IP addresses and ports.
- **Flexible Input**: Supports pasting just the cookie value (e.g., `1677787402.36895.0000`) or the full cookie string (e.g., `BIGipServerpool=...`).
- **Client-Side Only**: All processing is done locally in your browser using JavaScript. No data is sent to any server.

### How to Use
1. Download this repository or open `index.html` directly in your browser.
2. Paste the F5 BIG-IP Cookie into the input field.
3. Click the "Decode" button.
4. The result will be displayed below.

### Technical Details
F5 BIG-IP encodes the backend IP and Port into decimal numbers by default. This tool reverses the encoding based on the [F5 K6917](https://my.f5.com/manage/s/article/K6917) article:
1. Convert Decimal to Hexadecimal.
2. Perform Byte-swapping.
3. Convert back to Decimal to retrieve the IP and Port.

### License
This project is licensed under the [MIT License](LICENSE).
