### E22 M22S系列模塊

| promicro NRF52840 | LORA PIN | E-BYTE<br>E22-900M22S<br>(`SX126X`) | E-BYTE<br>E220-900M22S<br>(**`LLCC68`**) | 大夏龍雀<br>DX-LR30<br>(**`SX1262`**) | 大夏龍雀<br>DX-LR20<br>(**`LLCC68`**) |
| :--- | :---: | :---: | :---: | :---: | :---: |
| | PIN 1 | GND | GND | GND | GND |
| | PIN 2 | GND | GND | GND | GND |
| | PIN 3 | GND | GND | GND | GND |
| | PIN 4 | GND | GND | GND | GND |
| | PIN 5 | GND | 🔴 **`DIO3`** | 🔴 **`DIO3`** | 🔴 **`DIO3`** |
| D2/P0.17 | PIN 6 | RXEN | RXEN | RXEN | RXEN |
| NC | PIN 7 | TXEN | TXEN | TXEN | TXEN |
| NC | PIN 8 | DIO2 | DIO2 | DIO2 | DIO2 |
| | PIN 9 | VCC<br>(**`>3.0V`**保證輸出功率，不可超過 3.7V)<br>@22dbm: **`100~140mA`** | VCC<br>(**`>3.3V`**保證輸出功率，不可超過 3.7V)<br>**`130mA`** | VCC<br>(**`>3.3V`**保證輸出功率，不可超過 3.7V)<br>**`100mA`** | VCC<br>(**`>3.3V`**保證輸出功率，不可超過 3.7V)<br>**`100mA`** |
| | PIN 10 | GND | GND | GND | GND |
| | PIN 11 | GND | GND | GND | GND |
| | PIN 12 | GND | GND | GND | GND |
| D16/P0.10 | PIN 13 | DIO1 | DIO1 | DIO1 | DIO1 |
| D20/P0.29 | PIN 14 | BUSY | BUSY | BUSY | BUSY |
| D10/P0.09 | PIN 15 | NRST | NRST | NRST | NRST |
| D19/P0.02 | PIN 16 | MISO | MISO | MISO | MISO |
| D18/P1.15 | PIN 17 | MOSI | MOSI | MOSI | MOSI |
| D14/P1.11 | PIN 18 | SCK | SCK | SCK | SCK |
| D15/P1.13 | PIN 19 | NSS | NSS | NSS | NSS |
| | **功率** | 22 dbm | 22 dbm | 22 dbm | 22 dbm |
| | **傳輸距離**<br>(官方文件) | **`6 KM`** | **`5.5 KM`** | ⚠️ **`8 KM`** | ⚠️ **`8 KM`** |

#### REMARK 說明

- **PIN 5 (DIO3)**：DIO3 懸空 NC 處理[cite: 2]。
- **PIN 6 / PIN 7 / PIN 8 (RXEN / TXEN / DIO2)**：這三支腳用來控制 LORA 收發（沒處理好會打架 / 會無法發射訊號），有三種處理方式[cite: 2]：
  - **(1) 半自動控制**：TXEN / DIO2 短接，RXEN 接到 D2(P0.17)[cite: 2]。
  - **(2) 全自動控制 (邏輯 IC)**：TXEN / DIO2 短接，且 DIO2 到邏輯 IC 的 IN，RXEN 接到邏輯 IC 的 OUT[cite: 2]。
  - **(3) 全自動控制 (CMOS)**：參考 mesh mess 電路[cite: 2]。
- **PIN 9 (VCC)**：+3.3 V[cite: 2]。
- **PIN 13 (DIO1)**：IRQ[cite: 2]。
- **PIN 15 (NRST)**：NRST / RST / RESET[cite: 2]。
- **PIN 18 (SCK)**：CS[cite: 2]。
