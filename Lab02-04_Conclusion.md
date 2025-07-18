# สรุปผลและคำถามท้ายการทดลอง

## สรุปผลการทดลอง



## คำถามท้ายการทดลอง

1. นักศึกษาได้เรียนรู้อะไรบ้างเกี่ยวกับความแตกต่างและคุณสมบัติของชนิดข้อมูลแต่ละประเภทบน ESP32 (เช่น int, float, char, bool, long, long long, unsigned int, byte, double)

ชนิดข้อมูลแต่ละประเภทบน ESP32 มีขนาดและขอบเขตต่างกัน เช่น int/long ใช้ 4 ไบต์, double ใช้ 8 ไบต์, char ใช้ 1 ไบต์ และ bool ใช้ 1 ไบต์
2. ความสำคัญของการเลือกใช้ชนิดข้อมูลที่เหมาะสมในการเขียนโปรแกรมคืออะไร?

เลือกชนิดข้อมูลให้เหมาะสมช่วยประหยัดหน่วยความจำ เพิ่มความถูกต้อง และป้องกันข้อผิดพลาด
3. ถ้านักศึกษาต้องการเก็บค่าเวลา (เป็นมิลลิวินาที) ซึ่งอาจมีค่าสูงถึงหลายพันล้านมิลลิวินาที นักศึกษาควรใช้ชนิดข้อมูลใดบน ESP32

เก็บเวลาเป็นมิลลิวินาทีที่สูงมาก ควรใช้ unsigned long long เพราะเก็บค่าบวกขนาดใหญ่ได้
4. อธิบายความแตกต่างระหว่าง float และ double ในแง่ของขนาดหน่วยความจำและความแม่นยำ

float ใช้ 4 ไบต์ ความแม่นยำ 6-7 ตำแหน่งทศนิยม ส่วน double ใช้ 8 ไบต์ แม่นยำสูงกว่า 15-16 ตำแหน่ง
5. อธิบายแนวคิดเรื่อง "Overflow" และ "Underflow" ที่เกิดขึ้นกับชนิดข้อมูลจำนวนเต็ม (เช่น int, byte) พร้อมยกตัวอย่างจากใบงานนี้

Overflow คือค่าที่เกินขอบเขตสูงสุดวนกลับมาเริ่มต้นใหม่ เช่น int เกิน 2147483647; Underflow คือค่าต่ำสุดที่ต่ำกว่าขอบเขตวนกลับ เช่น ต่ำกว่า -2147483648
6. การทราบขนาดของชนิดข้อมูลด้วย sizeof() มีประโยชน์อย่างไรในการเขียนโปรแกรมสำหรับไมโครคอนโทรลเลอร์ที่มีหน่วยความจำจำกัด?

sizeof() ช่วยรู้ขนาดข้อมูลจริง เพื่อเลือกชนิดข้อมูลให้เหมาะสมกับหน่วยความจำที่จำกัด
