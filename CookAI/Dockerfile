FROM python:3.12-slim

WORKDIR /app

# copy requirements ก่อนเพื่อให้ Docker cache layer นี้ไว้ (ถ้าโค้ดเปลี่ยนแต่ requirements ไม่เปลี่ยน
# จะไม่ต้อง pip install ใหม่ทุกครั้ง ทำให้ build เร็วขึ้นมาก)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# copy โค้ดที่เหลือทั้งหมดเข้า image
COPY . .

EXPOSE 8000

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
