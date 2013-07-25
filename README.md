# มาสร้างบ้านให้กับเจ้าหนูน้ำ (Capybara) กันเถอะ!!
[![Build Status](https://secure.travis-ci.org/jnicklas/capybara.png)](http://travis-ci.org/jnicklas/capybara)
[![Dependency Status](https://gemnasium.com/jnicklas/capybara.png)](https://gemnasium.com/jnicklas/capybara)
[![Code Quality](https://codeclimate.com/badge.png)](https://codeclimate.com/github/jnicklas/capybara)

หลังจากที่เราลง Environment ต่างๆที่จำเป็นกันจบครบแล้ว ขั้นตอนต่อไป จะเป็นการสร้างบ้านให้กับเจ้า capybara.

1. อันดับแรก ให้สร้าง Folder เอาชื่อตามงานที่ทำ หรือเอาที่ชอบๆละกัน เช่น capybara เลยเล่นง่ายดีฮะ :D.

```
C:\capybara>mkdir features
```

หลังจากนั้นก็สร้างไฟล์ที่ชื่อ Gemfile(เป็นไฟล์ไม่ต้องมีนามสกุล) ในตัวของเจ้า capybara ด้วย โดยมีเนื้อไฟล์เบื้องต้นดังนี้

```gem
source 'https://rubygems.org'

gem 'cucumber-rails', '0.3.2'
gem 'capybara', '0.4.0.rc'
```



2. 
