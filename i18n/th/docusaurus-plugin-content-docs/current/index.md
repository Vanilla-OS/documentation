---
title: เอกสารอ้างอิงของ Vanilla OS 
description: เรียนรู้วิธีใช้งาน Vanilla OS พร้อมทั้งเครื่องมือและการตั้งค่าต่างๆ
sidebar_position: 1
---

# Vanilla OS

รับประสบการณ์ GNOME แบบดั้งเดิมบน Ubuntu พร้อมกับการปรุงแต่งเพิ่มเติม

## คำถามที่พบบ่อย

คำตอบสำหรับคำถามที่พบบ่อย (ถึงแม้ว่าโปรเจกต์นี้จะยังมีอายุน้อยก็ตาม).
- **ทำไมต้องสร้างระบบใหม่ด้วย?**<br />
  Vanilla OS เกิดขึ้นจากความต้องการระบบที่มีพื้นฐานจาก Ubuntu Linux ที่ใช้ GNOME แบบดั้งเดิม
  โดยที่ไม่มีการเปลี่ยนแปลงต่อประสบการณ์การใช้งาน และในภายหลังมีการเพิ่มเทคโนโลยีและเครื่องมืออื่นๆ เช่น Almost (การล็อคไฟล์ระบบตามความต้องการ) และ Apx (ตัวจัดการแพคเกจที่มีพื้นฐานบน Distrobox)
- **มันใช้ OSTree หรือเปล่า?**<br />
  ไม่, Vanilla OS ล็อคไฟล์ระบบผ่าน [`almost`](https://github.com/Vanilla-OS/almost). 
  เราสร้างเครื่องมือนี้สำหรับการล็อคไฟล์ระบบตามความต้องการตามคุณสมบัติของไฟล์
  ซึ่งวิธีนี้ทำให้สามารถล็อคไฟล์บนระบบไฟล์แบบใดก็ได้ แต่อาจมีการพิจารณาการใช้งาน OSTree ในอนาคต
- **ใช้การปล่อยเวอร์ชั่นแบบ Rolling Release (ไม่มีเวลากำหนดแน่นอน) ไหม?**<br />
  ไม่, Vanilla OS มีการปล่อยเวอร์ชั่นใหม่ตาม Ubuntu

## หัวข้อ

- **[การล็อคไฟล์ระบบ (`almost`)](/almost)**<br />
Almost เป็นเครื่องมือที่ใช้ในการล็อคไฟล์ระบบตามความต้องการตามคุณสมบัติของไฟล์

- **[ตัวจัดการแพคเกจ (`apx`)](/apx/)**<br />
Apx เป็นตัวจัดการแพคเกจที่ให้คุณติดตั้งและจัดการแพคเกจในพื้นที่ที่จำกัด โดยไม่ยุ่งกับไฟล์ของระบบ แต่ก็สามารถใช้ Apx ในการติดตั้งแพคเกจบนระบบโดยไม่ผ่านตัวจำกัดได้