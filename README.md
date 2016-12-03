คำตอบ 
(1.)ไม่เห็นด้วย เพราะ ในยุคสมัยนี้คนส่วนมากต้องการความสะดวกและรวดเร็ว  ซึ่ง การทำ agile เป็นซอฟแวร์ที่ตอบโจทย์มากในสมัยนี้ ซึ่งจะเน้นว่าใครถนัดอะไร และการพูดคุยสื่อสารกัน มากกว่า การยึดติดที่เครื่องมือและกระบวนการ ยอมรับความเปลี่ยนแปลง เน้นความพอใจให้ลูกค้า ลูกค้าชอบ มีการส่งมอบ software อย่างต่อเนื่อง 
ส่วน Waterfall เป็นการทำงานตามลำดับขั้น  ลูกค้าเห็นและทดลองใช้ Software ก็ต่อเมื่อถึงขั้นตอนสุดท้าย หากมีบางอย่างที่ไม่ตรงกับความต้องการของลูกค้า การแก้ไขยาก แพง เสียเวลา การแก้ไขจำเป็นต้องเริ่มรอบใหม่
(2.)  เห็นด้วยอย่างยิ่ง เพราะ ทั้งCVS, SVN นั้นใช้ central code repository model คือ changes ของ file ทั้งหมดถูกเก็บอยู่ที่ central repo หรือศูนย์กลางที่เดียว ถ้าสมมติว่า central repo เกิดพังขึ้นมาหรือผู้ใช้ไม่สามารถติดต่อกับ central repo ได้ก็จะทำให้ไม่สามารถดึงไฟล์ที่พึ่งเปลี่ยนแปลงมาทีตัวเองได้ ส่วน Git นั้น แต่ละคนจะมี copy ของไฟล์ตั้งแต่เริ่มแรกจนท้ายสุด ดังนั้นแต่ละทีมหรือแต่ละคนสามารถ maintain code ได้โดยที่ทุกคนมี copy ของไฟล์ทั้งหมดอยู่ ของแต่ละ version ที่เกิดขึ้นจากหลายๆ ทีมนั้นสามารถรวมกันได้ ไม่จำเป็นต้องรอ changes copy จาก central repo อีกต่อไป ดังนั้น จึงเร็วกว่า และผู้ใช้งานก็สามารถแก้ได้ทุกที่ โดยไม่จำเป็นจะต้องติดต่อกับ central repo ก็ได้
(3.)  
-  git branch feature1 
-  git commit -m "work completed"
-  git remote add origin https://github.com/57160540/final_part_1
-  git push -u origin master
(4.) จากคำกล่าวของรุ่นพี่  ทำให้มือใหม่อย่างเราได้เตรียมตัวรับมืออย่างถูกทาง สืบเสาะหาวิธีแก้ไขได้อย่างมีประสิทธิภาพ เพื่อความรวดเร็วของงานที่ออกมา ไม่เกิดความล่าช้า 
(6.)  จากคำกล่าวเขาคนนี้อาจจะไม่ชอบความยุ่งยาก หรืออาจจะไม่ถนัดในด้านการทำ Application ซะมากกว่า อีกอย่างเป็นการย่นระยะเวลาของการทำงานได้เยอะ ไม่ต้องมานั่งผลิตเอง อีกอย่างผลลัพธ์ที่ได้มาก็ไม่ต่างอะไรไปจากซอฟต์แวร์ทั่วๆไป  ที่ทำงานได้เหมือนกัน
(7.) ขั้นตอนมีดังนี้
1. เริ่มจาก Client ส่ง Request ไปที่ Web App ซึ่งจะถูกส่งต่อให้ Rails router
2. Rails router รับข้อมูลมา ซ่งจะถูกส่งต่อให้ Controller ทำการตรวจสอบข้อมูลที่มาให้ (Request Method, Request Parameters) 
3. แล้ว Controller จะเรียก Method ให้ทำงานเพื่อจัดการ Request นั้น 
4. Model จะทำการคำนวณและอาจติดต่อกับ Database เพื่อจัดการกับ Request  
นั้น 
5. แล้วส่งผลลัพธ์กลับไปที่ Controller 
6. เมื่อ Controller ได้ผลลัพธ์จาก Model แล้วก็ใช้ผลลัพธ์นั้นส่งต่อให้ View ทำงาน 
7. View จะสร้าง Page สำหรับแสดงผลลัพธ์นั้น แล้วส่ง page กลับไปที่ Controller  
8. Controller ส่ง Page นั้น (เป็น Response) กลับไปยัง Client
(9.)  Heroku เป็น Platform as a Service (Paas) ที่ให้เราใช้งานได้ฟรี (มีแบบเสียเงินด้วย) โดยรองรับภาษาโปรแกรมที่หลากหลาย เช่น Ruby, PHP, Node.js, Python, Java, Clojure, Scala และยังสามารถสร้าง buildpack สำหรับภาษาอื่นๆได้ เช่น Lua ที่รันอยู่บน OpenResty ได้
มีบทบาทกับ Application คือ สามารถสร้างแอปไปรันบน Heroku จะทำผ่าน heroku toolbelt ส่วนของโค้ดที่จะเขียน ก็ใช้ text editor ได้ตามความถนัดครับ โค้ดตัวอย่างเริ่มต้น ผมเลือกภาษา Python และ Flask web framework มาให้ดู เพราะโค้ดที่สั้น เข้าใจง่าย
(10.) เพราะ มีกระบวนการพัฒนาซอฟต์แวร์ การบริหารโครงการซอฟต์แวร์กระบวนการวิศวกรรมความต้องการ แบบจำลองระบบ การออกแบบ การสร้างซอฟต์แวร์ การทดสอบ การตรวจสอบความถูกต้อง การจัดการและควบคุมการเปลี่ยนแปลงในการพัฒนางานด้านซอฟต์แวร์ การบำรุงรักษาซอฟต์แวร์

