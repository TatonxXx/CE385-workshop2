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

OWNER_PHONE owner_id Foreign Key INTEGER เก็บ ID ของเจ้าของ ชี้ไปที่ OWNER.id

PET owner_id Foreign Key INTEGER เก็บ ID ของเจ้าของ ชี้ไปที่ OWNER.id

VET_SPECIALTY vet_id Foreign Key INTEGER เก็บ ID ของสัตวแพทย์ ชี้ไปที่ VET.id

VISIT pet_id Foreign Key INTEGER เก็บ ID ของสัตว์เลี้ยง ชี้ไปที่ PET.id

VISIT vet_id Foreign Key INTEGER เก็บ ID ของสัตวแพทย์ ชี้ไปที่ VET.id

SERVICE_ITEM visit_id Foreign Key INTEGER เก็บ ID ของการเข้ารับบริการ ชี้ไปที่ VISIT.id

ตาราง (Entities)

OWNER: เก็บข้อมูลเจ้าของสัตว์เลี้ยง (รหัสเจ้าของ, ชื่อ-นามสกุล, ที่อยู่สำหรับทำรายงานรายเขต)

OWNER_PHONE: ตารางเบอร์โทรศัพท์ของเจ้าของ (รองรับกรณีเจ้าของ 1 คนมีได้หลายเบอร์)

PET: เก็บข้อมูลสัตว์เลี้ยง (รหัสสัตว์, ชื่อ, วันเกิดสำหรับคำนวณอายุ, รหัสเจ้าของ)

VET: เก็บข้อมูลสัตวแพทย์ผู้ตรวจ (รหัสสัตวแพทย์, ชื่อ-นามสกุล)

VET_SPECIALTY: ตารางความเชี่ยวชาญเฉพาะทางของสัตวแพทย์ (รองรับกรณีสัตวแพทย์ 1 คนมีความเชี่ยวชาญได้หลายด้าน)

VISIT: เก็บประวัติการเข้ารับบริการ (รหัสการตรวจ, ลำดับครั้งที่เข้าตรวจ, วันเวลาที่ตรวจ, ยอดรวมเงิน, รหัสสัตว์, รหัสสัตวแพทย์)

SERVICE_ITEM: เก็บรายการยาหรือบริการแต่ละครั้ง (รหัสรายการ, ชื่อยา/บริการ, ขนาดยา, จำนวนวัน, จำนวนชิ้น, ราคา, รหัสการตรวจ)

เส้นความสัมพันธ์ (Relationships)

fk_OWNER_PHONE_owner_id_OWNER: เชื่อมเจ้าของกับเบอร์โทรศัพท์ (ความสัมพันธ์แบบ 1 ต่อ N)

fk_PET_owner_id_OWNER: เชื่อมเจ้าของกับสัตว์เลี้ยง (เจ้าของ 1 คนมีสัตว์เลี้ยงได้หลายตัว)

fk_VISIT_pet_id_PET: เชื่อมสัตว์เลี้ยงกับการเข้ารับบริการ (สัตว์เลี้ยง 1 ตัวเข้ารับบริการได้หลายครั้ง)

fk_VISIT_vet_id_VET: เชื่อมสัตวแพทย์กับการเข้ารับบริการ (สัตวแพทย์ 1 คนตรวจการรับบริการได้หลายครั้ง)

fk_VET_SPECIALTY_vet_id_VET: เชื่อมสัตวแพทย์กับความเชี่ยวชาญ (สัตวแพทย์ 1 คนมีได้หลายความเชี่ยวชาญ)

fk_SERVICE_ITEM_visit_id_VISIT: เชื่อมการเข้ารับบริการกับรายการยา/บริการ (การเข้ารับบริการ 1 ครั้งมีรายการยา/บริการได้หลายรายการ)
