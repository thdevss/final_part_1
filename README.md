## ข้อ 1
การใช้ waterfall อาจจะอำนวยความสะดวกในด้านการมีหลักฐานไปเบิกงบประมาณ แต่ก็เป็นดาบสองคม เมื่อมีการต้องเปลี่ยนแปลงหรือปรับเปลี่ยนความต้องการของระบบ การใช้ Agile ย่อมเหมาะกว่า เพราะสามารถปรับเปลี่ยนแปลงได้ง่าย ไม่ต้องผ่านขั้นตอนการประชุมหรือวิเคราะห์ข้อมูลเยอะแยะ แต่กลับกัน การใช้ waterfall อาจต้องเสียเวลานานในการทำเอกสารก่อนที่จะมีการลงโค้ด และนั่นอาจทำให้การเปลี่ยนแปลงที่เราต้องการนั้น มันสายเกินกว่าที่เราจะสามารถนำเอามาใช้งานได้ (เช่น เว็บแอพฯที่ต้องมีการเกาะตามกระแสสังคม ถ้าต้องรอการประชุมและทำเอกสารเสร็จ อาจไม่ทันการ) อีกทั้ง Agile ยังมีข้อดีเรื่องค่าใช้จ่ายที่น้อยกว่า เพราะไม่ต้องสิ้นเปลืองทำเอกสาร แต่ก็เป็นดาบสองคม เพราะการไม่มีเอกสารสเปคอะไรอ้างอิง ย่อมส่งผลให้โปรแกรมเมอร์ต้องคิดเองมากขึ้น เหนื่อยมากขึ้น อีกทั้งหากมีการทำงานเป็นทีม ถ้าไม่มีการประชุมตกลงเรื่องมาตรฐานโค้ดกันก่อน สิ่งที่ได้มาอาจจะกลายเป็นโค้ดที่ไม่มีมาตรฐาน หรือไม่เป็นไปในทิศทางเดียวกัน โค้ดอ่านยาก แก้ตามลำบาก...

## ข้อ 2
อาจเป็นเรื่องจริง เพราะปัจจุบันมีการทำงานเป็นทีมมากขึ้น และเมื่อมีความเป็นทีม งานก็ควรจะเอากลับไปทำต่อในส่วนของตนเอง แล้วสามารถเอากลับมาประกอบร่างได้ โดยที่งานคนอื่นก็ไม่เสียหายด้วย ซึ่งความเป็น Git ได้รองรับในจุดๆนี้ ซึ่งแตกต่างจาก CVS หรือ SVN ทั่วๆไป ที่ต้องทยอยอัพขึ้นทุกครั้งที่มีการแก้ไข และทีมต้องคอยอัพเดทไฟล์ล่าสุดก่อนทำการแก้ไขฟังค์ชั่นใหม่ๆ ซึ่งไม่สะดวก จัดการยาก และทำให้การทำงานล่าช้า

## ข้อ 3
```sh
$ git checkout -b feature1
$ git add -A
$ git commit -m "first commit"
$ git push origin master
```

## ข้อ 4
อาจเกิดเพราะคนในทีมไม่มีการคุยกัน ซึ่งในความเป็นจริงควรจะคุยกันและเลือกโค้ดที่ดีที่สุดในการ merge แต่ละครั้ง 

## ข้อ 5
```sh
abcde
```
[![picture](http://i.imgur.com/PDalw7N.png)](http://i.imgur.com/PDalw7N.png)

## ข้อ 6
เป็นแนวคิดที่ค่อนข้างอนุรักษ์นิยม แต่มองกลับในความเป็นจริง การใช้แผ่น CD ในการติดตั้งโปรแกรมแทบจะไม่มีเห็นแล้วในปัจจุบัน (แม้แต่ลง OS ยังใช้ Flash Drive แทนแผ่น CD) ซึ่งแนวคิดในการทำ web application ก็เป็นอีกหนึ่งปัจจัยที่ทำให้การใช้แผ่น CD ลงโปรแกรมได้รับความนิยมน้อยลง เพราะสะดวก สะบาย ใช้งานง่าย ใช้งานจากที่ไหนก็ได้ ขอแค่มีคอมพิวเตอร์ , Browser , Internet 3 อย่างพอ อีกทั้ง **Web Application เมื่อมีการปรับปรุงหรืออัพเดทเวอร์ชั่นใหม่ๆ ย่อมทำได้ง่ายกว่าการอัพเดทโปรแกรมที่เป็นแผ่น CD เพราะไม่ต้องเสียค่าปั๊มแผ่นเพิ่ม ไม่ต้องเสียค่าขนส่ง สามารถยัดขึ้นเว็บแล้วแจ้งผู้ใช้ได้เลย**

## ข้อ 7
	1. user เรียกใช้งานผ่าน url : /user
	2. ผ่าน rails router วิ่งไปยัง controller
	3. controller เรียก method User.all ใน Model user.rb
	4. method User.all ใน model ทำการเรียกข้อมูลจากฐานข้อมูลออกมา
	5. method User.all ใน model ส่งข้อมูลกลับมายัง controller
	6. เรียกหน้า view (index.html.erb) โดยส่งตัวแปรที่ชื่อ @users ที่เป็นข้อมูลที่ดึงมาจากข้อ 4 ขึ้นไปด้วย
	7. ทำการ generate HTML ออกมา โดยใช้ design ที่โค้ดลงในไฟล์ index.html.erb และข้อมูลที่ส่งผ่านตัวแปร @users แล้วส่งไปยัง controller
	8. controller ทำการส่ง HTML ที่ generate มาแล้ว ไปยัง user ที่เรียกใช้งาน

## ข้อ 8
Codeigniter Framework คือตัวที่เคยใช้มาก่อน ซึ่งเขียนบนภาษา PHP ซึ่งจำแนกข้อดีขอเสียได้ประมาณนี้
#### Codeigniter
##### ข้อดี
- ศึกษาง่าย เข้าใจไว
- คู่มืออ่านง่าย มีตัวอย่างเยอะ
- ไวกว่า php framework ตัวอื่นๆที่มีความสามารถใกล้ๆกัน
- ใช้บน Share Hosting ทั่วไปได้
##### ข้อเสีย
- library ติดตัวมาน้อย ต้องหาเองเพิ่ม
- ไม่มี command-line ให้เล่นแบบ RoR

#### Rails Framework
##### ข้อดี
- มี command-line ให้ใช้
- สามารถ generate code มาเพื่อขึ้นงานได้อย่างว่องไว
- มี automation test ติดตัวมาด้วย
- ตรวจสอบคุณภาพโค้ดก็ยังได้
##### ข้อเสีย
- แรกเริ่มเรียนรู้ยาก เนื่องจากความเป็น Ruby Syntax มันสั้น ต้องใช้เวลาปรับตัว (ชินกับ PHP)
- rails server บน locahost ช้า (มากก...)
- หา Hosting ใช้ยาก (ต้องยัดขึ้น Heroku หรือเซ็ต Cloud ขึ้นมาเอง)


## ข้อ 9
Heroku คือ Cloud ชนิดหนึ่ง ที่เป็น Platform as a Service ซึ่งรองรับหลายๆภาษายอดนิยมสำหรับการทำเว็บแอพลิเคชั่น ช่วยอำนวยความสะดวกในการจัดการ Infrastructure ให้เราไม่ต้องนั่งติดตั้งระบบเอง หรือแม้แต่การเซ็ตระบบให้รองรับ Load สูงๆ อีกทั้งยังช่วยอำนวยความสะดวกในการเพิ่ม Node ใช้งาน ในกรณีที่ต้องรองรับ Load สูงๆ ซึ่งถ้าใช้ Cloud ตั้งเอง หรือ Server ของตัวเอง ต้องมีการทำ Solution รองรับในจุดนี้ แต่ Heroku มีการจัดการทั้งหมดให้ เพียงปลายนิ้วคลิ้ก และเงินถึง...



## ข้อ 10
**เรียนรู้ให้หลากหลาย** น่าจะเหมาะสมที่สุด จากการที่มีวิชา 887240 ที่เป็นวิชาเกี่ยวกับการทำเอกสาร (waterfall method) จึงต้องมีวิชานี้เข้ามาในหลักสูตร เพื่อทำให้เห็นอีกรูปแบบหนึ่งของการทำงานที่ไม่จำเป็นต้องใช้เอกสารยุ่งยากมากมาย แต่ให้ผลลัพธ์เทียบเท่าหรือดีกว่า (?) เพื่อให้นิสิตได้เรียนรู้ เมื่อถึงเวลาออกไปทำงานจริงๆ จะได้สามารถปรับตัวเข้ากับรูปแบบการทำงานขององค์กรนั้นๆได้ ไม่ว่าจะใช้รูปแบบการทำงานแบบ Waterfall หรือ Agile ก็ตาม...