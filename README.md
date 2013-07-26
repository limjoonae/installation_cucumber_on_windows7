#ขั้นตอนการติดตั้ง Cucumber on Windows Step by Step

อันดับแรก ดาวน์โหลด Rails Installer Package จาก [http://railsinstaller.org/en](http://railsinstaller.org/en) สำหรับระบบปฏิบัติการ Windows สำหรับ version ที่ผู้เขียนดาวน์โหลด เป็นตัว Ruby 1.9 ที่ประกอบด้วย Environment ต่างๆในตัวเดียว(เกือบครบครัน)

จากนั้นไปที่ไฟล์ที่โหลดเสร็จแล้ว กดติดตั้งได้เลยจ้า(Default การติดตั้งตามที่เขากำหนดมาให้) 

เมื่อเสร็จแล้ว เปิด cmd.exe ขึ้นมาเพื่อใช้ command line ให้ไปยังที่ที่เราติดตั้งโปรแกรมไว้ (ตัวอย่างต่อไปนี้เป็น Path ตามที่ผู้เขียนลงโปรแกรมไว้)

```
C:\>cd RailsInstaller
C:\RailsInstaller>
```

ตรวจสอบการติดตั้งว่าสามารถ run ruby ได้ โดยพิมพ์ ruby -v

```
C:\RailsInstaller>ruby -v
ruby 1.9.3p392 (2013-02-22) [i386-mingw32] <-- จะแสดง version ของ ruby ที่เราติดตั้งไป
```

ตรวจสอบการติดตั้งว่าสามารถ run gem ได้ โดยพิมพ์ gem -v

```
C:\RailsInstaller>gem -v
1.8.24 <-- จะแสดง version ของ gem ที่เราติดตั้งไป</p>
```

เมื่อมั่นใจแล้วว่ามี ต่อไปให้ run คำสั่ง gem install cucumber เพื่อดาวน์โหลด และติดตั้ง Cucumber

```
C:\RailsInstaller>gem install cucumber
Fetching....... ปรื้ดดดดๆๆๆๆๆ auto install กันไปยาวๆ (สังเกตดูตอน run ด้วยว่าต้องไม่มี error นะจ๊ะ :D)
```   

Make sure กับ cucumber ด้วยกัน run คำสั่ง cucumber --help  

```
C:\RailsInstaller>cucumber --help
จะมี result ออกมา
```   

ของผู้เขียน เมื่อ run แล้วจะมี message เกี่ยวกับ ANSICON เป็นตัวที่ใช้ในการแสดงสีของผลการ run cucumber เพราะตัว Windows เองไม่เข้าใจคำสั่งที่เป็น ANSI เกี่ยวกับเรื่องสี(แปลมาคร่าวๆได้ความประมาณนี้) ให้ไปดาวน์โหลด ANSICON จาก [http://adoxa.3eeweb.com/ansicon/](http://adoxa.3eeweb.com/ansicon/)

ดาวน์โหลดเสร็จเรียบร้อยแล้ว แตกไฟล์ไว้ที่ใดที่หนึ่ง(ถ้าสะดวกก็ที่ C: เลย) แล้วนำ Path ของโฟลเดอร์ไปวางไว้ที่ System Variable ที่ชื่อ Path เพื่อให้สามารถเรียกใช้งาน ANSICON ได้

จากนั้น ไปที่หน้า command prompt อีกครั้ง แล้ว run คำสั่ง ansicon -i (หรือ -I) เพื่อให้ตัว ansicon ทำงาน
   
```
C:\RailsInstaller>ansicon -i
ถ้า run ผ่านจะไม่เกิด action ใดๆ
```     

จากนั้นปิดหน้า command prompt เข้ามาอีกครั้ง แล้วลอง run คำสั่ง cucumber --help อีกที จะต้องไม่เห็น error msg เรื่อง ANSICON แล้ววว :)

ขั้นตอนต่อไป run คำสั่ง gem install capybara เพื่อดาวน์โหลดและติดตั้ง library ของตัว Capybara web automation 

```
C:\RailsInstaller>gem install capybara
```  

เมื่อเสร็จแล้วให้ run คำสั่ง gem install rspec เพื่อดาวน์โหลดและติดตั้ง library ต่างๆสำหรับการอ่าน การ compare code หรืออื่นๆ

```
C:\RailsInstaller>gem install rspec
```  

Automation Test ตัวนี้เบื้องต้นจะสามารถทำงานในบน Firefox web browser จึงควรมีไว้บนเครื่อง ถ้าไม่มีก็โหลดเนาะ ^^

เท่านี้ก็เรียบร้อยแล้วค๊าา สำหรับการลง cucumber on Windows เบื้องต้น

ขั้นตอนต่อไป เราจะไปสร้าง Folder สำหรับการ run Script Test กันจ้าา~~

หากทำตามขั้นตอนด้านบนแล้วติดปัญหา ดูเพิ่มเติมได้ที่
[www.richardlawrence.info](http://www.richardlawrence.info/2011/08/20/getting-started-with-ruby-cucumber-and-capybara-on-windows/)



# มาสร้างบ้านให้กับเจ้าหนูน้ำ (Capybara) กันเถอะ!!

หลังจากที่เราลง Environment ต่างๆที่จำเป็นกันจบครบแล้ว ขั้นตอนต่อไป จะเป็นการสร้างบ้านให้กับเจ้า capybara.

อันดับแรก ให้สร้าง Folder เอาชื่อตามงานที่ทำ หรือเอาที่ชอบๆละกัน เช่น capybaraHome เลยเล่นง่ายดีฮะ :D.

```
C:\>mkdir capybaraHome
```

หลังจากนั้นให้เข้าไปใน capybaraHome เพื่อสร้างห้องที่ชื่อว่า features

```
C:\capybaraHome>mkdir features
```

เข้าไปใน features สร้างอีก 2 ห้อง ที่จำเป็น

```
C:\capybaraHome\features>mkdir support
และ
C:\capybaraHome\features>mkdir steps
```

เสร็จแล้ววว บ้านของเจ้า capybara  :D



## ใส่เฟอร์นิเจอร์ต่างๆเข้าไปในบ้าน

เนื่องจากเรามีบ้านแล้ว แต่เรายังไม่มีข้าวของเครื่องใช้ในบ้านซ้ากกกอย่าง เราเลยจะเอาเฟอร์นิเจอร์ต่างๆมาใส่ให้

ให้ไปสร้างไฟล์ที่ชื่อ Gemfile(เป็นไฟล์ไม่ต้องมีนามสกุล) เก็บไว้ใน  C:\capybaraHome>

Gemfile แบบปกติ (Default browser: Firefox)

```gem
source 'https://rubygems.org'

gem 'cucumber', '~> 1.3.4'
gem 'capybara', '~> 1.1.2'
gem 'rspec', '~> 2.8.0'
```

แต่ถ้าต้องการให้ run บน  IE ได้ ให้ set Gemfile ด้วย gem ตามด้านล่าง

```gem
source 'https://rubygems.org'

gem 'cucumber-rails', '0.3.2'  #Necessary and Compatible for IE Browser
gem 'capybara', '0.4.0.rc'     #Necessary and Compatible for IE Browser
```

จากนั้น run คำสัง bundle install เพื่อเรียกใช้ bundle ต่างๆที่จำเป็น

```
C:\capybaraHome>bundle install
```

หาก run สำเร็จจะปรากฎข้อความ
```
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.
```

เรียบร้อยแล้ว อันดับต่อไป สร้างไฟล์ env.rb ที่ path C:\capybaraHome\features\support

env.rb แบบปกติ (Default browser: Firefox)

```ruby
require 'capybara/cucumber'

Capybara.app = "domain name"
Capybara.run_server = false
Capybara.app_host = 'domain name'
Capybara.default_selector = :css
Capybara.default_driver = :mechanize
Capybara.default_driver = :selenium
```

แต่ถ้าต้องการให้ run บน  IE ได้ ให้ set env.rb เพิ่มเติมตามด้านล่าง

```ruby
require 'capybara/cucumber'
require 'selenium-webdriver'  #require for ie browser
require 'rubygems'   	#require for ie browser
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
สามารถไปดาวน์โหลดจากลิ้งค์นี้ได้เลยจ้า โดยเลือกให้เหมาะกับ Windows เราว่าจะ x86, x64 อะไรก็ว่าไป อ้อ!! โหลดเป็นไฟล์ .zip นะจ๊ะ

หลังจากที่ดาวน์โหลดมาเรียบร้อยแล้ว ก็จัดการแตก zip ไว้ที่ไหนซักที่นึง 
แล้วเอา path ที่เก็บ ไปใส่ไว้ใน Environment Variable ที่ชื่อ PATH ด้วยเพื่อให้เรียกใช้งานได้ตอนสั่ง run cucumber

เท่านี้ก็เรียบร้อยแล้ววว
ขั้นตอนต่อไปเราจะไปสร้างไฟล์ feature กับ step สำหรับ test กันล่ะ!!!
