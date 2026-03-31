# ⚙️ Hybrid Hardware & Compiler Playground

> Rust tabanlı donanım tasarımı (Kaze) + TypeScript tabanlı C compiler (ts-c-compiler) birleşimi

---

## 🚀 Proje Hakkında

Bu proje, iki farklı ama güçlü yaklaşımı bir araya getirir:

* 🧠 **Donanım Tasarımı (HDL)** → Rust ile (Kaze)
* 💻 **Compiler Geliştirme** → TypeScript ile (ts-c-compiler)

Amaç:

> Yazılım ve donanım dünyasını tek bir projede birleştirmek

---

## 🔥 Kullanılan Teknolojiler

* Rust (Kaze - HDL)
* TypeScript (C Compiler)
* x86 (16-bit mimari)
* Assembly (NASM syntax)
* IR (Intermediate Representation)
* SSA Optimizer

---

## 🧩 Proje Bileşenleri

### 1. 🧠 Kaze (Hardware Description)

* Rust ile donanım devreleri tanımlama
* Verilog çıktısı üretme
* Simülasyon desteği

✔ Örnek kullanım:

```rust
let c = Context::new();
let m = c.module("Example");

let a = m.input("a", 1);
let b = m.input("b", 1);

m.output("out", a & b);
```

---

### 2. 💻 ts-c-compiler (C Compiler)

* TypeScript ile yazılmış C99 compiler
* Çok aşamalı (multi-pass) mimari
* IR + optimizer + backend içerir
* x86 16-bit binary üretir ([awesome.ecosyste.ms][1])

✔ Özellikler:

* Lexer + Parser + AST
* SSA tabanlı optimizasyon
* NASM uyumlu assembly üretimi
* 8086 emulator desteği

---

## 🔗 Proje Amacı

Bu birleşim ile:

* 🔹 Donanım + yazılım birlikte tasarlanabilir
* 🔹 Compiler → Assembly → Donanım akışı kurulabilir
* 🔹 FPGA / düşük seviye sistemlere geçiş yapılabilir

---

## ⚙️ Mimari

```
C Code
   ↓
ts-c-compiler
   ↓
Assembly (x86)
   ↓
Hardware Model (Kaze / Verilog)
   ↓
Simulation / FPGA
```

---

## 🎯 Kullanım Senaryoları

* 🧪 Eğitim (Compiler + Mikroişlemci)
* 🖥️ OS / Bootloader geliştirme
* ⚙️ FPGA prototipleme
* 🔬 Low-level sistem simülasyonu

---

## ⚠️ Uyarı

* ts-c-compiler: deneysel ve stabil değil ([awesome.ecosyste.ms][1])
* Kaze: araştırma / öğrenme amaçlı daha uygun

---

## 📦 Kurulum

### ts-c-compiler

```bash
yarn add @ts-cc/cli @ts-cc/machine
```

```bash
npx ts-c main.c -o output.bin
```

---

### Kaze

```bash
cargo add kaze
```

---

## 💣 Gelecek Planları

* [ ] Compiler → Verilog direkt dönüşüm
* [ ] FPGA entegrasyonu
* [ ] Mikroişlemci simülasyonu
* [ ] OS kernel çalıştırma

---

## 👤 Katkı

PR'lar her zaman açık 🔥

---
