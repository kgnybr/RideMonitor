# RideMonitor 🚗💨

RideMonitor, aracınızın anlık verilerini (akü voltajı, sıcaklık, rakım ve basınç) 128x32 piksel bir OLED ekran üzerinde görüntülemenizi sağlayan Arduino tabanlı bir takip sistemidir. Bounce2 kütüphanesi ile optimize edilmiş tek bir buton üzerinden menüler arası geçiş yapılabilir.

---

## 🛠 Donanım Gereksinimleri

Bu projeyi hayata geçirmek için aşağıdaki bileşenlere ihtiyacınız olacak:

* **Arduino Nano** (Veya benzeri bir geliştirme kartı)
* **0.91" OLED Ekran** (128x32 piksel, I2C iletişimli - SSD1306)
* **BMP085 / BMP180** Basınç ve Sıcaklık Sensörü
* **Push Buton** (Menü değişimi için)
* **Voltaj Bölücü Devre:** Akü voltajını ölçmek için (Kodda 3.3kΩ ve 1kΩ dirençlere göre kalibre edilmiştir).
* **LED'ler (7 Adet):** Görsel bildirimler için (Pin 3-9 arası).

---

## 📌 Devre Bağlantıları

| Bileşen | Arduino Pin | Not |
| :--- | :--- | :--- |
| **OLED VCC** | 5V | |
| **OLED GND** | GND | |
| **OLED SCL** | A5 (veya SCL) | I2C Hattı |
| **OLED SDA** | A4 (veya SDA) | I2C Hattı |
| **BMP085 VCC** | 3.3V / 5V | Sensör modeline göre |
| **BMP085 SCL** | A5 | I2C Hattı |
| **BMP085 SDA** | A4 | I2C Hattı |
| **Buton** | Pin 10 | `INPUT_PULLUP` olarak tanımlıdır |
| **Voltaj Girişi** | A0 | Voltaj bölücü çıkışı |
| **LED Pins** | 3, 4, 5, 6, 7, 8, 9 | Durum göstergeleri |

---

## 🚀 Kurulum ve Kullanım

1.  **Kütüphaneleri Yükleyin:**
    Arduino IDE üzerinden aşağıdaki kütüphanelerin yüklü olduğundan emin olun:
    * `Adafruit_GFX`
    * `Adafruit_SSD1306`
    * `Adafruit_BMP085`
    * `Bounce2`

2.  **Kodu Yükleyin:** `RideMonitor.ino` dosyasını Arduino IDE ile açın ve kartınıza yükleyin.

3.  **Kullanım:** Cihaz açıldığında bir karşılama logosu (`menuWelcome`) ve ardından genel özet ekranı (`menuAIO`) görünür. Butona basarak şu menüler arasında gezinebilirsiniz:
    * **RPM:** Devir göstergesi 
    .
    * **Sıcaklık:** BMP sensöründen gelen ortam sıcaklığı (°C).
    * **Rakım:** Deniz seviyesinden yükseklik (Metre).
    * **Basınç:** Hava basıncı (hPa).
    * **Akü Voltajı:** Voltaj bölücü üzerinden okunan gerilim (V).

---

# RideMonitor 🚗💨 (English)

RideMonitor is an Arduino-based monitoring system that allows you to view your vehicle's real-time data (battery voltage, temperature, altitude, and pressure) on a 128x32 OLED display. It features a single-button interface optimized with the Bounce2 library for seamless menu navigation.

---

## 🛠 Hardware Requirements

To build this project, you will need the following components:

* **Arduino Nano** (Or equivalent development board)
* **0.91" OLED Display** (128x32 pixels, I2C interface - SSD1306)
* **BMP085 / BMP180** Pressure and Temperature Sensor
* **Push Button** (For menu switching)
* **Voltage Divider Circuit:** To measure battery voltage (Calibrated for 3.3kΩ and 1kΩ resistors).
* **LEDs (x7):** For visual feedback (Pins 3-9).

---

## 📌 Wiring Diagram

| Component | Arduino Pin | Note |
| :--- | :--- | :--- |
| **OLED VCC** | 5V | |
| **OLED GND** | GND | |
| **OLED SCL** | A5 (or SCL) | I2C Bus |
| **OLED SDA** | A4 (or SDA) | I2C Bus |
| **BMP085 VCC** | 3.3V / 5V | Depending on sensor model |
| **BMP085 SCL** | A5 | I2C Bus |
| **BMP085 SDA** | A4 | I2C Bus |
| **Button** | Pin 10 | Defined as `INPUT_PULLUP` |
| **Voltage Input** | A0 | Output of voltage divider |
| **LED Pins** | 3, 4, 5, 6, 7, 8, 9 | Status indicators |

---

## 🚀 Installation and Usage

1.  **Install Libraries:**
    Make sure the following libraries are installed in your Arduino IDE:
    * `Adafruit_GFX`
    * `Adafruit_SSD1306`
    * `Adafruit_BMP085`
    * `Bounce2`

2.  **Upload the Code:** Open `RideMonitor.ino` in the Arduino IDE and upload it to your board.

3.  **Usage:** Upon startup, a welcome logo is displayed followed by an All-in-One summary screen. Press the button to cycle through the following menus:
    * **RPM:** RPM display .
    * **Temperature:** Ambient temperature from BMP sensor (°C).
    * **Altitude:** Altitude above sea level (Meters).
    * **Pressure:** Atmospheric pressure (hPa).
    * **Battery Voltage:** Voltage read via voltage divider (V).

---

**Project Link:** [kgnybr/RideMonitor](https://github.com/kgnybr/RideMonitor)