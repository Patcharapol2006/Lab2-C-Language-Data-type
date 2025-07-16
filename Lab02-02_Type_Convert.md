# ใบงานที่ 02.02 การคำนวณและแปลงชนิดข้อมูลเบื้องต้น


### 1. การคำนวณด้วยชนิดข้อมูลต่างกัน (Type Promotion)

__วัตถุประสงค์__ 

ทำความเข้าใจว่าการคำนวณระหว่างชนิดข้อมูลต่างกันมีผลลัพธ์อย่างไร

- โค้ดที่ต้องเพิ่มใน `setup()` โดยลบโค้ดเดิมออก ยกเว้นบรรทัด `Serial.begin(115200);`


``` c
Serial.println("\n--- ทดสอบการคำนวณระหว่างชนิดข้อมูล ---");
int numA = 10;
float numB = 3.0;
double numC = 3.0;

float resultFloat = numA / numB; // int หาร float ผลลัพธ์จะเป็น float
Serial.print("10 / 3.0 (ผลลัพธ์ float): ");
Serial.println(resultFloat, 2);

double resultDouble = numA / numC; // int หาร double ผลลัพธ์จะเป็น double
Serial.print("10 / 3.0 (ผลลัพธ์ double): ");
Serial.println(resultDouble, 10);

int resultInt = numA / (int)numB; // int หาร int ผลลัพธ์จะเป็น int (ทศนิยมถูกตัดทิ้ง)
Serial.print("10 / (int)3.0 (ผลลัพธ์ int): ");
Serial.println(resultInt);
```

- ดำเนินการจำลองตามวิธีที่ได้ทดลองมาแล้ว

__คำถาม__ 

1.1  ทำไม 10 / 3.0 (เมื่อตัวหารเป็น float หรือ double) ถึงได้ผลลัพธ์เป็นทศนิยม แต่เมื่อตัวหารถูกแปลงเป็น int แล้วผลลัพธ์เป็นจำนวนเต็ม?



10 / 3.0 ได้ผลลัพธ์เป็นทศนิยมเพราะ 3.0 เป็น float หรือ double ทำให้การหารเป็นจำนวนจริง
แต่ถ้าแปลงเป็น int (10 / 3) จะเป็นการหารจำนวนเต็ม ตัดทศนิยมทิ้ง ทำให้ได้ผลลัพธ์เป็นจำนวนเต็ม














### 2. การแปลงชนิดข้อมูล (Explicit Type Casting)

__วัตถุประสงค์__ 

ฝึกการแปลงชนิดข้อมูลด้วยตัวเอง

- โค้ดที่ต้องเพิ่มใน `setup()` โดยลบโค้ดเดิมออก ยกเว้นบรรทัด `Serial.begin(115200);`


``` c
Serial.println("\n--- ทดสอบการแปลงชนิดข้อมูล (Type Casting) ---");
float temperatureCelsius = 25.789;
Serial.print("อุณหภูมิ Celsius (float): ");
Serial.println(temperatureCelsius);

int temperatureInteger = (int)temperatureCelsius; // แปลง float เป็น int
Serial.print("อุณหภูมิ Celsius (แปลงเป็น int): ");
Serial.println(temperatureInteger);

// ตัวอย่างการใช้ char เป็นตัวเลข
char letter = 'P';
int asciiValue = (int)letter;
Serial.print("อักขระ 'P' มีค่า ASCII: ");
Serial.println(asciiValue);

// ตัวอย่างการแปลง int เป็น float
int count = 7;
int total = 20;
float average = (float)count / total; // ต้องแปลงอย่างน้อยหนึ่งตัวให้เป็น float ก่อนหาร
Serial.print("ค่าเฉลี่ย (7/20): ");
Serial.println(average);
```

- ดำเนินการจำลองตามวิธีที่ได้ทดลองมาแล้ว


__คำถาม__

- ในการเขียนโปรแกรม ต้องทำ Type Casting ในสถานการณ์ใดบ้าง

- Type Casting จำเป็นเมื่อ:

ต้องการเปลี่ยนชนิดข้อมูลเพื่อให้ตัวแปรหรือค่าตรงกับชนิดที่ฟังก์ชันหรือการคำนวณต้องการ

ต้องการบังคับแปลงชนิดข้อมูล เช่น แปลงจาก float เป็น int เพื่อตัดทศนิยม

เมื่อต้องการหลีกเลี่ยงข้อผิดพลาดหรือผลลัพธ์ที่ไม่ถูกต้องจากการคำนวณระหว่างชนิดข้อมูลต่างกัน

ต้องการแปลงข้อมูลเพื่อการแสดงผลหรือจัดเก็บ เช่น จาก int เป็น float เพื่อให้แสดงทศนิยม
