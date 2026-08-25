OWNER	id	Key	INTEGER	ใช้ระบุเจ้าของแต่ละคนไม่ให้ซ้ำ
OWNER	name	Simple	VARCHAR(100)	เก็บชื่อเจ้าของ
OWNER_PHONE	phone	Multivalued	VARCHAR(20)	เจ้าของ 1 คนมีเบอร์โทรได้หลายเบอร์
PET	id	Key	INTEGER	ใช้ระบุสัตว์แต่ละตัว
PET	name	Simple	VARCHAR(100)	เก็บชื่อสัตว์
PET	birth_date	Simple	DATE	เก็บวันเกิดของสัตว์
PET	age	Derived	ไม่ต้องเก็บ	คำนวณอายุจากวันเกิดและวันที่ปัจจุบัน
VET	id	Key	INTEGER	ใช้ระบุสัตวแพทย์แต่ละคน
VET	name	Simple	VARCHAR(100)	เก็บชื่อสัตวแพทย์
SPECIALTY	id	Key	INTEGER	ใช้ระบุความเชี่ยวชาญ
SPECIALTY	specialty_name	Simple	VARCHAR(100)	เก็บชื่อด้านความเชี่ยวชาญ
VISIT	id	Key	INTEGER	ใช้ระบุการเข้ารับบริการแต่ละครั้ง
VISIT	visit_no	Simple	INTEGER	เก็บลำดับครั้งที่ 1, 2, 3... ของสัตว์
VISIT	visit_date	Simple	TIMESTAMP	เก็บวันและเวลาเข้ารับบริการ
VISIT	total_amount	Simple	NUMERIC(10,2)	เก็บยอดเงินแบบมีทศนิยม และยอดหลังรับเงินไม่เปลี่ยน
SERVICE_ITEM	id	Key	INTEGER	ใช้ระบุรายการบริการ
SERVICE_ITEM	item_name	Simple	VARCHAR(100)	เก็บชื่อยา/บริการ
SERVICE_ITEM	quantity	Simple	INTEGER	เก็บจำนวนรายการ
SERVICE_ITEM	price	Simple	NUMERIC(10,2)	เก็บราคาที่มีทศนิยม
