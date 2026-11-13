# ระบบคลังย่อย (Sub-Store) โรงพยาบาลศูนย์การแพทย์ มหาวิทยาลัยวลัยลักษณ์

หน้าเว็บสำหรับเบิก จ่าย ตัดใช้ ตรวจยอดคงเหลือ และ Dashboard ผู้บริหาร
ฐานข้อมูลอยู่ที่ Supabase โปรเจกต์ `wuh-substore`

- เว็บ: https://rainbow-wuh.github.io/wuh-substore/
- ฐานข้อมูล: https://supabase.com/dashboard/project/oxcrpbmcmzfomsclmdng

## ไฟล์

| ไฟล์ | หน้าที่ |
| --- | --- |
| `index.html` | หน้าเว็บทั้งหมด (HTML + JavaScript ไฟล์เดียว) |
| `.nojekyll` | บอก GitHub Pages ให้ส่งไฟล์ตามเดิม ไม่ต้องแปลง |

## บทบาทผู้ใช้

| role | ทำอะไรได้ |
| --- | --- |
| `requester` | เบิกของ ตัดใช้ ดูยอดคงเหลือคลังตนเอง |
| `unit_head` | เหมือนผู้เบิก + อนุมัติใบเบิกของหน่วย |
| `main_store` | รับเข้า จ่ายตามใบเบิก จัดการสินค้าและ Min/Max ดูทุกคลัง |
| `manager` | Dashboard อนุมัติใบปรับยอด ดูทุกคลัง |
| `admin` | ทุกอย่าง + จัดการคลังและผู้ใช้ |

## หมายเหตุความปลอดภัย

คีย์ Supabase ใน `index.html` เป็นคีย์สาธารณะ (publishable key) ที่ออกแบบให้อยู่ในหน้าเว็บได้
ข้อมูลถูกป้องกันด้วยการล็อกอินและ Row Level Security ในฐานข้อมูล
ห้ามนำคีย์ `service_role` หรือ secret key มาใส่ในไฟล์นี้
