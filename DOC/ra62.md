### RA01 / RA62 系列模塊

| ProMicro | LORA PIN | HT-RA62 HF<br>(SX1262) | RA-01SCH<br>(**`LLCC68`**) | RA-01SH<br>(SX1262) | RA-01SH-P<br>(SX1262) | RA-01SCH-P<br>(**`LLCC68`**) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| | PIN1 | ANT | ANT | ANT | **`ANF`** | **`ANF`** |
| | PIN2 | GND | GND | GND | GND | GND |
| | PIN3 | 3.3V<br>(**`>150 mA`**) | 3.3V<br>(>200 mA) | 3.3V<br>(>200mA) | ⚠️ 3.3V<br>(**`> 1A`**) | ⚠️ 3.3V<br>(**`> 1A`**) |
| D10/P0.09 | PIN4 | **`RST`** | RESET | RESET | RESET | RESET |
| **NC** | PIN5 | TXEN | TXEN | TXEN | 🔴 **`VCCPA`** | 🔴 **`VCCPA`** |
| D16/P0.10 | PIN6 | DIO1 | DIO1 | DIO1 | DIO1 | DIO1 |
| **NC** | PIN7 | DIO2 | DIO2 | DIO2 | DIO2 | DIO2 |
| **NC** | PIN8 | DIO3 | DIO3 | DIO3 | DIO3 | DIO3 |
| | PIN9 | GND | GND | GND | GND | GND |
| D20/P0.29 | PIN10 | BUSY | BUSY | BUSY | BUSY | BUSY |
| ~~D2/P0.17~~<br>**NC** | PIN11 | RXEN<br>(NC) | RXEN<br>(NC) | RXEN<br>(NC) | 🔴 **`RF_EN`**<br>(NC) | 🔴 **`RF_EN`**<br>(NC) |
| D14/P1.11 | PIN12 | SCK | SCK | SCK | SCK | SCK |
| D19/P0.02 | PIN13 | MISO | MISO | MISO | MISO | MISO |
| D18/P1.15 | PIN14 | MOSI | MOSI | MOSI | MOSI | MOSI |
| D15/P1.13 | PIN15 | NSS | NSS | NSS | NSS | NSS |
| | PIN16 | GND | GND | GND | GND | GND |
| | **功率** | 22 dbm | 22 dbm | 22 dbm | 🔥 **`29 dbm`** | 🔥 **`29 dbm`** |

#### 腳位與供電說明

* **PIN3 (電源與電流需求)**：
  * **RA62**：3V3 pin (≥150mA)
  * **RA-01SH-P**：建議電壓 3.3V，峰值電流需大於 1A；若使用 DC-DC 供電，建議將紋波 (ripple) 控制在 100mV 以內。
  * **RA-01SCH-P**：建議電壓 3.3V，峰值電流需大於 1A；若使用 DC-DC 供電，建議將紋波 (ripple) 控制在 100mV 以內。
  * **RA-01SH**：建議電壓 3.3V，峰值電流需大於 200mA；建議使用 LDO 供電，若使用 DC-DC 則建議將紋波控制在 30mV 以內。
  * **RA-01SCH**：建議電壓 3.3V，峰值電流需大於 200mA；建議使用 LDO 供電，若使用 DC-DC 則建議將紋波控制在 30mV 以內。
* **PIN5 (TXEN / VCCPA)**：
  * **22 dbm 模組**：TXEN 與 DIO2 短接（與開發板無關）。
  * **29 dbm 模組**：VCCPA 電壓規格為 3.0V / 5.0V / 5.25V (min / typical / max)。
* **PIN7 (DIO2)**：
  * **22 dbm 模組**：TXEN 與 DIO2 短接（與開發板無關）。
  * **29 dbm 模組**：NC（空接）。
* **PIN11 (RXEN / RF_EN)**：
  * **22 dbm 模組**：~~LORA RXEN 與 promicro D2 連接（非必要）~~。若所選模組已具備內建射頻切換 (internal RF switching)，則無需連接 RXEN。
  * **29 dbm 模組**：NC（RF_EN 預設為 HIGH）。
* **PIN15 (NSS)**：對應 SPI 的 CS（晶片選擇）腳位。
* **功率規格補充 (RA-01SH-P)**：
  * **3.3V 版本**：29 dbm (3.3V 750mA)
  * **5V 版本**：31 dbm (5V 1000mA)
