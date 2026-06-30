# syntax=docker/dockerfile:1

# ใช้เวอร์ชันที่เฉพาะเจาะจงเพื่อความเสถียร
FROM python:3

# ตั้งค่า Environment variables
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# กำหนดโฟลเดอร์ทำงาน
WORKDIR /code

# ติดตั้ง dependencies ก่อนเพื่อใช้ประโยชน์จาก Docker Cache
COPY requirements.txt /code/
RUN pip install -r requirements.txt

# คัดลอก source code ทั้งหมด
COPY . /code/

# รันคำสั่งเริ่มต้น (สำหรับ Development)
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]