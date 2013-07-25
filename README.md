# มาสร้างบ้านให้กับเจ้าหนูน้ำ (Capybara) กันเถอะ!!

หลังจากที่เราลง Environment ต่างๆที่จำเป็นกันจบครบแล้ว ขั้นตอนต่อไป จะเป็นการสร้างบ้านให้กับเจ้า capybara.

อันดับแรก ให้สร้าง Folder เอาชื่อตามงานที่ทำ หรือเอาที่ชอบๆละกัน เช่น capybara เลยเล่นง่ายดีฮะ :D.

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
และ
C:\capybara\features>mkdir steps
```

หลังจากนั้นก็สร้างไฟล์ที่ชื่อ Gemfile(เป็นไฟล์ไม่ต้องมีนามสกุล) เก็บไว้ใน path C:\capybara>
(หมายเหตุ: ในที่นี้ เราจะสร้าง Gemfile สำหรับการ run test บน IE Web Browser)

```gem
source 'https://rubygems.org'

gem 'cucumber-rails', '0.3.2'  #Necessary and Compatible for IE Browser
gem 'capybara', '0.4.0.rc'     #Necessary and Compatible for IE Browser
```

จากนั้น run คำสัง bundle install ไปก่อน 1 ทีเพื่อเรียกใช้ bundle ต่างๆที่จำเป็น

```
C:\capybara>bundle install
```

หาก run สำเร็จจะปรากฎข้อความ
```
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.
```

เรียบร้อยแล้ว อันดับต่อไป สร้างไฟล์ env.rb ที่ path C:\capybara\features\support
(หมายเหตุ: บรรทัดที่มี # เป็น config สำหรับผู้ที่ต้องการ run test โดยใช้ IE Web Browser)

```ruby
require 'capybara/cucumber'
require 'selenium-webdriver'  #require for ie browser
require 'rubygems'				    #require for ie browser
require 'rspec/expectations'	#require for ie browser

Capybara.app = "www.google.com" #you can change this default domain
Capybara.app_host = 'www.google.com'  #you can change this default domain
Capybara.default_selector = :css
Capybara.default_driver = :selenium
Capybara.register_driver :selenium do |app|			#require for ie browser
  Capybara::Selenium::Driver.new(app, :browser => :internet_explorer )
end
```

เกือบเสร็จสมบูรณ์แล้วว....
คราวนี้ เนื่องจากว่าโดยปกติการ run test จะมี web browser เริ่มต้นเป็น Firefox 
แต่เราไปบังคับให้มัน run บน IE ก็เลยต้องมีตัวช่วยนิดหน่อย นั่นก็คือ อือๆๆๆ [IEDriverServer](https://code.google.com/p/selenium/downloads/list)
ก็ไปดาวน์โหลดจากลิ้งค์นี้ได้เลย โดยเลือกให้เหมาะกับ Windows เราว่าจะ x86, x64 อะไรก็ว่าไป อ้อ!! โหลดเป็นไฟล์ .zip นะจ๊ะ

หลังจากที่ดาวน์โหลดมาเรียบร้อยแล้ว ก็จัดการแตก zip ไว้ที่ไหนซักที่นึง 
แล้วเอา path ที่เก็บ ไปใส่ไว้ใน Environment Variable ที่ชื่อ PATH ด้วยเพื่อให้เรียกใช้งานได้ตอนสั่ง run cucumber

เท่านี้ก็เรียบร้อยแล้ววว
ขั้นตอนต่อไปเราจะไปสร้างไฟล์ feature กับ step สำหรับ test กันล่ะ!!!
