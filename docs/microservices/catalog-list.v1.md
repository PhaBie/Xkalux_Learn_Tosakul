# API รายการสินค้า

สถานะ: PROPOSED
รุ่น: v1
เจ้าของข้อเสนอ: Microservice

คำขอ: GET /api/v1/catalog/products
Request body: ไม่ส่ง

Fields:
id: pencil:string
name: ดินสอ:string
priceSatang: 1200:number
available: true:boolean

id: ruler:string
name: ไม้บรรทัด:string
priceSatang: 2000:number
available: false:boolean

id: eraser:string
name: ยางลบ:string
priceSatang: 800:number
available: true:boolean

id: sharpener:string
name: กบเหลาดินสอ:string
priceSatang: 1500:number
available: false:boolean

Query:
?available = true : จะได้สินค้าที่มีสต๊อกอยู่ tag available สินค้านั้นต้องเป็น true ถึงจะขึ้นแสดงผล ได้แก่ pencil , eraser Status code 200

    ?available = false : จะได้สินค้าที่มีสต๊อกอยู่ tag available สินค้านั้นต้องเป็น false ถึงจะขึ้นแสดงผล ruler , sharpener จะได้ Status code 200

    ?available = yes : จะได้ status code 422 เพราะค่าไม่ตรงกับที่เรากำหนดไว้

    ? = Status 200 ไม่มีเงื่อนไข Query ได้ของที่มีทั้งหมด

กรณีผิดพลาด:
ถ้าใส่ ?available เฉยๆ แล้วไม่ใช่ = true / false ต่อ จะได้ status code 422 เพราะ ไม่เข้าเงื่อนไข
catalog-list.v1.md
