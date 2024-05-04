# Comparing-High-Rated-Books-from-Amazon-and-Goodreads
## The tools used in this project.
- [Google Colaboratory](https://colab.research.google.com/)
- [MongoDB Atlas](https://www.mongodb.com/cloud/atlas/register) (NoSQL database)

## Work process
### Data sources
- Amazon: Dataset from [Kaggle](https://drive.google.com/drive/folders/1IUBq38A2Mg0Yg-921UvA0zlbnOPTsr-0?usp=sharing)
- Goodreads: Web scraping from this collection ["Best Books Ever"](https://www.goodreads.com/list/show/1.Best_Books_Ever?page=1)

### Data understanding from Goodreads

| Column Name  | Data type |
|:---|:---| 
|ISBN_13  |รหัสหนังสือ 13 หลัก
|BookTitle  |ชื่อหนังสือ
|BookAuthor  |ชื่อผู้แต่ง
|avgRating  |เรทติ้งโดยเฉลี่ย
|TotalRate  |จำนวนเรทติ้งทั้งหมด
|TotalReview  |จำนวนรีวิวทั้งหมด
|BookFormat  |รูปแบบหนังสือประกอบด้วยจำนวนหน้าและรูปแบบหนังสือเช่น Hardcover, Ebooks เป็นต้น
|PublishedDate  |วันที่ตีพิมพ์
|Categories  |หมวดหมู่
|Linkhref  |ลิงก์ไปที่หน้าหนังสือ
|TotalScorebyVote  |จำนวนคะแนนโหวตจากคนใน community
|TotalVote  |จำนวนคนใน community ที่โหวตทั้งหมด

### Data understanding from Amazon
 - book_data

| Column Name  | Description |
|:---|:---|
|Title  |ชื่อหนังสือ
|description  |คำอธิบายหนังสือ
|authors  |ชื่อผู้แต่ง
|image  |ปกหนังสือ
|previewLink  |ลิงก์ไปหน้าพรีวิว
|publisher  |สำนักพิมพ์
|publishedDate  |วันที่ตีพิมพ์
|infoLink  |ลิงก์ไปหน้าข้อมูลของหนังสือ
|categories   |หมวดหมู่
|ratingsCount  |จำนวนเรทติ้งทั้งหมด

- book_rating

| Column Name  | Description |
|:---|:---|
|Id  |รหัสรีวิว
|Title  |ชื่อหนังสือ
|Price  |ราคาหนังสือ
|User_id  |รหัสผู้ใช้
|profileName  |ชื่อผู้ใช้
|review/helpfulness  |ความช่วยเหลือในการรีวิว
|review/score  |คะแนนรีวิว
|review/time  |จำนวนครั้งที่รีวิว
|review/summary  |รีวิวสรุป
|review/text  |ข้อความรีวิว

### Data Cleaning From Goodreads
- Drop columns that are not used, including TotalScorebyVote, TotalVote, and Linkhref.
- Drop rows with null values.
- Clean data from TotalRate and TotalReview by keeping only numerical values.
- Clean data from BookFormat by keeping only the book format and not the number of pages.
- Clean data from PublishedDate by keeping only the day, month, and year.
- Drop rows with duplicate ISBN values.

### Data Cleaning From Amazon
- Clean the book_data by checking for missing data and removing unused columns.
- Check the data types and convert them if necessary.
- Calculate the average rating from the book_rating and merge it with book_data.

### Storing Goodreads data into MongoDB Atlas

<p align="center">
  <img width="543" height="226" src="https://github.com/Boat2356/Comparing-High-Rated-Books-from-Amazon-and-Goodreads/assets/140761543/2364f0ae-e26e-4ee2-a251-4d65dec307f6">
</p>

### Storing Amazon Books data into MongoDB Atlas

<p align="center">
  <img width="543" height="226" src="https://github.com/Boat2356/Comparing-High-Rated-Books-from-Amazon-and-Goodreads/assets/140761543/426ae7a2-ca6a-4f59-bdf1-5c7779c718a4">
</p>

### Data Visualization
- Graph displaying the 20 lowest-rated books on Goodreads.

<p align="center">
  <img width="543" height="296" src="https://github.com/Boat2356/Comparing-High-Rated-Books-from-Amazon-and-Goodreads/assets/140761543/f73c78ec-d020-47b8-aa5c-c6d3de73ca9c">
</p>

- Graph displaying the 20 lowest-rated books on Amazon.

<p align="center">
  <img width="543" height="226" src="https://github.com/Boat2356/Comparing-High-Rated-Books-from-Amazon-and-Goodreads/assets/140761543/2b5561a3-6609-46e4-9568-091a2da54963">
</p>

- Graph displaying the 20 highest-rated books on Goodreads.

<p align="center">
  <img width="543" height="226" src="https://github.com/Boat2356/Comparing-High-Rated-Books-from-Amazon-and-Goodreads/assets/140761543/c28f6dca-a8c2-4934-a808-0bae74c06a81">
</p>

- Graph displaying the 20 highest-rated books on Amazon.

<p align="center">
  <img width="543" height="226" src="https://github.com/Boat2356/Comparing-High-Rated-Books-from-Amazon-and-Goodreads/assets/140761543/9b6ee62f-8757-42ae-8618-df4fad09fd83">
</p>

