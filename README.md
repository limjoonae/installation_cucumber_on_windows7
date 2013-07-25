# มาสร้างบ้านให้กับเจ้าหนูน้ำ (Capybara) กันเถอะ!!

หลังจากที่เราลง Environment ต่างๆที่จำเป็นกันจบครบแล้ว ขั้นตอนต่อไป จะเป็นการสร้างบ้านให้กับเจ้า capybara.

1. อันดับแรก ให้สร้าง Folder เอาชื่อตามงานที่ทำ หรือเอาที่ชอบๆละกัน เช่น capybara เลยเล่นง่ายดีฮะ :D.

```
C:\>mkdir capybara
```

หลังจากนั้นให้เข้าไปในตัวเจ้า capybara และสร้าง folder บังคับ เริ่มต้นด้วย features

```
C:\capybara>mkdir features
```

เข้าไปใน features สร้างอีก 2 folder ที่จำเป็น

```
C:\capybara\features>mkdir support
```
และ
```
C:\capybara\features>mkdir steps
```

หลังจากนั้นก็สร้างไฟล์ที่ชื่อ Gemfile(เป็นไฟล์ไม่ต้องมีนามสกุล) ในตัวของเจ้า capybara ด้วย โดยมีเนื้อไฟล์เบื้องต้นดังนี้

```gem
source 'https://rubygems.org'

gem 'cucumber-rails', '0.3.2'
gem 'capybara', '0.4.0.rc'
```



2. 
